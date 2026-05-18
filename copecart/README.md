# CopeCart — High-Ticket Vendor Audit

60-second revenue-gap diagnostic for digital product vendors.
Four inputs (revenue, AOV, payment methods, tax setup) → one number split into
checkout-gap and compliance-drag → optional lead gate → 30-min strategy call.

## Purpose

Partnership-building asset for Florian's relationship with Stefan Wurl
(CopeCart concept & strategy). Built in CopeCart's visual language so Stefan
can immediately picture it inside the brand. Florian stays invisible — this
reads as a CopeCart asset, not an FL Digital lead magnet.

## What it is

- Single-file HTML, vanilla JS, no build step
- CopeCart-inspired design: lavender-blue gradient background, white rounded
  cards, pill buttons, Inter typography, soft shadows
- 60-second engagement target
- Lead gate is **optional** — number reveals before any email is collected
- Webhook-tagged `copecart-vendor-audit` for separate routing

## Structure

```
copecart/
├── index.html      Single-page tool
├── assets/         Brand assets (drop logo here when official approval given)
├── README.md       This file
└── CLAUDE.md       Project context for future Claude sessions
```

## Local test

```bash
cd copecart
python3 -m http.server 8000
# Browser: http://localhost:8000
```

## Before sending to Stefan

- [ ] Replace `CALENDLY` placeholder with Stefan's real slot
- [ ] (Optional) Drop official CopeCart SVG logo into `assets/` and swap the
      CSS-built brand mark in the header
- [ ] Have Stefan review the multipliers in `index.html`
      (`paymentGapPct`, `aovFactor`, tax-cost constants)
- [ ] Decide hosting: `audit.copecart.com` subdomain vs subpath on FL's repo

## Tech

| Aspect | Value |
|---|---|
| Stack | Single HTML, vanilla JS, Google Fonts (Inter, JetBrains Mono) |
| Hosting | TBD: subdomain on copecart.com or subpath on github pages |
| Webhook | `https://hook.eu1.make.com/1npebtm7jcj283enhqvmulnfxcnkhm47` (shared, tag-filtered) |
| Source tag | `copecart-vendor-audit` |
| URL params | `?name=Foo&company=Bar` pre-fills lead gate |
