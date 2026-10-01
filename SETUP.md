# Mission Control Setup & Operations Manual

This repository (`tshivaneshk/tshivaneshk`) contains the complete space-themed Mission Control developer portfolio.

---

## 1. Required GitHub Settings

To enable the automated workflows (3D City Observatory generator, Comms Crew Log and Decryption Puzzle processor, and Daily Transmission synchronizer):

1. Navigate to: `https://github.com/tshivaneshk/tshivaneshk/settings/actions`
2. Scroll down to **Workflow permissions**.
3. Select **Read and write permissions**.
4. Check **Allow GitHub Actions to create and approve pull requests**.
5. Click **Save**.

---

## 2. Generating the 3D City Visualization

The 3D contribution city is generated automatically on a daily schedule via `.github/workflows/contributions.yml` and committed to the `output` branch.

To trigger the first generation immediately:

```pwsh
gh workflow run contributions.yml
```

Once the action completes, `profile-3d-contrib/profile-night-rainbow.svg` will be available in the `output` branch and render directly inside the Observatory module.

---

## 3. Interactive Visitor Features

### Crew Log
- Visitors click **Sign the crew log** (`assets/sign-crew-log.svg`), which opens the issue form template in `.github/ISSUE_TEMPLATE/crew-log.yml`.
- The `.github/workflows/comms-interaction.yml` workflow automatically sanitizes the transmission (strips HTML/links, enforces character limits), prepends it between `<!-- CREW_LOG_START -->` and `<!-- CREW_LOG_END -->` (keeping the latest 5 entries with UTC date), posts a confirmation comment, and closes the issue.

### Intercepted Signal Puzzle
- Visitors decode the Caesar-shifted and Base64-encoded transmission `RFJRUkhYRFVHQg==` (solution: `ANDROGUARD`).
- Solvers submit their answer via `.github/ISSUE_TEMPLATE/signal-decode.yml`.
- The workflow verifies the checksum, replies "Access granted. Welcome aboard.", and appends their handle to the `<!-- DECODED_BY_START -->` roster.

### Daily Transmission
- Powered by `.github/workflows/daily-transmission.yml`, which cycles through 40 original security/engineering one-liners stored in `data/transmissions.json` every 24 hours, updates `assets/transmission.svg`, and refreshes the UTC timestamp.
