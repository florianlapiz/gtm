# Sky Life Agency — Creator Marketing ROI Check

Project context for Claude. Loaded automatically when working in `/Users/florianlapiz/Documents/gtm/skylife/`.

## 1. What this asset is

A 60-second foot-in-the-door diagnostic for **brand marketers running creator campaigns**.
Built as a value-first asset for Florian to deepen the partnership with **Bano Diop, Founder of Sky Life Agency**.

**Format**: 3 inputs → 1 number (annual unrealized revenue estimate) → optional lead gate → CTA to call with Bano.
**Language**: English (Sky Life is international: Hamburg + Beverly Hills, clients incl. Twitch, Warner Bros, Amazon Prime, Stake).
**Tonality**: Direct, no marketing fluff, operator-to-operator.

## 2. Strategic context

**Trigger**: Florian is well connected with Bano and wants to deepen the partnership.
This is **not** Florian's lead-gen tool — it's Sky Life's. Florian gives the asset to Bano as a partnership-builder.

**Bano's USP that this tool surfaces**: scalable creator monetization + high-volume CPM placements / paid distribution of creator content. This is exactly what `Question 02` (whitelisting / Spark Ads) is designed to expose — most brands don't do it, Sky Life does it at scale.

**Lead routing**: Leads flow into Sky Life, NOT FL Digital. Florian's value-add is the asset itself, not the pipeline.

## 3. What it is NOT

- Not a 6-lever quiz (Earlybird format). Too heavy for cold brand-side audience.
- Not a Florian lead magnet — branding is Sky Life only (with text lockup "SLA · Sky Life Agency").
- Not a precise calculator — directional estimate based on industry benchmarks. Methodology disclosed in expand.
- Not iGaming-specific (regulatory risk in DE for ad platforms; iGaming clients come via Bano's direct sales).

## 4. Tech specs

| Aspect | Value |
|---|---|
| Stack | Single HTML, vanilla JS, Google Fonts (Inter, Anton, JetBrains Mono) |
| Hosting | TBD: subdomain `roi.skylifeagency.com` or subpath |
| Webhook | `https://hook.eu1.make.com/1npebtm7jcj283enhqvmulnfxcnkhm47` (shared, tag `skylife-creator-roi`) |
| Calendly | Placeholder `https://calendly.com/bano-diop/strategy-call` — TODO: real slot from Bano |
| URL params | `?name=Foo&company=Bar` pre-fills lead gate |
| Anonymous tracking | Anon ping on reveal stage (score + inputs, no PII) |

## 5. Design system

### Palette
- Background: pure white `#FFFFFF` (Sky Life logo is B&W)
- Text: near-black `#0A0A0A`
- Surface: `#FAFAFA`, `#F4F4F4`
- Border: `#E5E5E5`, accent border `#1A1A1A`
- Result section inverts to dark (black background, white text) for visual punch on the number

### Typography
- **Anton**: display headlines, big number, hero h1 (condensed, ALL CAPS)
- **Inter**: body, UI, labels (400–900 weights)
- **JetBrains Mono**: numerical labels, range markers, micro-copy

### Visual style
- Editorial / minimal / premium (not "tech startup")
- Sharp corners (no border-radius)
- Generous whitespace
- High contrast: white card on white page, black result on white page
- No images required — text lockup for logo, no portraits

## 6. The 3 inputs

| # | Question | Type | Multipliers (calc) |
|---|---|---|---|
| 01 | Monthly creator marketing spend | Slider $5k–$500k, step $5k | n/a (linear annual base) |
| 02 | Paid amplification on creator content | Radio: No / Sometimes / Yes | 1.0 / 0.4 / 0.15 |
| 03 | Campaign structure | Radio: One-off / Multi-week / Always-on | 1.2 / 1.0 / 0.8 |

### Formula
```
annualSpend = monthly_spend_k × 1000 × 12
waste = annualSpend × whitelistMult × cadenceMult
waste = clamp(waste, annualSpend × 0.08, annualSpend × 1.5)
waste = round_to_nearest(5000)
```

### Anchor reasoning
- No-whitelisting brands typically miss 5–15x reach extension at fractional cost → multiplier 1.0 captures roughly 1x of annual spend in unrealized incremental revenue
- "Sometimes" boosters typically only amplify hero pieces (20–30% of inventory) → ~0.4 of annual
- "Yes systematically" brands still have creative variety + cross-platform gaps → ~0.15 of annual
- One-off campaigns lose compounding (creative libraries, retargeting, audience signals) → 1.2x penalty
- Always-on already captures most compounding → 0.8 reduction

## 7. Lead gate logic

- Number reveals with **no email gate** — foot-in-the-door means immediate value
- Gate appears only on CTA "Show Me The Plan →"
- Fields: name, work email, company, role (select), annual budget (select)
- Budget field is the qualifier: Bano should personally follow up only on $250k+ / $1M+ / $5M+
- Sub-$250k gets automated email sequence (TBD by Bano)

## 8. Webhook payload shape

Two stages tracked:

**Stage 1 — anonymous reveal** (auto-fired on result reveal):
```json
{
  "source": "skylife-creator-roi",
  "timestamp": "2026-05-18T...",
  "stage": "reveal",
  "spend_monthly_k": 50,
  "whitelist": "no",
  "cadence": "oneoff",
  "waste_estimate": 720000
}
```

**Stage 2 — lead** (fired on lead form submit):
Same as above plus `name`, `email`, `company`, `role`, `budget`, `stage: "lead"`.

## 9. Open items before Bano sends

- [ ] Real Calendly slot from Bano (placeholder is `calendly.com/bano-diop/strategy-call`)
- [ ] Sky Life logo as SVG/PNG → replace text lockup in header
- [ ] (Optional) Dedicated Make.com webhook for Sky Life leads
- [ ] Sanity-check calculation multipliers with Bano's real deal data
- [ ] Decide hosting: `roi.skylifeagency.com` subdomain vs subpath on existing site
- [ ] Robots meta: keep `noindex,nofollow` if Bano wants exclusivity, remove for public launch

## 10. Anti-patterns

If I drift into these patterns while iterating, stop me:

- **6-Lever-Quiz creep**: "let's add one more question..." — NO. Three inputs, that's it. Friction kills foot-in-the-door.
- **Florian-branding creep**: FL Digital logo, Florian portrait, "by Florian Lapiz" — NO. Bano's asset, his pipeline.
- **iGaming carve-outs**: special copy for iGaming brands — NO. Generic brand-side, iGaming stays in Bano's direct sales.
- **Precision claims**: "exactly $X wasted" — NO. Always "estimated" / "directional" with methodology link.
- **Email gate before reveal**: hiding the number behind email — NO. Reveal is free, gate is for the plan.
- **Adding "we" / "our team" before partnership signed**: copy is currently sky-life-as-actor — keep it that way until Bano commits.

## 11. References

- Earlybird sibling asset (different use-case): `../earlybird/`
- Original 6-lever GTM-Audit: `../index.html`
- Sky Life Agency: https://skylifeagency.com
- Bano Diop LinkedIn: founder/host context already captured in this file
