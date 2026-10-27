# Spec v2 — What Landed on Your Desk Last Week?

**Door:** What landed on your desk last week?
**Asset name:** The Decision Tree Check (Taft survey name, tag prefix)
**Slug:** syncovatellc.com/desk
**What it is:** a picture, not a diagnosis. The tree is the model for the decisions. The desk is the leader. The result shows where the weight sits on your tree, whether that fits your stage and role, and two tips.
**Mechanism:** Taft survey with per-answer points → score-band redirect to designed result pages on the Syncovate site → workflow for emails. This is the mechanism the 2026 contractor build used (survey `ml4MMyo0MvP1cI1EIc7N` + site `9ogHGNXNWnCW9feI6SE7`); we reuse the mechanism and none of the content. Build steps: `taft/build-spec.md`. Reference implementation of the scoring: `prototype/index.html`.

## The flow

1. **Door.** One line, one button.
2. **Tap what landed.** 18 everyday things, across all five levels, on four screens (People / Customers / Money and tools / The big stuff). Tap everything that came to you last week. The big-stuff screen asks each item as Yes/No so a "no" can carry weight.
3. **Size and role.** Asked last, with the line that explains why: *"The map looks different at five people than at twenty-five. Everything running through you is the right answer at one of those sizes."*
4. **Opt-in.** First name, email, Seed yes/no (default no). Email required; it gates the result.
5. **Result.** The tree, lit by what landed. Stage, fit, one green flag, one red flag, One Move for Monday, two buttons.

## The items

Each item belongs to a level. The taker never sees the level. Order on screen is mixed so the levels aren't guessable.

| # | Item (as shown) | Level | Screen |
|---|-----------------|-------|--------|
| 1 | Somebody wanted next Friday off. | Leaf | People |
| 2 | Two people on a crew or shift wanted to swap days. | Leaf | People |
| 3 | A crew needed to know which job to start first tomorrow. | Branch | People |
| 4 | Somebody asked how to handle a customer who was getting loud. | Branch | People |
| 5 | A new hire's first week needed a plan. | Limb | People |
| 6 | Somebody wanted to move into a different role. | Limb | People |
| 7 | A customer called to ask when their order would be ready. | Leaf | Customers |
| 8 | A regular asked if we could squeeze in a rush job. | Branch | Customers |
| 9 | A customer wanted a price exception. | Limb | Customers |
| 10 | A long-time customer asked for work we're not set up for yet. | Trunk | Customers |
| 11 | A tool broke and needed replacing. A few hundred bucks. | Leaf | Money & tools |
| 12 | A supplier said the delivery would be a day late. | Branch | Money & tools |
| 13 | A software renewal or a small recurring bill came due. | Leaf | Money & tools |
| 14 | A piece of equipment that costs real money needed a yes or no. | Trunk | Money & tools |
| 15 | Somebody caught a quality problem before it went out the door. | Branch | Money & tools |
| 16 | Your best person said they're thinking about leaving. | Root | The big stuff |
| 17 | A chance came up to add a service, a location, or a big new customer. | Root | The big stuff |
| 18 | Somebody asked what the company's going to look like in three years. | Root | The big stuff |

Count by level: Leaf 5, Branch 5, Limb 3, Trunk 2, Root 3. The big-stuff screen (items 10, 14, 16, 17, 18) is asked as "Did this one come to you?" Yes/No.

## Size and role (asked last)

**How many people work here?** Under 10 · 10–25 · 26–40 · 41–100 · 100+
**What's your seat?** Owner / CEO / President · On the leadership team · Manager or crew lead · Family member in the business

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
| Manager / crew lead (any stage) | ✔ | ✔ | ~ | ✘ | ✘ |
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
