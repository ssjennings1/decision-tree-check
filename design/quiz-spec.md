# Quiz spec — The Decision Tree Check

**Working title:** The Decision Tree Check
**Promise (one line):** Two minutes to see how much of your week is leaf-level work, and the one decision to hand back Monday.
**Audience:** Owner-operators, roughly 20–200 people, trades / manufacturing / family business / services.
**Runs on:** Taft Quiz Builder (Sites → Quizzes). Build instructions in `taft/build-spec.md`.

## How it works in one paragraph

Ten everyday situations. For each one the owner answers the same question: *last time this happened, where did it land?* Every situation is one that, in a company that is ready to grow, belongs on a leaf or a branch (someone else decides, with or without telling the owner). The answers score how far each decision climbed the tree. The total puts the owner in one of three results, and the category that scored highest (people, customers, money, or operations) tells them which branch to hand back first.

## Design choices (and why)

- **Same answer scale every time.** Faster, feels like a gut check not a test, and the scale itself quietly teaches the model (the five options ARE the five levels, read from the owner's side).
- **Situations, not self-ratings.** "Where did this land?" is something they know. "How good are you at delegating?" invites a flattering guess.
- **No worsening ladder, no confession.** Every answer is a legitimate way to run a company. The result names the pattern, not the person.
- **Ten questions.** Research puts the sweet spot for completion at 7–12, under three minutes. (`research/quiz-practice.md`)
- **Opt-in before the result, after the questions.** Standard for quiz lead magnets; the person has invested two minutes and wants the answer. (`research/quiz-practice.md`)
- **Three results, not a score.** A number is forgettable. A named pattern gets repeated to a spouse.
- **The One Move is solo.** It builds appetite without teaching away the room. Shannon's value is her in the room.

## Screen 1 — Intro

**Headline:** What landed on your desk this week?
**Body:** Ten everyday situations. For each one, pick where it landed the last time it happened. Two minutes. At the end you'll see how much of your week is small-decision work, and one thing to hand back on Monday.
**Button:** Start

## Screens 2–11 — The ten situations

Question stem on every screen: **Last time this happened, where did it land?**

Answer options (identical on every screen), with points:

| # | Answer | Points | Tree level it maps to |
|---|--------|--------|-----------------------|
| a | Someone handled it. I never heard about it. | 0 | Leaf |
| b | Someone handled it and told me after. | 1 | Branch |
| c | They checked with me before they acted. | 2 | Limb |
| d | We worked it out together. | 3 | Trunk |
| e | It came to me, and I decided. | 4 | Root |

Situations (category in brackets is for the follow-up, not shown to the taker):

| Q | Situation | Category |
|---|-----------|----------|
| 1 | A customer calls upset. A job or order didn't go the way they expected. | Customers |
| 2 | Two people on a crew or shift want to swap days. | People |
| 3 | A tool or small piece of equipment breaks and needs replacing. A few hundred dollars, not a few thousand. | Money |
| 4 | A supplier says a delivery is going to be a day late. | Operations |
| 5 | An employee asks for next Friday off. | People |
| 6 | A regular customer asks if you can squeeze in a rush job. | Customers |
| 7 | Somebody catches a quality problem before it goes out the door. | Operations |
| 8 | Two of your people disagree about how a job should be done. | People |
| 9 | A software renewal or a small recurring bill comes due. | Money |
| 10 | A new hire's first week needs to be planned. | People |

Score range: 0–40.

**A note on Q1 and Q8.** These are branch decisions in Shannon's own examples (a customer escalation; a disagreement between peers). A "checked with me first" answer (2 points) is not wrong there. The scoring still works because the result bands are wide and the point is the pattern across all ten, not any one answer. If Shannon wants it cleaner, swap Q1 for "A customer calls to ask when their order will be ready" and Q8 for "A crew needs a decision on which job to start first tomorrow."

## Categories (the "heaviest branch")

Each answer on each situation is assigned to that situation's category in the builder (People, Customers, Money, Operations). Taft scores each category as a percentage of its own maximum and reports the highest, so the uneven split (4/2/2/2) is fine. The result page and the emails use the highest category as "the heaviest branch." Ties are possible with two-question categories; the builder's tie-break is undocumented, so test a tied submission before launch.

Category wording as it appears to the taker (used on the result page and in email):

| Category | Shown as |
|----------|----------|
| People | People: schedules, time off, who does what, disagreements |
| Customers | Customers: complaints, special requests, promises made in the field |
| Money | Money: purchases, bills, small spending calls |
| Operations | Operations: suppliers, quality, equipment, what gets done when |

## Screen 12 — Opt-in (last page before the result)

In the builder this is a page with the fields below; the result page follows on submit. Email is required, which gates the result.

**Headline:** Your result is ready.
**Body:** Tell me where to send it. You'll see your result on the next screen and get a copy in your inbox with the one move for Monday.
**Fields:** First name (required) · Email (required) · How many people work in your company? (dropdown, Object Field `company_size`: Under 10 / 10–25 / 26–75 / 76–200 / 200+)
**Yes/No question (default No):** Also send me the Saturday Seed, one leadership idea a week you can put into play Monday. (Object Field `seed_optin`)
**Button:** Show my result
**Fine print:** No spam. Unsubscribe any time.

> Open decision for Shannon: unchecked checkbox (cleaner consent, fewer Seed subscribers) vs. a line saying "You'll also get the Saturday Seed; unsubscribe any time" (more subscribers, still honest). Recommendation: the checkbox. People who tick it stay.

## Results — three bands

| Band | Points | Builder tier (% of 40) | Result name | Tag (set by workflow) |
|------|--------|------------------------|-------------|-----------------------|
| A | 0–12 | 0–30% | Your tree holds its own weight. | `dt-result-a` |
| B | 13–26 | 31–65% | Half the canopy is on your desk. | `dt-result-b` |
| C | 27–40 | 66–100% | Everything runs through you. | `dt-result-c` |

Result copy is in `copy/result-pages.md`. Each result has the same shape: what the score means in plain words, what it looks like from inside, one move for Monday, one quiet line about help. The result page shows the overall tier as the headline and the highest category as the personalized line. The raw score is not the point; hide it if the builder allows, otherwise show "out of 10."

## Data captured on the contact

Synced automatically by the builder (Results Template → Settings → Custom Fields), named by Taft after the quiz:

| Field (as Taft names it) | Type | Values |
|--------------------------|------|--------|
| The Decision Tree Check - Overall Score | number | 0–40 |
| The Decision Tree Check - Overall Tier | text | A / B / C (tier labels set in the builder) |
| The Decision Tree Check - Highest Category Name | text | People / Customers / Money / Operations |

Object Fields on the opt-in page (created in Custom Fields before building):

| Field | Type | Values |
|-------|------|--------|
| `company_size` | dropdown | Under 10, 10–25, 26–75, 76–200, 200+ |
| `seed_optin` | yes/no | Yes / No |

Tags, all applied by the workflow: `decision-tree-check` (took it), `dt-result-a` / `dt-result-b` / `dt-result-c`, and the Saturday Seed source tag when `seed_optin` = Yes.

## What happens after (workflow, summary)

1. Quiz Submitted trigger (filter: quiz name) → tag `decision-tree-check`; If/Else on Overall Tier → result tag.
2. Immediately: result email (`copy/emails.md`, Email 1), matched to band, with the highest-category line merged from the synced field.
3. Band C only: Shannon gets an internal notification with name, size, heaviest branch. No automated pitch. Her call whether to reach out.
4. Three days later, Mon–Thu 8 AM: follow-up (`copy/emails.md`, Email 2). One question: which one did you hand back?
5. If `seed_optin` = Yes: add the Saturday Seed source tag so the existing Seed welcome sequence takes over.

Full build steps in `taft/build-spec.md`.
