# Mission Control Profile Setup & Operations Manual

This repository (`tshivaneshk/tshivaneshk`) powers your personal GitHub profile README through self-contained SVG modules and automated GitHub Actions.

---

## 1. Required GitHub Settings

To enable the automated workflows (3D City contribution generator, Pacman arcade graph, Crew Log updater, and Telemetry timestamp sync), ensure your repository workflow permissions are set to **Read and write permissions**:

1. Navigate to: `https://github.com/tshivaneshk/tshivaneshk/settings/actions`
2. Scroll down to **Workflow permissions**.
3. Select **Read and write permissions**.
4. Check the box **Allow GitHub Actions to create and approve pull requests**.
5. Click **Save**.

---

## 2. Automated Workflows Overview

| Workflow | File | Frequency | Output Target |
|---|---|---|---|
| **Contributions & City** | `.github/workflows/contributions.yml` | Daily @ 00:00 UTC, push to main, or manual dispatch | `output` branch (`profile-3d-contrib/*`, `pacman.svg`, `pacman-dark.svg`) |
| **Crew Log Guestbook** | `.github/workflows/crew-log.yml` | Triggered when visitors open an issue with label `crew-log` | Directly patches the `<!-- CREW_LOG_START -->` section of `README.md` |
| **Telemetry Sync** | `.github/workflows/update-timestamp.yml` | Every 6 hours | Updates UTC timestamp in `README.md` |

---

## 3. Triggering the Initial Build

You can trigger the 3D contribution and Pacman graph generation immediately from your terminal or the GitHub Actions tab:

```pwsh
gh workflow run contributions.yml
```

Once the run completes (approx. 1-2 minutes), the `output` branch will contain the visual files referenced by the README.

---

## 4. Testing the Crew Log

1. Click on the badge **TRANSMIT_LOG** or open an issue using the template at `.github/ISSUE_TEMPLATE/crew-log.yml`.
2. Fill out the callsign and transmission message.
3. Upon submission, the `crew-log.yml` workflow will automatically sanitize the input, update the README with the 5 latest entries, post a comment, and close the issue.
