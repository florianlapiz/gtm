# eBrain — Event-Automatisierungs-Check

Projekt-Kontext für Claude. Wird automatisch geladen, wenn an `/ebrain/` gearbeitet wird.

## 1. Was ist das Asset?

Interaktiver 3-Minuten-Selbsttest für Eventmanager, Agenturen und Inhouse-Eventteams.
8 Fragen → 3 Sub-Scores (Admin-Zeit, Kosten, Teilnehmer-Erlebnis) → Gesamt-Score 0–100 →
Tier-Einordnung → 3 schwächste Hebel mit eBrain-Modul-Mapping → 14-Tage-Trial + Demo-CTA.

**Datei**: `index.html` (single-file, GitHub-Pages-deploybar)
**Hosting**: `florianlapiz.github.io/gtm/ebrain/`
**Sprache**: Deutsch, Du-Form
**Tonalität**: Pragmatisch-operativ, Eventmanager-Sprache, kein KI-Hype

## 2. Strategischer Kontext

**Zweck**: Klassischer Lead-Magnet. E-Mail-gated. Output ist ein qualifizierter Lead inkl.
Score-Profil, das in CRM/Make-Pipeline läuft.

**Florians Rolle bei eBrain**: Co-Founder / Marketing & Growth. Das Asset ist
**kein externes Sales-Vehikel**, sondern ein **Inhouse-Lead-Asset für eBrain selbst**.
Kein FL-Digital-Branding, reines eBrain-Look-&-Feel.

**Zielgruppe**:
- Eventagenturen (Margin-Wachstum)
- Inhouse-Eventmanager bei Enterprises (Kostenoptimierung)
- Event-Dienstleister (Skalierung)

**Conversion-Ziel**: Primär 14-Tage-Trial-Signup. Sekundär: Demo-Buchung via Calendly.

## 3. Was es NICHT ist

- **Kein Massen-Awareness-Tool**: Bewusst gated, Lead-Daten als Pflicht.
- **Kein FL-Digital-Asset**: Florian taucht hier nicht als Operator auf, das ist ein eBrain-Produkt-Asset.
- **Kein Feature-Dump**: Module werden nur als Lösung zu konkreten Pain-Points der drei schwächsten Hebel gezeigt, nicht als Liste.
- **Kein Sales-Pitch**: Trial-CTA ist primär, Demo nur als Alternative für "lieber sprechen".

## 4. Technische Specs

| Aspekt | Wert |
|---|---|
| Stack | Single HTML, vanilla JS, Google Fonts |
| Hosting | GitHub Pages |
| Lead-Webhook | `LEAD_WEBHOOK_URL` — **TODO**: Make.com-Slot eintragen |
| Trial-URL | `TRIAL_URL` — **TODO**: echter eBrain-Trial-Link |
| Demo-URL | `DEMO_URL` — **TODO**: echter Calendly-Slot |
| Source-Tag im Payload | `ebrain-automation-check` |
| URL-Params | Optional `?firstname=X&company=Y` für Pre-fill |
| UTM | CTAs hängen automatisch UTM-Parameter und Lead-Daten an |

## 5. Design-System (eBrain-aligned)

### Farbpalette
- Background: `#FFFFFF` (hell, clean SaaS — auf Wunsch von Florian on-brand)
- Soft-BG / Surface: `#F7F7FA`
- Primary: `#712EE5` (eBrain-Violett, alle CTAs, Headlines-Accents)
- Signal/Accent: `#DCE43E` (Lemon Green, Pulse-Dot, Trial-CTA, Highlight-Glow)
- Diagnose-Block (dark editorial moment): `#0E0B1F` Gradient mit Lemon-Glow

### Typografie
- **Display/Headlines**: Space Grotesk 700 (modern, geometrisch, on-brand SaaS)
- **Body**: Inter
- **Mono / Counter**: JetBrains Mono
- Logo: Wordmark "eBrain" mit violettem "e" als Platzhalter — sobald Florian das offizielle SVG liefert, wird `.brand-logo` durch `.brand-logo-img` ersetzt (CSS-Klasse existiert bereits)

### Visueller Stil
- Modern SaaS hell, kein editorial-brutalism wie Early Bird
- Großzügige Display-Headlines, Violet-Accent, Lemon als Energy-Punkt
- Sub-Score-Cards mit ampelfarbiger Meter (rot/orange/grün je nach Wert)
- 1 dramatischer dunkler Block (`.diagnosis`) als visuelles Highlight im Result

## 6. Die 8 Hebel

Jeder Hebel mapped 1:1 auf ein eBrain-Modul. Score 0/1/2 pro Antwort.

| # | Hebel | Dimension(en) | eBrain-Modul |
|---|---|---|---|
| 1 | Event-Setup | Admin | KI-Website-Erstellung |
| 2 | Registrierung | Admin | Teilnehmerregistrierung |
| 3 | Kommunikation | Admin | Communication Center |
| 4 | Tool-Stack | Kosten | All-in-One Suite (Reporting + Ticketing) |
| 5 | Kontingente | Kosten | Kontingent-Management |
| 6 | Teilnehmer-Support | Erlebnis | Emily-Chatbot |
| 7 | Check-in & Badges | Erlebnis | Badge & Check-in |
| 8 | Daten & Entscheidungen | Kosten + Erlebnis | Predictive Forecasting |

