# GTM-Audit Quiz

Interaktives 6-Hebel-Audit für B2B-Mittelständler im DACH-Raum. Nutzer beantworten 6 Fragen zu ihrem Go-to-Market-Setup, tragen sich nach Frage 6 ein und bekommen ihren Score plus Hebel-Klasse.

**Live:** [florianlapiz.github.io/gtm/](https://florianlapiz.github.io/gtm/) (sobald GitHub Pages aktiviert ist)

## Tech

- Standalone HTML, vanilla JS, keine Build-Schritte
- Inter + JetBrains Mono via Google Fonts
- Lead-Capture per POST an Make.com Webhook

## Struktur

```
.
├── index.html           Single-Page Quiz mit allen Screens
├── assets/
│   └── florian-portrait.png
└── README.md
```

## Lokal testen

```bash
cd gtm
python3 -m http.server 8000
# Browser: http://localhost:8000
```

## GitHub Pages aktivieren

Settings → Pages → Source: `main` branch, `/` (root) → Save.

## Lead-Flow

Quiz-Submit → Make-Webhook → Google Sheet plus HubSpot-Contact-Property `gtm_audit_score`.

---

GTM FLO · GTM Engineering Consultancy für den deutschen Mittelstand
