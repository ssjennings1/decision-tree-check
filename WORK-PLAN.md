# Decision Tree Check — Work Plan

**What this is:** A lead-generation quiz for Syncovate, built to run on Taft's (GoHighLevel) native Quiz Builder. It replaces the Scotoma Spotter (spotter.syncovatellc.com, repo `ssjennings1/scotoma-spotter`), which was built to sell a diagnostic offer that no longer exists.

**Owner:** Shannon S. Jennings (decisions). **Builder:** Claude (drafts, specs, research, reports).

**How we work:** This file is the source of truth between sessions. Every session ends with the "Where we are" line below updated and a short report in `REPORTS.md` in the same shape: what I did, what I decided on my own, what needs your yes, what's next. Nothing goes live in Taft without a yes. I don't invent frameworks; the model is Shannon's Decision Tree as she teaches it (see `design/decision-tree-model.md`).

---

## Where we are

**2026-10-27 — Stage 2 drafted, Stages 3–6 not started.** Waiting on Shannon's review of `design/quiz-spec.md` and `copy/`. See `REPORTS.md` for the first report and the open questions.

---

## Stages

| # | Stage | Who | Status | Gate |
|---|-------|-----|--------|------|
| 0 | Pick the concept | Shannon | **Done** — Decision Tree Check (2026-10-27) | — |
| 1 | Research: model validity + quiz practice + Taft quiz capabilities | Claude | **Done** — `research/` | None |
| 2 | Design: questions, scoring, result tiers, result copy, emails | Claude | **Drafted** | Shannon approves copy |
| 3 | Taft assets buildable by API: tags, custom fields, email templates | Claude | Not started | None (reversible); Shannon said "not yet" on API for now |
| 4 | Taft assets needing a browser: the quiz, the workflow, the page | Shannon or Claude-in-Chrome with Shannon present | Not started | Shannon in the room |
| 5 | Landing page + redirect: point spotter.syncovatellc.com at the new page, archive old GitHub Pages site | Claude drafts, Shannon pastes/flips | Not started | Shannon flips |
| 6 | Test + ship: take the quiz as a test contact, verify tag → email → Seed handoff | Claude | Not started | Shannon says "live" |

## Repo map

- `WORK-PLAN.md` — this file
- `REPORTS.md` — session reports, newest first
- `DECISIONS.md` — decisions made and by whom
- `research/` — research memos with sources
- `design/decision-tree-model.md` — the model, canonical wording
- `design/quiz-spec.md` — questions, answers, points, tiers, data fields
- `copy/result-pages.md` — the three result screens
- `copy/emails.md` — result email + follow-up email, in Dr. J's voice
- `copy/landing-page.md` — page copy for the quiz page
- `taft/build-spec.md` — click-by-click build instructions for the Quiz Builder, custom fields, tags, workflow
- `taft/workflow-ai-prompt.md` — the prompt to paste into Taft's workflow AI builder

## Rules carried in from Shannon's brand

- Plain language. Litmus test: a second-generation contractor in Elkhart follows it on his phone on a Saturday.
- No negging. Name the situation, never the person's inadequacy.
- No em dashes in email body copy (GHL plain-text fallback). No "genuinely," "honestly," "actually," "truly," "bandwidth," "nobody ever taught you."
- Never sign off "Warmly."
- "Put into play Monday" is the promise.
- Credit the Decision Tree as inspired by Susan Scott's work at Fierce, grown a lot in Shannon's hands since.
- No diagnostic-purchase machinery. This is a gift that earns a Seed subscriber, not a funnel to a paid scan.
