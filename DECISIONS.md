# Decisions

Newest first. "S" = Shannon decided. "C" = Claude decided on his own and it's reversible; flagged in the report.

| Date | Decision | Who |
|------|----------|-----|
| 2026-10-27 | Replace the Scotoma Spotter rather than redesign it. Fresh repo. | S |
| 2026-10-27 | Concept: lead-generation quiz based on the Decision Tree model. | S |
| 2026-10-27 | Research first; build the plan and the spec; no API or browser work in Taft for now. | S |
| 2026-10-27 | Working name "The Decision Tree Check." Slug `/decision-tree`. | C |
| 2026-10-27 | Ten situational questions, one shared 0–4 answer scale, three result bands. "Heaviest branch" comes from native category scoring, not a self-report question. | C |
| 2026-10-27 | Opt-in screen sits after the questions and before the result. | C |
| 2026-10-27 | Seed subscription is a Yes/No question defaulting to No on the opt-in page (recommendation; see open questions). | C |
| 2026-10-27 | Result C triggers an internal notification only, no automated pitch. | C |
| 2026-10-27 | Repo lives at github.com/ssjennings1/decision-tree-check (Shannon created it; pushed same day). | S |

## Open questions for Shannon

1. Name: "The Decision Tree Check" vs. "What Landed on Your Desk?" vs. something of yours.
2. Seed opt-in: Yes/No defaulting to No, or a disclosed auto-subscribe line ("You'll also get the Saturday Seed; unsubscribe any time")?
3. Q1 and Q8 are branch-level in your own examples; keep them, or swap for the leaf-level alternatives in the spec?
4. Result A: show the 15-minute booking button or not?
5. Do you want the old `scotoma-spotter` repo archived once the redirect is live?
