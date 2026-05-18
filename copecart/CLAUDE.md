# CopeCart — High-Ticket Vendor Audit

Project context for Claude. Loaded automatically when working in `/Users/florianlapiz/Documents/gtm/copecart/`.

## 1. What this asset is

A 60-second foot-in-the-door diagnostic for **digital product vendors scaling past €10k/month**.
Built as a partnership-builder for Florian's relationship with **Stefan Wurl**, who is involved
in CopeCart's concept and strategic development.

**Format**: 4 inputs (revenue, AOV, payment methods, tax setup) → 1 total + breakdown into
checkout-gap and compliance-drag → optional lead gate → CTA to strategy call.
**Language**: English (CopeCart is international: 530k+ vendors, multi-region).
**Tonality**: Direct, operator-to-operator, no marketing fluff.

## 2. Strategic context

**Trigger**: Florian met Stefan in person and had ~30 min conversation about his background and
career path. Stefan gave him his personal WhatsApp. This is a warm relationship-builder asset,
not a cold sales tool.

**Florian's positioning**: Background advisor / behind-the-scenes consultant.
He does NOT appear in the asset branding. The tool reads as a CopeCart asset.
Florian gets credit via the personal channel (WhatsApp message accompanying the link).

**CopeCart's USPs that this tool surfaces** (taken directly from their website):
- High-ticket + high-margin focus
- Payments + BNPL (97% approval rate) → Q3 in the audit
- Tax Compliance / Vendor-of-Record → Q4 in the audit
- 9 payment methods including crypto → Q3 advanced option
- "All-in-one to skip the bureaucracy" → exactly what the diagnosis surfaces

The tool diagnoses the two gaps that CopeCart explicitly solves: checkout friction and
compliance overhead. By the time a vendor sees the result, they're already primed to think
"I need a platform that handles both" — which is CopeCart's pitch.

## 3. What it is NOT

- Not a generic platform-comparison quiz. It's CopeCart-aligned by surfacing the gaps CopeCart
  closes, without naming competitors directly.
- Not a Florian lead magnet — branding is CopeCart only.
- Not a precise calculator — directional estimate. Methodology disclosed in expand.
- Not narrowly targeted at one platform's users. Generic enough to work on any vendor stack.

## 4. Tech specs

| Aspect | Value |
|---|---|
| Stack | Single HTML, vanilla JS, Google Fonts (Inter, JetBrains Mono) |
| Hosting | TBD: subdomain `audit.copecart.com` or GitHub Pages subpath |
| Webhook | `https://hook.eu1.make.com/1npebtm7jcj283enhqvmulnfxcnkhm47` (shared, tag `copecart-vendor-audit`) |
| Calendly | Placeholder `https://calendly.com/stefan-wurl/strategy` — TODO real slot |
| URL params | `?name=Foo&company=Bar` pre-fills lead gate |

## 5. Design system

### Palette (lifted from copecart.com)
- Background: lavender-blue gradient `#E8EBF7 → #DDE3F4 → #E5E9F4`
- Surface: pure white `#FFFFFF` with subtle blue-tint variants
- Borders: soft `#E2E7F2`
- Text: deep navy-ink `#0F1535`
- Accent: bright blue gradient `#5990FF → #3D7BFF → #2B5FE0`
- Soft accent: `rgba(61, 123, 255, 0.08)` for hover/selected states

### Typography
- **Inter**: everything. 900 (display), 700/600 (UI), 500/400 (body)
- **JetBrains Mono**: numerical labels, step markers, technical micro-copy

### Visual language
- Pill-shaped buttons and badges (border-radius: 100px) — matches CopeCart hero buttons
- Cards with generous border-radius (24px) — matches CopeCart feature cards
- Soft layered shadows (no harsh borders)
- Gradient highlights on key words ("checkout & compliance", "digital revenue") via background-clip
- Glassy topbar with `backdrop-filter: blur` + saturation
- Result card inverts to dark ink with blue glow gradients

## 6. The 4 inputs

| # | Question | Type | Multipliers |
|---|---|---|---|
| 01 | Monthly digital revenue | Slider €1k–€500k, step €1k | linear base |
| 02 | Average Order Value | Slider €50–€5000, step €10 | aovFactor 0.5/1.0/1.5/2.0 |
| 03 | Payment methods at checkout | Radio: standard / extended / bnpl / full | gap% 0.20/0.10/0.04/0.02 |
| 04 | Tax & VAT setup | Radio: diy / outsourced / vor / de_only | annual cost €18k/€6k/€0/€600 |

