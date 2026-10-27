# Reports

Newest first. Same shape every time: what I did, what I decided on my own, what needs your yes, what's next.

---

## 2026-10-27 (evening) — Session 3: design v2 and the old build

This one came out of you thinking out loud, so the design is yours; I built it.

**What changed and why**
- The ten-question, five-answer quiz is gone. In its place: eighteen things that happen in every company, across all five levels of the tree, and you tap what landed on your desk. The big-stuff items are yes/no so a "no" can count.
- Size and role are asked last, with your line about the map looking different at five people than at twenty-five.
- The score is fit, not volume. A Builder at eight people with everything on the desk is on track. The same desk at sixty is the finding.
- Three stages: Builder, Stretching, Architect. Three fit states: on track, weight climbing, roots drifting. One green flag and one red flag, personalized. One Move for Monday. Team members, managers and family members get their own read, so the owner can send it to the team and compare trees.
- Mechanism: Taft survey with scored redirect to designed pages, plus a workflow. That's what your contractor built; we keep the mechanism and none of the content. The Quiz Builder is out because its results page can't react to role or size; the custom-page webhook route is in reserve.

**What I built**
- `design/quiz-spec.md` v2: the items, the expected-desk matrix (role × stage), the fit rules, the flag logic.
- `copy/result-pages.md` v2: eight owner pages, three team pages, manager and family variants, and the ten flag sentences.
- `copy/emails.md`, `copy/landing-page.md`, `strategy/launch-kit.md`: updated to the new stages and the picture framing.
- `taft/build-spec.md` v2 and `taft/workflow-ai-prompt.md` v2: survey, pages, fields, tags, the workflow's math and branches, nine test cases.
- `prototype/index.html` v2, published: the whole flow with the tree drawn from your answers. It's the reference implementation; the Taft points get tuned to agree with it.
- `research/old-scotoma-spotter-in-taft.md`: what the contractor built, what we keep (mechanism, size and role, "Builder"), what we drop, what to retire.

**What I decided on my own**
- Size thresholds for the stages: under 10, 10–40, 41+. Guesses; the copy says gut check.
- Start with three result pages (by state) with the stage merged in, and only build eleven if the page merge doesn't render.
- Kept the no-negging rule at the level of every flag sentence; a red flag names the situation, never the person.

**What I need from you**
- Take the prototype three times: as an owner at 8 people with everything on your desk, as an owner at 30 who's handed off the small stuff, and as a team lead. Tell me where the picture or the words are wrong.
- Ten minutes in Taft: open the old survey's settings and confirm the survey builder scores per answer and redirects by score. That decides whether the build is as clean as the spec says.

**Still not done**
- Nothing in Taft. Stage 3 by API is ready. Stage 4 needs you present.
- The three stage illustrations (Builder / Stretching / Architect trees) don't exist yet. Your call whether that's Claude Design, Canva, or an illustrator.

---

## 2026-10-27 (afternoon) — Session 2: the experimental run

Shannon's brief: make every call, nothing goes live, deliver a fully functioning, ready-to-launch tool and strategy. Fun, interactive, useful, a gut check not a scientific tool.

**What I built**
- A clickable prototype of the whole flow (door, ten questions, opt-in page, result with Desk Load, heaviest branch, pattern, One Move, share text). Published privately; file at `prototype/index.html`. It mirrors the Taft build exactly so what you click is what gets built.
- Final copy in the gut-check tone: spec, three result pages, five emails plus a personal note for Builders, landing page.
- The launch strategy (`strategy/launch-plan.md`): list first, partners second, DisruptHR QR third, LinkedIn last. Numbers to watch, kill criteria, and what version two would be.
- The launch kit (`strategy/launch-kit.md`): the list email, the partner email with a forwardable paragraph, the QR slide, the scanner thank-you, a LinkedIn carousel, a poll and results post, evergreen lines, and a reply bank for when results come in.
- Two more research memos: titles and engagement, plus your 2026 lead-gen report saved into `research/`.

**The calls I made (all in `DECISIONS.md`)**
- Door title "What Landed on Your Desk Last Week?"; asset name "The Decision Tree Check"; slug `/desk`.
- Show the score (Desk Load, NN of 40) AND name the pattern.
- Pattern names: The Shade Tree, The Switchboard, The Builder. The highest-load result gets the most flattering name on purpose.
- Seed opt-in defaults to No. Q1 and Q8 swapped. Booking button on all results. Builders get a personal note from you within 24 hours (drafted).
- Scope stays narrow; the four-dimension version is v2.
- Launch tied to DisruptHR.

**What I'd want you to check first**
1. Take the prototype on your phone. Answer as a client you know. Does the result sound like something you'd say to them?
2. The three pattern names. They're mine; you may have better words from the room.
3. The partner email. That one goes out under your name to people whose trust the practice runs on.

**What I didn't do**
- Anything in Taft. Stages 3–6 are specified click by click and ready.
- Confirm Taft's category tie-break or the On Submit / results-page interaction. Both are test steps in the build spec.

**What's next, if you say go**
- Stage 3 by API (tags, fields, five email templates): about an hour, reversible.
- Stage 4 in the browser with you present (the quiz, the result template, the workflow): about two hours.
- Then the launch plan runs on your calendar.

---

## 2026-10-27 — Session 1: research and design

**What I did**
- Set up the repo and the work plan (six stages, gates marked).
- Pulled your current Decision Tree wording (the Oct 26 Seed welcome Email 2 version with the Susan Scott credit) into `design/decision-tree-model.md`.
- Ran two research passes. The model holds up: Bain's RAPID, McKinsey's decision taxonomy, HBR's "monkey" article, Greiner's growth crises and the Edward Lowe second-stage research all say the same thing the tree says. Taft's Quiz Builder does everything the design needs natively: points per answer, category scoring with a highest-category merge tag, score-range tiers, result fields synced to the contact, a Quiz Submitted workflow trigger. Memos in `research/`.
- Drafted the quiz (ten situations, one answer scale, three results), the three result screens, five emails, the landing page copy, the click-by-click Taft build spec, and the workflow AI prompt.

**What I decided on my own (all reversible)**
- Name "The Decision Tree Check" and slug `/decision-tree`.
- The heaviest branch comes from category scoring across the ten answers, not from asking. The research showed the builder supports it, and it's more honest than self-report.
- Seed opt-in is a Yes/No defaulting to No. My reasoning: people who say yes stay subscribed, and your Seed list is worth protecting. It will cost subscribers versus auto-enrolling.
- Result C sends you a notification and nothing else. No automated pitch on the highest-need result.
- No stats on the landing page. The audience trusts the story more than McKinsey.

**What needs your yes**
- The copy: `design/quiz-spec.md`, `copy/result-pages.md`, `copy/emails.md`, `copy/landing-page.md`. Mark it up however you like; I'll fold it in.
- The six open questions in `DECISIONS.md`. Name, Seed opt-in, two borderline questions, the Result A button, archiving the old repo, and creating the GitHub repo.

**What I couldn't do**
- (Resolved 09:10) Pushed to github.com/ssjennings1/decision-tree-check once Shannon created the repo.
- Confirm two Taft details that aren't documented: how category ties break, and whether the generic "On Submit" setting interferes with the results page. Both are in the build spec as test steps.

**What's next**
- You review and answer the open questions.
- Stage 3 (tags, fields, email templates by API) is ready to run the moment you say so. Stage 4 (the quiz and workflow in the browser) needs you present.