### Score-Verteilung pro Dimension
- **Admin-Zeit**: Q1+Q2+Q3 → max 6 Punkte → skaliert 0–100
- **Kosten**: Q4+Q5+Q8 → max 6 Punkte → skaliert 0–100
- **Erlebnis**: Q6+Q7+Q8 → max 6 Punkte → skaliert 0–100 (Q8 zählt doppelt)
- **Gesamt**: Mittelwert der drei Sub-Scores

### Option-Reihenfolge (Anti-Gaming)
Reihenfolge pro Frage fest, sodass die beste Antwort wechselt: B/C/A/C/A/C/C/C.

## 7. Tier-System (Gesamt-Score)

| Score | Tier | Badge-Farbe |
|---|---|---|
| 0–30 | Manueller Modus | Rot |
| 31–60 | Halb-digital | Amber |
| 61–100 | Digital reif | Grün |

Sub-Scores verwenden die gleichen Schwellen (≤33 rot, ≤66 amber, sonst grün) und färben Meter + Zahl entsprechend.

## 8. Modul-Mapping (Result)

Die **3 schwächsten Hebel** werden auf der Result-Seite als nummerierte Karten gezeigt (01/02/03), Top-Hebel ist visuell hervorgehoben (`.highlighted`).

Pro Karte:
- **Kind** (z.B. "Setup-Hebel", "Kosten-Hebel", "Erlebnis-Hebel")
- **Title** (Hebel-Name)
- **Pain** (was Du aktuell verlierst, in Klartext)
- **Solution** (was eBrain konkret tut, mit gefettetem Modul)
- **Module Tag** (Pill mit eBrain-Modulnamen)

## 9. Lead-Gate

Position: **zwischen Frage 8 und Result**.

| Feld | Pflicht? |
|---|---|
| Vorname | ✓ |
| Firma | ✓ |
| E-Mail (geschäftlich) | ✓ (Regex-Validation) |
| Rolle | optional, Dropdown |

Pre-fill via URL-Params `?firstname=X&company=Y` möglich.

## 10. Status & offene Punkte

### Gemacht
- [x] Design im eBrain Look (hell, Violett primary, Lemon Akzent)
- [x] 8 pragmatisch-operative Fragen für Eventmanager
- [x] Drei-Achsen-Score (Admin/Kosten/Erlebnis) + Gesamt-Score
- [x] E-Mail-Gate mit Validation
- [x] Modul-Mapping auf eBrain-Features
- [x] Trial- + Demo-CTA-Stack
- [x] Webhook-Hook (URL noch TODO)
- [x] URL-Param-Pre-fill
- [x] Dramatische Diagnose-Section (dunkel, on-brand mit Lemon-Glow)
- [x] Mobile-Responsive

### Vor Go-Live
- [ ] **Logo**: Florian liefert eBrain-SVG/PNG → `ebrain/assets/logo.svg` ablegen, im `.brand-lockup` Text durch `<img class="brand-logo-img">` ersetzen
- [ ] **LEAD_WEBHOOK_URL**: Make.com-Slot anlegen, in JS-Konstante einsetzen
- [ ] **TRIAL_URL**: Echter eBrain-Trial-Link (Self-Service-Signup oder Funnel-URL)
- [ ] **DEMO_URL**: Calendly-Slot mit dem eBrain-Team
- [ ] **Test im Browser**: Alle 8 Fragen durchklicken, drei Szenarien (low/mid/high Score) prüfen
- [ ] **Datenschutz**: Link/Hinweis auf Datenschutzerklärung im Gate ergänzen (rechtlich für gated Lead-Capture)
- [ ] **Robots-Meta**: Entscheidung — indexieren (Lead-Magnet → ja) oder nicht (eher ja, weil Pipeline-Asset)

### Nachgelagert (Phase 2)
- [ ] Mehrsprachigkeit: EN-Variante via Toggle (eBrain-Site hat DE/EN)
- [ ] A/B-Test: Trial-CTA vs. Demo-CTA als primärer Hebel
- [ ] Branchen-Varianten: Agentur vs. Inhouse vs. Dienstleister mit angepassten Fragen
- [ ] Score-Benchmarking: "Du gehörst zu den oberen 30% der Eventmanager" (braucht aggregierte Daten)

## 11. Anti-Patterns für dieses Asset

- **Feature-Listen-Drift**: Result wird zu einer Liste aller 9 Module → NEIN. Nur die 3 schwächsten Hebel werden zu Modulen gemappt, der Rest taucht im Breakdown auf.
- **KI-Hype-Sprache**: "Revolutioniere", "Game-Changer", "Disruption" → NEIN. Pragmatisch bleiben: "Stunden zurückgewinnen", "Schlangen vermeiden", "Daten in Echtzeit".
- **Massen-Newsletter-Geste**: "Hol Dir den Report + 7 Bonus-PDFs" → NEIN. Lead-Magnet liefert genau das, was er verspricht: Score + Empfehlungen + Trial-Hook.
- **Pseudo-Personalisierung**: Branchen-spezifische Varianten als Phase 1 → NEIN. Erst Daten sammeln, dann differenzieren.
- **Sales-Drift**: Demo-CTA wandert nach oben, Trial wandert weg → NEIN. Self-Service-Trial ist der primäre Conversion-Hebel, weil schneller und skalierbarer.

## 12. Referenzen

- Schwester-Asset (Struktur-Vorlage): `../earlybird/index.html`
- eBrain Website: https://ebrain.events
- Hosting: GitHub Pages, gemeinsam mit dem GTM-Repo
