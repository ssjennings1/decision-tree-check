# Spec v2 — What Landed on Your Desk Last Week?

**Door:** What landed on your desk?
**Asset name:** The Decision Tree Check (Taft survey name, tag prefix)
**Slug:** syncovatellc.com/desk
**What it is:** a picture, not a diagnosis. The tree is the model for the decisions. The desk is the leader. The result shows where the weight sits on your tree, whether that fits your stage and role, and two tips.
**Mechanism:** Taft survey with per-answer points → score-band redirect to designed result pages on the Syncovate site → workflow for emails. This is the mechanism the 2026 contractor build used (survey `ml4MMyo0MvP1cI1EIc7N` + site `9ogHGNXNWnCW9feI6SE7`); we reuse the mechanism and none of the content. Build steps: `taft/build-spec.md`. Reference implementation of the scoring: `prototype/index.html`.

## The flow

1. **Door.** One line, one button.
2. **Tap what landed.** 25 everyday decisions on five screens (People / Customers / Money / Operations / Strategy), one of each level per screen, shuffled. Tap every decision that landed on you in the last two weeks. Nothing on screen gives the level away.
3. **Size and role.** Asked last, with the line that explains why: *"The map looks different at five people than at twenty-five. Everything running through you is the right answer at one of those sizes."*
4. **Opt-in.** First name, email, Seed yes/no (default no). Email required; it gates the result.
5. **Result.** The tree, lit by what landed. Stage, fit, one green flag, one red flag, One Move for Monday, two buttons.

## The items

Twenty-five decisions, five categories, one of each level in every category (Shannon, 2026-10-27: "25 checkboxes across 5 categories"). Every item is a decision, verb first. The taker never sees the level; within a screen the five items are shuffled. Window: the last two weeks.

| # | Decision (as shown) | Level | Screen |
|---|---------------------|-------|--------|
| 1 | Approve time off for next Friday. | Leaf | People |
| 2 | Decide who covers when somebody's out sick. | Branch | People |
| 3 | Decide whether somebody moves into a different role. | Limb | People |
| 4 | Decide what we offer for benefits and time off. | Trunk | People |
| 5 | Decide what our values are and what our culture is going to be. | Root | People |
| 6 | Give a customer a delivery date. | Leaf | Customers |
| 7 | Handle a customer complaint. | Branch | Customers |
| 8 | Decide whether a long-time customer gets an exception on price or terms. | Limb | Customers |
| 9 | Decide what changes after the same complaint shows up for the third time. | Trunk | Customers |
| 10 | Decide whether to take on bigger work for a customer that means investing in new tools. | Root | Customers |
| 11 | Replace everyday equipment. A few hundred dollars. | Leaf | Money |
| 12 | Approve a purchase a manager wants that's over their usual limit. | Branch | Money |
| 13 | Decide whether to repair the old one or buy new. | Limb | Money |
| 14 | Buy software that changes how everybody works. | Trunk | Money |
| 15 | Decide whether it's time for a CFO instead of a bookkeeper. | Root | Money |
| 16 | Choose between FedEx and UPS. | Leaf | Operations |
| 17 | Decide what to do when a vendor misses a delivery. | Branch | Operations |
| 18 | Decide how to handle a safety concern somebody raised. | Limb | Operations |
| 19 | Change a process everybody touches. | Trunk | Operations |
| 20 | Decide what's next now that we've outgrown our space. | Root | Operations |
| 21 | Decide which association meeting or local event we show up at. | Leaf | Strategy |
| 22 | Decide how to respond when a competitor drops their prices. | Branch | Strategy |
| 23 | Set this quarter's priorities. | Limb | Strategy |
| 24 | Decide how to respond to a competitor who keeps hiring our best people. | Trunk | Strategy |
| 25 | Decide whether to grow next year, or stay the size we are. | Root | Strategy |

Count by level: 5 each (25 items). Candidates not used, available to swap in: make a critical hire (People, root); your best person says they're thinking about leaving (People, trunk); somebody caught stealing (People, root); decide who our ideal customer is (Customers, root); go after a new product or service line (Operations/Strategy, root); retool the line (Operations, root); set this year's goals (Strategy, trunk); what the company looks like in five years (Strategy, root); a competitor who's retiring is for sale (Strategy, root).

