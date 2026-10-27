# Reports

Newest first. Same shape every time: what I did, what I decided on my own, what needs your yes, what's next.

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
