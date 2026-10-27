# What was already in Taft: the 2026 contractor build of the Scotoma Spotter

Reviewed in the browser 2026-10-27. Shannon's note: she hired a contractor to build this in GHL, never launched it; it was her first iteration of the Scotoma Spotter. The GitHub app (spotter.syncovatellc.com) was the second iteration.

## Inventory

| Asset | Id | Status |
|-------|----|--------|
| Survey "Scotoma Spotter™" | ml4MMyo0MvP1cI1EIc7N | exists; widget URL link.syncovatellc.com/widget/survey/ml4MMyo0MvP1cI1EIc7N |
| Site "Scotoma Spotter Pages" | 9ogHGNXNWnCW9feI6SE7 | 13 pages, no domain attached (parked) |
| Workflow "Scotoma Spotter Survey Submitted" | 674cd620-… | draft; Survey Submitted → Add Tag "Scotoma Spotter" (tag never created) → Internal Notification → End. No email. |
| Workflow "Scotoma Spotter App" | 4f1982ad-… | **published**, v35; Inbound Webhook → Create Contact → Update contact field → Add Tag → Internal Notification → End. No email. This is what the GitHub app posted to. Unpublish at launch. |
| Site "Internal Champion Toolkit…" | 8DOXEpKMPNRfSFixGSSk | one page, "Scotoma Spotting Manager"; unrelated draft |

## The survey (9 slides)

1. Size (1–10 / 11–25 / 26–75 / 76–200 / 200+) and role (Founder/CEO/Owner · C-suite/President/Partner · VP/Director · Manager/Other)
2. How often do you wake up at 3 am with the feeling that something's off?
3. Which statement best describes your current leadership reality? (see everything → drowning)
4. In the past 12 months, tried to fix friction and it didn't stick?
5. How long have you been sensing this?
6. Which pattern feels most true? (four blind spots: Architectural / Optimizer / Relational / Velocity)
7. If you could solve this today, would you rather… (DIY / roadmap / hands-on partnership / other)
8. Annual revenue, and "what would you invest" ($1k to $25k+)
9. Gate: "Your Scotoma Profile Is Ready" — first name, email, organization, marketing consent, Submit

Scored by points → redirect to one of the 13 pages by stage (Early-Scale under 30 / Builder / Inflection / Breaking / Transformation) and blind spot.

## The result pages

Dark background, serif headline, "Hi {{first name}}," then The Pattern / The Reality / The Cost / What You're Missing / The Path Forward, ending in "Purchase the Blind Spot Scan, $3,500" and a "not ready?" PDF. Example claims: "every week this remains invisible, you lose approximately 15–20% in execution velocity." Nav: Services / About / Contact / Schedule a Blind Spot Scan.

## What we keep

- **The mechanism.** Survey with per-answer points → score-band redirect → designed pages in the site builder → workflow. It gives full control of the result page without code, which the Quiz Builder's results page can't.
- **Size and role as inputs.** Moved to the end in v2, but the instinct was right.
- **"Builder"** as a stage name.

## What we drop

- Every question (they measure distress and willingness to pay, not the business).
- The revenue question and "what would you invest" (Shannon, 2026-10-27: headcount only, revenue gone).
- The result copy (invented numbers; "you think it's a people problem" is the negging the brand now bans).
- The $3,500 Blind Spot Scan (the offer no longer exists).
- No follow-up email existed in either workflow. The v2 sequence is the first time the lead gets anything after the result page.

## Retire at launch

Unpublish "Scotoma Spotter App"; rename both workflows "OLD – DO NOT USE – …"; leave the survey and site parked or delete; remove CNAME from the GitHub repo and archive it.