## Disagreement is the point

Levels are company-specific. A truck purchase is a leaf for a fleet and a root for a three-truck shop. The items are written as clearly as possible with scale anchors ("a few hundred dollars, not a few thousand"), and every result page carries the disagreement block: you'll disagree with where I put some of these, good, the real tree is the one you draw with your team. (Shannon, 2026-10-27.)

## Size and role (asked last)

**How many people work here?** Under 10 · 10–25 · 26–40 · 41–100 · 100+
**What's your seat?** Owner / CEO / President · On the leadership team · Manager or team lead · Family member in the business

Stage comes from size (the territory). Fit comes from role and stage together (what should be on this desk).

| Size | Stage |
|------|-------|
| Under 10 | **Builder** |
| 10–40 | **Stretching** (Doug Tatum calls it No Man's Land; we say stretching) |
| 41+ | **Architect** |

These thresholds are Shannon's judgment, not research, and the copy says so ("a gut check, not a diagnosis").

## The expected desk (the matrix)

Which levels *should* land on this desk. ✔ = expected on the desk. ✘ = should be handled elsewhere. ~ = either is fine.

| Role × Stage | Leaf | Branch | Limb | Trunk | Root |
|--------------|------|--------|------|-------|------|
| Owner, Builder | ✔ | ✔ | ✔ | ✔ | ✔ |
| Owner, Stretching | ✘ | ~ | ✔ | ✔ | ✔ |
| Owner, Architect | ✘ | ✘ | ~ | ✔ | ✔ |
| Leadership team (any stage) | ✘ | ✔ | ✔ | ✔ | ✘ |
| Manager / team lead (any stage) | ✔ | ✔ | ~ | ✘ | ✘ |
| Family member (any stage) | treated as Leadership team, with its own copy about bloodline vs. role | | | | |

## Fit

Two counts, computed from the tapped items against the expected desk:

- **Climbing** = items that landed on the desk from a ✘ level. (Small stuff reaching you.)
- **Drifting** = items from a ✔ level that did NOT land on the desk. (Big stuff happening without you.)

~ levels count for neither.

| Result state | Rule |
|--------------|------|
| **On track** | climbing ≤ 1 and drifting ≤ 1 |
| **Weight climbing** | climbing ≥ 2 and climbing ≥ drifting |
| **Roots drifting** | drifting ≥ 2 and drifting > climbing |

Flags (two lines, personalized):
- **Green flag** = the ✘ level with the fewest items on the desk (what you let go of well), or for Builder-stage owners the ✔ level most lit (what you're carrying well).
- **Red flag** = the ✘ level with the most items on the desk (what you hold), or if drifting wins, the ✔ level with the most items missing (what's happening without you).

## Result pages

Pages are stage × state for owners (Builder on track, Builder drifting, Stretching on track / climbing / drifting, Architect on track / climbing / drifting) plus three for other seats (Leadership team on track / climbing / drifting, with Manager and Family variants in copy). Copy in `copy/result-pages.md`. Each page: stage headline said like a compliment, the tree illustration for that stage, the fit line, the two flags (merged from fields; see build spec), One Move, buttons: Book 15 minutes · Send this to someone whose desk you're curious about.

## How Taft computes this (summary; detail in build spec)

Taft surveys score by points, not by rule, so the survey carries an approximation and the workflow finishes the job:
- Each tapped item carries points by level (Leaf 2, Branch 2, Limb 1, Trunk −1, Root −2 for the Yes answer; the No answer on trunk/root carries +2). Size and role options carry adjustment points so a Builder-stage owner's full desk nets near zero.
- The survey's score bands pick the redirect page (negative = drifting, near zero = on track, positive = climbing).
- Every item is mapped to a contact field; the workflow's Math Operation steps sum per-level loads into five number fields and compute the flags, which merge into the result email.
- The prototype is the reference implementation; the Taft points are tuned to agree with it on the test cases in the build spec.
