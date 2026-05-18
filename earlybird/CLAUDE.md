# earlybird × FL Digital — Founder GTM Check

Projekt-Kontext für Claude. Wird automatisch geladen, wenn an `/Users/florianlapiz/Documents/gtm/earlybird/` gearbeitet wird.

## 1. Was ist das Asset?

Interaktiver 3-Minuten-Selbstcheck für B2B-Founder zwischen Seed und Series A.
7 Fragen → Score 0–14 → Phase-Tier → 3 Strategic Plays → kostenloses Sparring-Sprechen.

**Datei**: `index.html` (single-file, GitHub-Pages-deploybar)
**Hosting**: `florianlapiz.github.io/gtm/earlybird/`
**Sprache**: Englisch (earlybird ist international)
**Tonalität**: Founder-natürlich, Du-Form, kein B2B-Jargon

## 2. Strategischer Kontext (wichtig)

**Auslöser**: Setter-/Discovery-Call mit Jay Anna Harris-Theis (Portfolio Excellence, earlybird).
Florian wurde von earlybird qualifiziert auf Empfehlung von Partner H. Brandis als
möglicher Mentor im Portfolio-Excellence-Programm.

**Strategische Säule**: Dieses Asset bedient die in der FL-Digital-CLAUDE.md beschriebene
Säule **"VC-Portfolio-Advisory"** (5–15 % Zielumsatz, Status "in Vorbereitung").

**Positionierung**: Florian ist hier **nicht im Sales-Modus**, sondern qualifiziert sich als
Mentor im earlybird-Netzwerk. Das Asset ist die Value-First-Geste, kein Pitch.

**Erwarteter Hebel**: Über earlybird Zugang zu ~30 Portfolio-Foundern → 2–3 davon als
echte Retainer = solides Standbein in der Advisory-Säule.

## 3. Was es NICHT ist

- **Kein Massen-Leadmagnet**: Nicht öffentlich verlinkt, kein Index-bait
- **Kein E-Mail-Gate**: Founder gibt KEINE Lead-Daten ab vor Result. Friction zerstört Trust.
- **Kein Tool-Pitch**: Plays am Ende sind Operator-Moves, keine Template-Links
- **Kein Sales-Funnel**: Calendly-Buchung ist der einzige Lead-Touchpoint, freiwillig

## 4. Technische Specs

| Aspekt | Wert |
|---|---|
| Stack | Single HTML, vanilla JS, Google Fonts |
| Hosting | GitHub Pages |
| Lead-Webhook | `https://hook.eu1.make.com/1npebtm7jcj283enhqvmulnfxcnkhm47` (anonymes Score-Tracking) |
| Source-Tag im Payload | `earlybird-founder-check` |
| Calendly | `https://calendly.com/florian-lapiz/diagnose` (TODO: eigener earlybird-Slot) |
| URL-Params | Optional `?founder=Marc&company=Hive` für Personalisierung |

## 5. Design-System (earlybird-aligned)

### Farbpalette
- Background: `#1A0F0D` (warm dunkles Braun, NICHT pure black)
- Akzent: `#FF1A1A` (earlybird-Rot)
- Atmosphäre: Pink/Purple/Blue Gradient unten (matches earlybird hero)
- Text: White auf dunkel

### Typografie
- **Logo "earlybird"**: Alfa Slab One (Google Font, free) — kommt der echten earlybird-Wortmarke optisch sehr nah, rechtlich sauber. Färbung in `#FF1A1A`.
- **Headlines/Display**: Anton (condensed, bold, ALL CAPS — "Druk"-like)
- **Body**: Inter
- **Mono**: JetBrains Mono

### Visueller Stil
- Editorial / brutalist / dramatic (kein "clean tech")
- Scharfe Corners (2–4px), nicht rund
- Großzügige Display-Headlines im ALL-CAPS
- Co-Branding-Header: `earlybird × FL DIGITAL`

## 6. Die 7 Hebel

Founder-conversational, keine Sales-Jargon. Score 0–2 pro Hebel.

| # | Hebel | Frage | Beste Antwort = |
|---|---|---|---|
| 1 | Customer Insight | Do you know exactly why your best customers chose you? | C |
| 2 | Sales Independence | Could your team close a deal without you in the room? | B |
| 3 | Win Concentration | Look at your last 20 won deals. How similar are they? | A |
| 4 | Pipeline Visibility | Could you name the next 5 deals that will close — and why? | B |
| 5 | Buy-Now Triggers | Do you know what makes a customer buy now vs. later? | C |
| 6 | Funnel Truth | Do you know where deals actually die in your sales process? | A |
| 7 | Operating Resilience | If you took 2 weeks completely off, what would happen to pipeline? | B |

**Best-Antwort-Verteilung**: C/B/A/B/C/A/B — gleichmäßig gestreut, kein Pattern erkennbar.

### UI-Marker
Optionen werden als **A/B/C** angezeigt (nicht 0/1/2), damit die Score-Logik nicht sichtbar wird.

## 7. Tier-System

| Score | Tier | Bedeutung |
|---|---|---|
| 0–5 | Foundation Phase | Founder-led mode, biggest unlock: system over person |
| 6–9 | Scaling Tension | System trägt noch nicht, Founder muss raus. 2–3 Hebel entscheiden über die nächsten 6 Monate. |
| 10–14 | Scale-Ready | Top tier. Vertical expansion + ROI multiplier statt mehr Inputs. |

## 8. Strategic Plays (statt Tools)

Bewusste Designentscheidung: Auf der Result-Seite **keine Template-Links**, sondern
**konkrete Operator-Moves** mit Begründung und Zeitfenster.

