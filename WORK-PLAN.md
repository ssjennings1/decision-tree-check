# Decision Tree Check — Work Plan

**What this is:** A lead-generation quiz for Syncovate, built to run on Taft's (GoHighLevel) native Quiz Builder. It replaces the Scotoma Spotter (spotter.syncovatellc.com, repo `ssjennings1/scotoma-spotter`), which was built to sell a diagnostic offer that no longer exists.

**Owner:** Shannon S. Jennings (decisions). **Builder:** Claude (drafts, specs, research, reports).

**How we work:** This file is the source of truth between sessions. Every session ends with the "Where we are" line below updated and a short report in `REPORTS.md` in the same shape: what I did, what I decided on my own, what needs your yes, what's next. Nothing goes live in Taft without a yes. I don't invent frameworks; the model is Shannon's Decision Tree as she teaches it (see `design/decision-tree-model.md`).

---

## Where we are

**2026-10-27 (afternoon) — Experimental run complete. Stages 1, 2 and 7 done; Stages 3–6 ready to run on Shannon's yes.** All open decisions were made by Claude (see `DECISIONS.md`). A clickable prototype of the full flow is published as a private artifact and saved at `prototype/index.html`. Launch plan and ready-to-send copy are in `strategy/`. Nothing is live in Taft. Shannon tests the prototype and reads `REPORTS.md`.

---

## Stages

| # | Stage | Who | Status | Gate |
|---|-------|-----|--------|------|
| 0 | Pick the concept | Shannon | **Done** — Decision Tree Check (2026-10-27) | — |
| 1 | Research: model validity, quiz practice, Taft quiz capabilities, engagement/titles, 2026 lead-gen landscape | Claude | **Done** — `research/` (4 memos) | None |
| 2 | Design: questions, scoring, result patterns, result copy, emails, landing page, clickable prototype | Claude | **Done** (gut-check tone) | Shannon tests the prototype |
| 3 | Taft assets buildable by API: tags, custom fields, email templates | Claude | Not started | None (reversible); Shannon said "not yet" on API for now |
| 4 | Taft assets needing a browser: the quiz, the workflow, the page | Shannon or Claude-in-Chrome with Shannon present | Not started | Shannon in the room |
| 5 | Landing page + redirect: point spotter.syncovatellc.com at the new page, archive old GitHub Pages site | Claude drafts, Shannon pastes/flips | Not started | Shannon flips |
| 6 | Test + ship: take the quiz as a test contact, verify tag → email → Seed handoff | Claude | Not started | Shannon says "live" |
| 7 | Launch strategy + kit: timeline, metrics, kill criteria, list email, partner paragraph, QR slide, LinkedIn doc and poll, evergreen lines | Claude | **Done** — `strategy/` | Shannon sends |

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
- `prototype/index.html` — the clickable prototype (also published as a private artifact)
- `strategy/launch-plan.md` — timeline, metrics, kill criteria, version two
- `strategy/launch-kit.md` — every piece of launch copy, ready to send

## Rules carried in from Shannon's brand

- Plain language. Litmus test: a second-generation contractor in Elkhart follows it on his phone on a Saturday.
- No negging. Name the situation, never the person's inadequacy.
- No em dashes in email body copy (GHL plain-text fallback). No "genuinely," "honestly," "actually," "truly," "bandwidth," "nobody ever taught you."
- Never sign off "Warmly."
- "Put into play Monday" is the promise.
- Credit the Decision Tree as inspired by Susan Scott's work at Fierce, grown a lot in Shannon's hands since.
- No diagnostic-purchase machinery. This is a gift that earns a Seed subscriber, not a funnel to a paid scan.
