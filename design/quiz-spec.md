# Spec v2 — What Landed on Your Desk Last Week?

**Door:** What landed on your desk last week?
**Asset name:** The Decision Tree Check (Taft survey name, tag prefix)
**Slug:** syncovatellc.com/desk
**What it is:** a picture, not a diagnosis. The tree is the model for the decisions. The desk is the leader. The result shows where the weight sits on your tree, whether that fits your stage and role, and two tips.
**Mechanism:** Taft survey with per-answer points → score-band redirect to designed result pages on the Syncovate site → workflow for emails. This is the mechanism the 2026 contractor build used (survey `ml4MMyo0MvP1cI1EIc7N` + site `9ogHGNXNWnCW9feI6SE7`); we reuse the mechanism and none of the content. Build steps: `taft/build-spec.md`. Reference implementation of the scoring: `prototype/index.html`.

## The flow

1. **Door.** One line, one button.
2. **Tap what landed.** 28 everyday decisions, across all five levels, on five screens (People / Customers / Money and operations / The big stuff / The really big stuff). Tap every decision that landed on you last week. The two big-stuff screens ask each one as Yes/No so a "no" can carry weight.
3. **Size and role.** Asked last, with the line that explains why: *"The map looks different at five people than at twenty-five. Everything running through you is the right answer at one of those sizes."*
4. **Opt-in.** First name, email, Seed yes/no (default no). Email required; it gates the result.
5. **Result.** The tree, lit by what landed. Stage, fit, one green flag, one red flag, One Move for Monday, two buttons.

## The items

Every item is a decision, verb first (Shannon, 2026-10-27: "it's a decision tree, so they should be decisions"). Two pairs escalate on purpose so the levels teach themselves: a complaint vs. the same complaint for the third time; a small renewal vs. the major one that keeps going up. Each item belongs to a level the taker never sees. Industry-neutral wording.

| # | Decision (as shown) | Level | Screen |
|---|---------------------|-------|--------|
| 1 | Approve time off for next Friday. | Leaf | People |
| 2 | Approve two people swapping schedules. | Leaf | People |
| 3 | Decide who covers when somebody calls in sick. | Branch | People |
| 4 | Decide which big project starts tomorrow and which one waits. | Branch | People |
| 5 | Plan a new hire's first week. | Limb | People |
| 6 | Decide whether somebody moves into a different role. | Limb | People |
| 7 | Tell a customer when their order or project will be ready. | Leaf | Customers |
| 8 | Handle a customer complaint. | Branch | Customers |
| 9 | Decide what changes after the same complaint shows up for the third time. | Limb | Customers |
| 10 | Decide whether a good customer gets an exception on price or terms. | Limb | Customers |
| 11 | Replace something that broke. A few hundred dollars. | Leaf | Money & operations |
| 12 | Renew a small software subscription. | Leaf | Money & operations |
| 13 | Decide what to do when a vendor says they'll be late. | Branch | Money & operations |
| 14 | Decide how to fix a mistake somebody caught before it reached a customer. | Branch | Money & operations |
| 15 | Decide whether to take on work a long-time customer wants that we're not set up for. | Trunk | The big stuff |
| 16 | Renew a major software contract that keeps going up, or invest in infrastructure instead. | Trunk | The big stuff |
| 17 | Decide what we offer for benefits. | Trunk | The big stuff |
| 18 | Decide how people get reviewed, or whether they do. | Trunk | The big stuff |
| 19 | Set this year's goals. | Trunk | The big stuff |
| 20 | Decide what happens when sales promises something operations has to clean up. | Trunk | The big stuff |
| 21 | Decide what the sales team's job is, because right now they're not sure. | Trunk | The big stuff |
| 22 | Decide what to do when your best person says they're thinking about leaving. | Root | The really big stuff |
| 23 | Decide what's next now that we've outgrown our space. | Root | The really big stuff |
| 24 | Decide whether it's time for a role we've never had, like a CFO instead of a bookkeeper. | Root | The really big stuff |
| 25 | Decide what the company looks like in five years. | Root | The really big stuff |
| 26 | Decide how to respond to a competitor who keeps hiring our best people. | Root | The really big stuff |
| 27 | Decide whether to make a move on a competitor that closed, is retiring, or is for sale. | Root | The really big stuff |
| 28 | Decide what happens after somebody was caught stealing from the company. | Root | The really big stuff |

Count by level: Leaf 5, Branch 5, Limb 4, Trunk 7, Root 7 (28 items). The two big-stuff screens (items 15–28) are asked as "Did this decision come to you?" Yes/No. Trunk and root examples are Shannon's.

## Disagreement is the point

Levels are company-specific. A truck purchase is a leaf for a fleet and a root for a three-truck shop. The items are written as clearly as possible with scale anchors ("a few hundred dollars, not a few thousand"), the first screen says "answer for your company, not the textbook," and every result page carries the disagreement block: you'll disagree with where I put some of these, good, the real tree is the one you draw with your team. (Shannon, 2026-10-27.)

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