### Formula
```
annualRevenue = monthly_k * 1000 * 12
aovFactor: <100 = 0.5 | <500 = 1.0 | <1500 = 1.5 | else = 2.0
paymentGapAnnual = annualRevenue * paymentGapPct * aovFactor (capped at 120% of annual)
taxAnnual = fixed mapping by tax option
total = paymentGapAnnual + taxAnnual
total clamped to [annualRevenue * 0.04, annualRevenue * 1.5]
```

### Anchor reasoning
- Cart-abandonment by payment-method coverage: Baymard Institute data — 20% abandonment baseline drops with each major method added
- BNPL impact on high-ticket: Klarna case studies show 30%+ uplift on >€500 AOV → aovFactor 1.5 for that range
- DIY tax setup cost: ~10–15h/month founder time × €80–€150 opportunity cost + Steuerberater retainer = ~€18k/year
- Vendor-of-Record removes the entire compliance layer (CopeCart positioning)

## 7. Lead gate logic

- Number reveals with **no email gate** — foot-in-the-door = immediate value
- Gate appears only on CTA "Show Me The Plan →"
- Fields: name, work email, company, **current platform**, **business stage**
- Platform field is a qualifier: vendors on Digistore24/elopage/Hotmart are highest-value migration leads for CopeCart
- Business-stage field filters by revenue tier

## 8. Webhook payload shape

Stage 1 — anonymous reveal (no PII):
```json
{
  "source": "copecart-vendor-audit",
  "timestamp": "2026-05-18T...",
  "stage": "reveal",
  "revenue_monthly_k": 50,
  "aov_eur": 800,
  "payment": "standard",
  "tax": "diy",
  "total_gap": 186000,
  "payment_gap": 180000,
  "tax_cost": 18000
}
```

Stage 2 — lead: same plus `name`, `email`, `company`, `platform`, `business_stage`, `stage: "lead"`.

## 9. Open items before sending to Stefan

- [ ] Real Calendly slot from Stefan (placeholder is `calendly.com/stefan-wurl/strategy`)
- [ ] Official CopeCart logo SVG → swap the CSS-built brand mark
- [ ] Have Stefan review multipliers — they should match CopeCart's internal benchmarks
- [ ] Decide hosting: subdomain on copecart.com vs FL's GitHub Pages
- [ ] Robots meta: currently `noindex,nofollow` — keep until Stefan greenlights

## 10. Anti-patterns

If I drift into these while iterating, stop me:

- **Naming competitors directly in result-screen copy** — "Digistore24 is bad" is a no-go. Frame all gaps as platform-agnostic.
- **Florian-branding creep** — no "by Florian", no FL Digital logo, no portrait. Florian's name appears only in the WhatsApp message that delivers the link.
- **Adding more questions** — 4 is already at the upper limit for foot-in-the-door. Friction kills.
- **Precision claims** — always "estimated" / "directional" with methodology disclosure.
- **Gating the number** — reveal is free, gate is for the breakdown + call only.
- **Over-claiming on tax** — €18k DIY cost is an upper-bound estimate. Don't write "you're losing €18k", write "average DIY setup carries ~€18k/year in time + advisor cost."

## 11. Outreach context (Stefan)

**Personal context Florian has**: They met in person, had ~30 min conversation covering Stefan's
career and background. So the WhatsApp opener can reference that specific conversation without
being generic.

**Channel**: Personal WhatsApp (Stefan gave the number directly).

**Recommended outreach (analog to Bano/SkyLife play)**:
- 30–45 sec voice message referencing the 30-min conversation, surfacing the strategic observation
  (CopeCart's two real moats are payments+BNPL and tax compliance — exactly what most vendors
  underestimate)
- Link as text follow-up
- No pitch, no ask for a call, just "schau drauf, sag mir was hängen bleibt"

## 12. References

- CopeCart website: https://copecart.com
- Sibling assets: `../skylife/` (Bano Diop), `../earlybird/` (Jay/earlybird VC)
- Stefan Wurl: involved in CopeCart concept & development (per Florian's intro)
