# Inovexus — Pipeline Readiness Check

Project context for Claude. Loaded when working in `/Users/florianlapiz/Documents/gtm/inovexus/`.

## 1. What this asset is

A 60-second self-diagnostic for **Pre-Seed and Seed B2B SaaS founders** in the
**Inovexus acceleration cohort**. Five levers, score 0–10, tier-based diagnosis,
three priority operator plays, CTA for a 1:1 cohort mentor slot with Florian.

## 2. Strategic context

**Trigger:** Florian gave a 60-minute workshop ("From ICP to Pipeline") to 7
founders in an Inovexus cohort. The workshop was unpaid — explicit foot-in-the-door
move. Several weeks of silence since. Florian was mentioned in a Prospeo post
(reference unclear), but no follow-up.

**Goal:** Florian wants to become **recurring cohort mentor** at Inovexus,
establishing himself in their system rather than running one-off workshops.

**Contacts:**
- **Damien** — initial contact, escalated him to Alberto. Has decision-making weight.
- **Alberto** — operational contact who ran the workshop with Florian.

Outreach plan: Tool goes to **both**. Direct to Alberto (operational), FYI-loop to Damien.

**Florian's positioning:** "Background advisor / cohort mentor" — invisible in
the tool branding (it reads as an Inovexus asset), visible only in the result
CTA section and on the Calendly link.

## 3. The five levers — why these

Direct from Florian's workshop material (`/Users/florianlapiz/Documents/cc-inovexus-workshop/`).
Specifically the Q&A cheatsheet + emergency playbook.

| # | Lever | Workshop reference | Pre-Seed/Seed bottleneck it diagnoses |
|---|---|---|---|
| 1 | **ICP Concentration** | Last-20 Audit play (adapted to Last-10 for Pre-Seed) | ICP drift before repeatability |
| 2 | **Signal vs Volume** | 90-Day Trigger Map play | Outbound research vs. spam |
| 3 | **Stack-Phase Fit** | €200-250/month stack rule, anti-HubSpot-Enterprise | Premature scaling via wrong tooling |
| 4 | **Founder Operating Mode** | Founder Mute Test play | Bottleneck identification |
| 5 | **PMF Reality** | 30%-price-raise litmus test | PMF vs. payment confusion |

Each lever is a `radio` group with three options scoring 0, 1, 2 — total max 10.

## 4. Tier logic

| Score | Tier | Strategic frame |
|---|---|---|
| 0–3 | Foundation Phase | Pre-PMF · research mode · don't scale yet |
| 4–7 | Finding Repeatability | Transition phase · system emerging but founder still load-bearing |
| 8–10 | Ready-to-Scale | Repeatable motion · ROI-per-hour focus, not inputs |

## 5. Plays (auto-picked by lowest scores)

Three plays from the workshop, picked by the three weakest levers. Priority play
gets visual highlight + "Priority" tag.

All play texts are from Florian's workshop material — same operator moves he
already delivered live.

## 6. Tech / Design

| Aspect | Value |
|---|---|
| Stack | Single HTML, vanilla JS, Google Fonts |
| Theme | Dark mode (navy `#0B1729` background) — inverse of CopeCart |
| Accent | Cyan-blue gradient `#6FCBFF → #4FB8FF → #5D78FF` |
| Logo | Inovexus white SVG (from their own CDN) |
| Pattern reuse | Multi-step flow, auto-advance on radio select, mobile-optimized — all inherited from CopeCart base |
| Webhook tag | `inovexus-pipeline-readiness` |
| Calendly placeholder | `https://calendly.com/florian-lapiz/inovexus-mentor` (TODO real slot) |
| Language | English (Inovexus is international: Europe, Asia, US) |

## 7. CTA framing

Result CTA explicitly says **"Cohort Mentor Slot"** — not "book a discovery call".
That phrase plants the position Florian wants to establish:
- Pre-pre: Florian = workshop speaker
- Post-tool: Florian = cohort mentor

The CTA copy:
> "Florian Lapiz · GTM mentor for the Inovexus cohort. Same operator who ran the
> workshop — now available for recurring sparring on whichever lever is bottlenecking
> your pipeline."

## 8. Anti-patterns

- ❌ **Florian-branding creep** — no FL Digital logo, no portrait. Florian only
  appears in the result CTA section and the footer disclosure
- ❌ **Re-engagement apology** — never reference the silence in the tool itself.
  The tool moves forward, the handover message does
- ❌ **Pitching new workshops** — the tool sells **mentor recurrence**, not
  another paid workshop. That's a different motion
- ❌ **Email gate before result** — reveal is free, only the optional Calendly CTA
- ❌ **Naming founders' specific cohort** — keep it general so it can be reused
  across Inovexus cohorts without rebuilding

## 9. References

- Workshop material: `/Users/florianlapiz/Documents/cc-inovexus-workshop/`
- Sibling assets: `../skylife/` (Bano), `../copecart/` (Stefan), `../earlybird/` (Jay)
- Inovexus website: https://inovexus.com