Begründung: Templates sind vage Versprechen. Plays beweisen Operator-DNA und sind
sofort umsetzbar. Ein Founder, der den "Founder Mute Test" liest, denkt sofort
"okay, der hat das schon mal selbst gemacht" — das ist die Authority-Geste.

Format pro Play:
- **Kind** (z.B. "Customer Move", "Founder Move", "Strategy Move")
- **Title** (kurzer einprägsamer Name)
- **Description** (das echte Operator-Insight + Anti-Naiv-Warnung)
- **Pill** (Zeitfenster, z.B. "→ This week · 5 calls")

Die jeweils 3 schwächsten Hebel werden als Plays gezeigt. Top-Play wird visuell hervorgehoben.

## 9. Antwort-Reihenfolge (Anti-Gaming)

Reihenfolge pro Frage **fest definiert** (kein Random-Shuffle, damit Verhalten reproduzierbar bleibt):

| Frage | Options-Reihenfolge (Score) |
|---|---|
| 1 | [1, 0, 2] |
| 2 | [0, 2, 1] |
| 3 | [2, 1, 0] |
| 4 | [1, 2, 0] |
| 5 | [0, 1, 2] |
| 6 | [2, 0, 1] |
| 7 | [0, 2, 1] |

## 10. Status & offene Punkte

### Gemacht
- [x] Design im earlybird Look & Feel (dark warm, red, Anton + Alfa Slab One)
- [x] 7 founder-natürliche Fragen (kein Jargon)
- [x] Score → Tier → Plays-Logik
- [x] Webhook für anonymes Score-Tracking (Make.com)
- [x] URL-Param-Personalisierung (`?founder=X&company=Y`)
- [x] Co-Branding-Header earlybird × FL DIGITAL
- [x] Strategic Plays statt Template-Links
- [x] Exklusivitäts-Framing im Hero

### Offen vor erstem Versand
- [ ] **Calendly-Slot**: Eigene URL für earlybird-Portfolio anlegen (z.B. `calendly.com/florian-lapiz/earlybird-portfolio`)
- [ ] **Logo-Variante**: Mit Jay klären, ob offizielles earlybird-Logo-SVG genutzt werden darf. Aktuell Alfa Slab One als rechtlich saubere Approximation.
- [ ] **Avatar-Pfad prüfen**: `../assets/florian-portrait.png` zeigt auf gtm-Repo-Root, muss bei separatem Deploy adjustiert werden
- [ ] **Test im Browser**: Alle 7 Fragen durchklicken, Score-Verteilung in 3 Szenarien checken
- [ ] **Robots-Meta**: Optional `<meta name="robots" content="noindex,nofollow">` einbauen für echte Exklusivität

### Nach Jay-Call
- [ ] Co-Branding-Approval einholen oder Asset neutral umlabeln
- [ ] Falls Approval: Original earlybird-Logo-SVG einbauen
- [ ] URL-Param-Personalisierung an Jay erklären, damit sie die Links pro Founder customizen kann

## 11. Call-Strategie mit Jay

Asset wird **VOR** dem Call per Mail geschickt, mit folgender Framing:

> "Hi Jay, freu mich auf den Austausch. Damit wir nicht abstrakt reden — ich hab Dir
> ein konkretes Asset gebaut, das ich exklusiv für earlybird-Portfolio konzipiert habe
> (kein Massen-Leadmagnet, keine öffentliche Verlinkung). 3-Minuten-Check für Eure
> Seed/Series-A-Founder mit Score, drei Operator-Plays und kostenlosem Sparring-Slot.
> Schau gerne mal rein: [Link]. Im Call können wir besprechen, ob/wie das ins
> Portfolio-Excellence-Programm passt."

**Im Call**:
- Nicht pitchen
- Als Mentor qualifizieren, nicht als Service-Dienstleister
- Fragen zu earlybirds Portfolio-Excellence-Format stellen (1:1, Workshops, Office Hours?)
- 2–3 konkrete Operator-Cases parat haben (NEOLIMS, Impuls, DGS — messbar)
- DACH-Fokus ehrlich addressieren (Methodik global, Schwerpunkt DACH)

## 12. Anti-Patterns für dieses Asset

Wenn ich beim Weiterbauen in diese Muster verfalle, muss ich gestoppt werden:

- **Lead-Magnet-Logik schleicht zurück**: E-Mail-Gate, "noch eine Mail mit Templates" — NEIN. Bleibt anonym + Calendly = einziger Lead-Touchpoint.
- **Tool-Drift**: Plays werden wieder zu "klick zu meinem Notion" — NEIN. Plays sind Operator-Moves, keine Tools.
- **Jargon-Drift**: "Pipeline-Velocity-Optimization", "Funnel-Conversion-Engineering" — NEIN. Founder-natural English bleibt.
- **Massentauglichkeit**: "Damit es auch für Nicht-Portfolio-Founder funktioniert..." — NEIN. Exklusivität ist der Hebel.
- **Über-Personalisierung**: Branchen-spezifische Varianten für DeepTech/Health/Fintech — NEIN. Asset bleibt B2B Sales-led generisch. Differenzierung passiert im Sparring-Call, nicht im Quiz.

## 13. Referenzen

- Original Pipeline-Generator (Vorlage): `../index.html` (florianlapiz.github.io/gtm/)
- earlybird Website (Design-Referenz): https://earlybird.com
- Globale FL-Digital-Kontext: `/Users/florianlapiz/Documents/cc-gtm-flo/CLAUDE.md`
