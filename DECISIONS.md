# Decisions

Newest first. "S" = Shannon decided. "C" = Claude decided; Shannon said "you make the calls" on 2026-10-27 for this experimental run, so these stand unless she overrules.

| Date | Decision | Who |
|------|----------|-----|
| 2026-10-27 (eve) | **Design v2, Shannon's direction:** a picture, not a diagnosis. The tree is the model for decisions; the desk is the leader. Items across all five levels; tap what landed. Size and role asked LAST with the "map looks different at 5 than at 25" line. Score = goodness of fit between the desk and what the stage and seat call for, not volume. | S |
| 2026-10-27 (eve) | **Stage names:** Builder (under 10), Stretching (10–40; "Doug Tatum calls it No Man's Land, I call it stretching"), Architect (41+). Switchboard and Shade Tree rejected. Thresholds are Shannon's judgment; copy says gut check. | S / C |
| 2026-10-27 (eve) | **Result = stage + fit state (on track / weight climbing / roots drifting) + green flag + red flag + One Move.** Flattering, useful, shareable. Team members and family members get their own fit read; the owner can send it to the team and compare trees. | S / C |
| 2026-10-27 (eve) | **Headcount only. Revenue question gone for good.** | S |
| 2026-10-27 (eve) | **Mechanism: Taft survey → scored redirect → designed pages → workflow** (the contractor build's mechanism, none of its content). Quiz Builder rejected because its results page can't condition on role or size; webhook/custom page held in reserve. Start with three result pages (by state) with the stage merged in; expand to eleven only if page merge fails. | C |
| 2026-10-27 (eve) | Old Taft assets: unpublish "Scotoma Spotter App" workflow at launch (live inbound webhook); rename both old workflows OLD – DO NOT USE; survey and 13-page site parked. | C |
| 2026-10-27 | **The goal of the tree, in Shannon's words:** clarity, empowerment, development, and a leader's desk with the most important on-the-business items on it. Result copy, One Moves and emails rewritten to carry all four, not just relief. | S |
| 2026-10-27 | Experimental run: Claude makes all calls, nothing goes live. Deliverable = working prototype + launch strategy. Tone: fun, interactive, useful, a gut check not a scientific tool. | S |
| 2026-10-27 | **Title (the door):** "What Landed on Your Desk Last Week?" **Asset/result name:** "The Decision Tree Check" (Taft quiz name, custom-field prefix). **Slug:** `/desk`. Reason: second-person question titles beat framework names in every title dataset; the buyer responds to language about the business, not the owner. | C |
| 2026-10-27 | **Show the score AND name the pattern.** Score as "Desk Load: NN of 40" (a number a CPA can repeat); pattern name as the headline (a label the owner will repeat). Both are supported natively in Taft. | C |
| 2026-10-27 | **Pattern names (flattering-but-true, no ladder of shame):** A = The Shade Tree. B = The Switchboard. C = The Builder. The highest-load result gets the most identity-affirming name on purpose: the sharing research says positive framing of the same score triples sharing, and the no-negging rule says the same thing. | C |
| 2026-10-27 | **Seed opt-in:** Yes/No defaulting to No, with a playful label. A real yes. | C |
| 2026-10-27 | **Q1 and Q8 swapped** for leaf-level situations ("when will my order be ready," "which job starts first tomorrow"). | C |
| 2026-10-27 | **Booking button on all three results.** | C |
| 2026-10-27 | **Result C gets a personal email from Shannon within 24 hours** (drafted; she edits and sends), plus the automated result email. Notification only was too passive for the warmest leads. | C |
| 2026-10-27 | **Scope stays narrow.** The four-dimension "Owner Readiness Check" from the lead-gen report is version two. Ship the Decision Tree Check alone; the data model (categories, tiers, tags) can take more dimensions later. | C |
| 2026-10-27 | **Launch order:** email list → referral partners with a forwardable paragraph → DisruptHR QR → LinkedIn (documents/carousels, not text posts). Reason: referrals are 55–80% of clients like hers; LinkedIn organic reach is down 34–50%. | C |
| 2026-10-27 | **Launch tied to a dated event** (DisruptHR). Scorecard cases that cite revenue were all paired with an event. | C |
| 2026-10-27 | **Archive `scotoma-spotter`** once the redirect is live. | C |
| 2026-10-27 | Replace the Scotoma Spotter rather than redesign it. Fresh repo. | S |
| 2026-10-27 | Concept: lead-generation quiz based on the Decision Tree model. | S |
| 2026-10-27 | Research first; no API or browser work in Taft for now. | S |
| 2026-10-27 | Ten situational questions, one shared 0–4 answer scale, three result bands. Heaviest branch from native category scoring. | C |
| 2026-10-27 | Opt-in page sits after the questions and before the result. | C |
| 2026-10-27 | Repo: github.com/ssjennings1/decision-tree-check. | S |

## Superseded on 2026-10-27 (eve)
- "Show the score AND name the pattern," the Shade Tree / Switchboard / Builder pattern names, and the ten-question 0–4 scale are replaced by the v2 design above.

## Still open (not blocking)

- Whether the DisruptHR date or the Seed list is the first public outing. Plan assumes list first, two weeks before DisruptHR.
- Size thresholds for the three stages (under 10 / 10–40 / 41+) are a first guess.
- Whether to build three result pages (state) or eleven (stage × state): decided by whether custom-field merge renders on Taft pages.
- Taft survey must be verified to support per-answer points and redirect-by-score (the old build suggests yes).
