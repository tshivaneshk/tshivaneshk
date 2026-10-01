# Implementation Plan: Mission Control Profile Redesign

## 1. Audit & Inventory
### Kept
- Core identity: T Shivanesh Kumar
- Real technical domains: Cybersecurity Engineer, Android Developer, ML and Full Stack learner, Open Source Contributor.
- Accurate real-world projects:
  - Android Security & Forensics (desktop ADB tool, static/dynamic inspection)
  - Wolfsniff (Hybrid Network IDS, native C + Random Forest on UNSW-NB15, MITRE ATT&CK)
  - AlphaStick-Android (Modular Android vulnerability auditor in Kotlin / Jetpack Compose)
  - Upstream contributions: Androguard/apk-parser PR #8 (preview codename fix) and OWASP/wstg PR #1543 (XSSI modernizing)
- Real tech stack: Python, Kotlin, C, C++, TypeScript, JavaScript, HTML, CSS, Android Studio, Linux, Bash, Git, GitHub, Scikit-learn, Wireshark.
- Core URLs: Portfolio (Vercel), LinkedIn, GitHub profile.

### Replaced
- Old space header & old divider -> replaced by self-contained animated SVGs:
  - `assets/hero.svg`: Spacecraft Mission Control / launch sequence starfield with twinkling stars, orbiting planetary bodies, and title reveal.
  - `assets/tagline.svg`: Self-contained SMIL typing SVG rotating through emoji-free titles.
  - `assets/divider.svg`: Clean telemetry orbit signal wave divider.
  - `assets/terminal.svg`: Interactive-looking terminal window looping real `whoami`, `cat focus.txt`, `ls projects/` commands.
  - `assets/cards-row1.svg` & `assets/cards-row2.svg`: Modern 3D spacecraft telemetry module cards (no emojis, subtle scans, hover-free glow, fully link-wrapped).
  - `assets/orbit.svg`: Planetary multi-ring orbit visualization with core and orbiting tech nodes.
- Snake workflow (`snake.yml`) -> replaced by comprehensive workflows generating 3D isometric city calendar (`github-profile-3d-contrib`), Pacman contribution arcade, metrics/stats, crew log updater, and auto-updated timestamp.

### Removed
- All emojis from all files, SVGs, workflows, issue templates, and README.
- Unreliable external Herokuapp streak dependency in primary flow (replaced with resilient action-generated artifacts and robust fallbacks).

---

## 2. Directory & File Plan
```
tshivaneshk/
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   └── crew-log.yml              # Issue template for visitor log
│   └── workflows/
│       ├── contributions.yml          # 3D city + Pacman contribution graph -> output branch
│       ├── crew-log.yml               # Automated issue-to-README logger with sanitization
│       └── update-timestamp.yml       # Periodic mission timekeeper
├── assets/
│   ├── hero.svg                      # Animated mission control starfield & launch
│   ├── tagline.svg                   # Self-contained SMIL typing animation (no emojis)
│   ├── terminal.svg                  # Animated spacecraft console / whoami terminal
│   ├── divider.svg                   # Animated orbital wave divider
│   ├── cards-row1.svg                # 3D modules: Android Forensics & Wolfsniff
│   ├── cards-row2.svg                # 3D modules: AlphaStick & Upstream Contributions
│   └── orbit.svg                     # 3-ring orbiting tech node galaxy
├── README.md                         # Mission Control developer portfolio
└── SETUP.md                          # Clear manual GitHub configuration instructions
```
