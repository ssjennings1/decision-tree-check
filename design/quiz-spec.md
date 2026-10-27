# Quiz spec — What Landed on Your Desk Last Week?

**Door (title people click):** What Landed on Your Desk Last Week?
**Asset name (Taft quiz name, result header):** The Decision Tree Check
**Slug:** syncovatellc.com/desk
**Promise:** Ten things that happen in every company. Pick where each one landed. Two minutes. You get a number you can repeat to your spouse and one thing to hand back on Monday.
**Tone:** a gut check, not a scientific tool. Fun, quick, no wrong answers, no grade.
**Runs on:** Taft Quiz Builder. Build steps in `taft/build-spec.md`. A clickable prototype of exactly this flow is published as an artifact and saved at `prototype/index.html`.

## How it works

Ten everyday situations, one question every time: *last time this happened, where did it land?* Five answers, same every time, scored 0–4. The total (0–40) is the Desk Load. The category that scored highest (People, Customers, Money, Operations) is the heaviest branch. Three result patterns, each named for what the owner IS, not what's wrong.

## Screen 1 — Door

**Headline:** What landed on your desk last week?
**Body:** Ten things that happen in every company. Pick where each one landed the last time it happened. No wrong answers, no grade. Two minutes.
**Small line:** You'll get your Desk Load, the one branch that's carrying the most, and one thing to hand back Monday.
**Button:** Let's see

## Screens 2–11 — The ten situations

Stem on every screen: **Last time this happened, where did it land?**

| # | Answer | Points | Level |
|---|--------|--------|-------|
| a | Never heard about it. Somebody handled it. | 0 | Leaf |
| b | Handled. Then they told me. | 1 | Branch |
| c | They checked with me first. | 2 | Limb |
| d | We hashed it out together. | 3 | Trunk |
| e | Came to me. I made the call. | 4 | Root |

| Q | Situation | Category |
|---|-----------|----------|
| 1 | A customer calls to ask when their order will be ready. | Customers |
| 2 | Two people on a crew or shift want to swap days. | People |
| 3 | A tool breaks and needs replacing. A few hundred bucks, not a few thousand. | Money |
| 4 | A supplier says the delivery is going to be a day late. | Operations |
| 5 | Somebody asks for next Friday off. | People |
| 6 | A regular customer asks if you can squeeze in a rush job. | Customers |
| 7 | Somebody catches a quality problem before it goes out the door. | Operations |
| 8 | A crew needs to know which job to start first tomorrow. | People |
| 9 | A software renewal or a small recurring bill comes due. | Money |
| 10 | A new hire's first week needs a plan. | Operations |

Category split: People 3, Customers 2, Money 2, Operations 3. Taft scores each category as a percentage of its own max, so uneven sizes are fine. Ties are possible; test one before launch (`taft/build-spec.md` §6).

## Screen 12 — Opt-in (last page before the result)

**Headline:** Your result's ready.
**Body:** Where should I send the copy? You'll see it on the next screen too.
**Fields:** First name (required) · Email (required) · How many people work in your company? (Under 10 / 10–25 / 26–75 / 76–200 / 200+)
**Yes/No, default No:** Also send me the Saturday Seed. One leadership idea a week, two minutes to read, built for Monday.
**Button:** Show me
**Small line:** No spam. Unsubscribe any time.

## Results — three patterns

| Band | Points | Builder tier (% of 40) | Pattern | Tag |
|------|--------|------------------------|---------|-----|
| A | 0–12 | 0–30% | The Shade Tree | `dt-result-a` |
| B | 13–26 | 31–65% | The Switchboard | `dt-result-b` |
| C | 27–40 | 66–100% | The Builder | `dt-result-c` |

Result page shows: pattern name (headline), Desk Load NN of 40, the heaviest branch line, the pattern paragraph, One Move for Monday, two buttons (Book 15 minutes · Send this to an owner you know), and the Susan Scott credit in small type. Copy in `copy/result-pages.md`.

## Data on the contact

Auto-synced by the builder: The Decision Tree Check - Overall Score (0–40), - Overall Tier (A/B/C), - Highest Category Name. Object fields on the opt-in page: `company_size` (dropdown), `seed_optin` (yes/no). Tags set by the workflow: `decision-tree-check`, `dt-result-a/b/c`, Saturday Seed source tag when `seed_optin` = Yes.

## After submit (workflow)

1. Quiz Submitted → tag `decision-tree-check`; If/Else on Overall Tier → result tag.
2. Immediately: result email matched to band (`copy/emails.md`).
3. Band C: internal notification to Shannon AND a task "Send personal note within 24h" with the draft from `copy/emails.md` pasted into the task.
4. Three days later, Mon–Thu 8 AM: follow-up email.
5. `seed_optin` = Yes → Saturday Seed source tag → existing Seed welcome sequence takes over.
