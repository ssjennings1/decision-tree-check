# Decision Tree Check — Work Plan

**What this is:** A lead-generation quiz for Syncovate, built to run on Taft's (GoHighLevel) native Quiz Builder. It replaces the Scotoma Spotter (spotter.syncovatellc.com, repo `ssjennings1/scotoma-spotter`), which was built to sell a diagnostic offer that no longer exists.

**Owner:** Shannon S. Jennings (decisions). **Builder:** Claude (drafts, specs, research, reports).

**How we work:** This file is the source of truth between sessions. Every session ends with the "Where we are" line below updated and a short report in `REPORTS.md` in the same shape: what I did, what I decided on my own, what needs your yes, what's next. Nothing goes live in Taft without a yes. I don't invent frameworks; the model is Shannon's Decision Tree as she teaches it (see `design/decision-tree-model.md`).

---

## Where we are

**2026-10-27 (evening) — Design v2 built. Stages 1, 2 and 7 done on the v2 design; Stages 3–6 ready to run on Shannon's yes.** v2 came out of an afternoon of ideation with Shannon: a picture not a diagnosis, fit by stage and seat, three stages (Builder / Stretching / Architect), green and red flags. Prototype v2 is published (private artifact) and at `prototype/index.html`; it is the reference implementation of the scoring. The build now runs on Taft's survey → scored redirect → designed pages → workflow, which is the mechanism the 2026 contractor build used (see `research/old-scotoma-spotter-in-taft.md`). Nothing is live. Next: Shannon takes the prototype as three different people (owner at 8, owner at 30, a crew lead), then Stage 3.

---

## Stages

| # | Stage | Who | Status | Gate |
|---|-------|-----|--------|------|
| 0 | Pick the concept | Shannon | **Done** — Decision Tree Check (2026-10-27) | — |
| 1 | Research: model validity, quiz practice, Taft quiz capabilities, engagement/titles, 2026 lead-gen landscape | Claude | **Done** — `research/` (4 memos) | None |
| 2 | Design v2: 18 items across five levels, size and role last, fit by stage and seat, stage × state result pages, flags, emails, landing page, prototype | Claude (direction: Shannon) | **Done** | Shannon tests the prototype |
| 3 | Taft assets buildable by API: custom fields (25), tags (11), six email templates | Claude | Not started | Shannon says go |
| 4 | Taft assets needing a browser: verify survey scoring, build the survey, the result pages, the workflow | Shannon or Claude-in-Chrome with Shannon present | Not started | Shannon in the room |
| 5 | Landing page `/desk` + redirect from spotter.syncovatellc.com; retire old workflows, survey, site and GitHub repo | Claude drafts, Shannon flips | Not started | Shannon flips |
| 6 | Test + ship: take the quiz as a test contact, verify tag → email → Seed handoff | Claude | Not started | Shannon says "live" |
| 7 | Launch strategy + kit: timeline, metrics, kill criteria, list email, partner paragraph, QR slide, LinkedIn doc and poll, evergreen lines | Claude | **Done** — `strategy/` | Shannon sends |

## Repo map

- `WORK-PLAN.md` — this file
- `REPORTS.md` — session reports, newest first
- `DECISIONS.md` — decisions made and by whom
- `research/` — research memos with sources, plus `old-scotoma-spotter-in-taft.md` (what the contractor built, what we keep)
- `design/decision-tree-model.md` — the model, canonical wording
- `design/quiz-spec.md` — v2: the 18 items, the expected-desk matrix, fit rules, flags
- `copy/result-pages.md` — v2: flag lines, eight owner pages, three team pages, manager and family variants
- `copy/emails.md` — result email + follow-up email, in Dr. J's voice
- `copy/landing-page.md` — page copy for the quiz page
- `taft/build-spec.md` — v2: survey → scored redirect → pages → workflow, with test cases
- `taft/workflow-ai-prompt.md` — the prompt to paste into Taft's workflow AI builder
- `prototype/index.html` — prototype v2, the reference implementation of the scoring (also a private artifact)
- `strategy/launch-plan.md` — timeline, metrics, kill criteria, version two
- `strategy/launch-kit.md` — every piece of launch copy, ready to send

## Rules carried in from Shannon's brand

- Plain language. Litmus test: a second-generation contractor in Elkhart follows it on his phone on a Saturday.
- No negging. Name the situation, never the person's inadequacy.
- No em dashes in email body copy (GHL plain-text fallback). No "genuinely," "honestly," "actually," "truly," "bandwidth," "nobody ever taught you."
- Never sign off "Warmly."
- "Put into play Monday" is the promise.
- Credit the Decision Tree as inspired by Susan Scott's work at Fierce, grown a lot in Shannon's hands since. "No Man's Land" is Doug Tatum's; nod to it, don't use it as a stage name.
- Headcount only. Never ask revenue.
- The goal of the tree: clarity, empowerment, development, and a leader's desk with the on-the-business work on it. A picture, not a diagnosis.
- No diagnostic-purchase machinery. This is a gift that earns a Seed subscriber, not a funnel to a paid scan.
