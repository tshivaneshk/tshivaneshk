# Mission Control Operations & Configuration Guide

This repository (`tshivaneshk/tshivaneshk`) contains the complete space-themed Mission Control developer portfolio.

---

## 1. Required GitHub Settings

To enable the automated scheduled workflows (3D City Observatory generator and Telemetry timestamp sync):

1. Navigate to: `https://github.com/tshivaneshk/tshivaneshk/settings/actions`
2. Scroll down to **Workflow permissions**.
3. Select **Read and write permissions**.
4. Check **Allow GitHub Actions to create and approve pull requests**.
5. Click **Save**.

---

## 2. Generating the 3D City Visualization

The 3D contribution city is generated automatically on a daily schedule via `.github/workflows/contributions.yml` and committed to the `output` branch.

To trigger generation immediately:

```pwsh
gh workflow run contributions.yml
```

Once the action completes, `profile-night-rainbow.svg` is stored in the `output` branch and served directly inside the Observatory picture element. If the branch or asset is momentarily unavailable, the built-in `assets/city-fallback.svg` immediately displays.

---

## 3. Telemetry Timestamp Sync

The `.github/workflows/update-timestamp.yml` workflow runs every 6 hours to sync the mission telemetry UTC timestamp between marker comments at the bottom of the README.
