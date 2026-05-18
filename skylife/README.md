# Sky Life Agency — Creator Marketing ROI Check

Foot-in-the-door diagnostic for brand marketers running creator campaigns.
3 inputs (monthly spend, amplification stance, cadence) → 1 number ("$X/year left on the table") → optional lead gate → 30-min call with Bano Diop.

## What it is

- Single-file HTML, vanilla JS, no build step
- Black & white editorial design, Inter + Anton + JetBrains Mono
- 60-second engagement target
- Lead gate is **optional** (number reveals before any email is collected)
- Webhook-tagged `skylife-creator-roi` for separate routing

## Structure

```
skylife/
├── index.html      Single-page tool
├── assets/         Brand assets (logo, portraits — drop here)
├── README.md       This file
└── CLAUDE.md       Project context for future Claude sessions
```

## Local test

```bash
cd skylife
python3 -m http.server 8000
# Browser: http://localhost:8000
```

## Before sending to Bano

- [ ] Replace `CALENDLY` placeholder in `index.html` with Bano's real slot
- [ ] Drop Sky Life Agency logo (SVG preferred) into `assets/` and swap the text lockup
- [ ] (Optional) Replace Make.com webhook with a dedicated Sky Life endpoint
- [ ] Have Bano review the calculation multipliers in `index.html` (search for `whitelistMult` / `cadenceMult`)

## Tech

| Aspect | Value |
|---|---|
| Stack | Single HTML, vanilla JS, Google Fonts |
| Hosting | Subfolder or own subdomain (e.g. `roi.skylifeagency.com`) |
| Webhook | `https://hook.eu1.make.com/1npebtm7jcj283enhqvmulnfxcnkhm47` (shared, tag-filtered) |
| Source tag | `skylife-creator-roi` |
| URL params | `?name=Foo&company=Bar` pre-fills the lead form |
