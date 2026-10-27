# Research memo: Taft (GoHighLevel) Quiz Builder capabilities and quiz lead-magnet practice

Prepared 2026-10-27 from GoHighLevel's official help docs and quiz-platform practitioner data. Paraphrased; sources at the end. Items marked **unconfirmed** need a test in the builder.

## A. What the Taft Quiz Builder can do (Sites → Quizzes)

**Question types.** Single choice, multiple choice, yes/no, short and long answer, number, dropdowns, plus personal-info fields (name, validated email, phone), display-only text and image, HTML, a T&C checkbox, and any contact custom field via "Add Object Fields." No stated cap on questions or pages. Multiple elements per page are allowed.

**Points per answer.** Yes. Single choice: one score per answer.

**Category scoring.** Yes, native. Categories are created in "Manage Categories"; each answer is assigned to one or more categories (or "Overall Only"). Each category is scored as a percentage of its own maximum, so uneven category sizes are fine. The result page can show the Highest (or Lowest) category with its own custom headline, body, image and CTA, and merge tags `{{quiz_tags.highest_category_name}}` and `{{quiz_tags.highest_category_score}}` are available. **Unconfirmed: tie-breaking.** Design the point tables so ties are rare, and test tied cases.

**Result tiers by score range.** Yes. Overall Score section supports tiers (e.g. 0–30%, 31–65%, 66–100%) with a message and optional CTA per tier. Score can display as percentage, raw score, or out of 10. Watch the boundaries (30 vs 31) and test edge scores.

**Result page.** Sections: header (logo, title, colors), overall score, category breakdown, individual category (headline, body, image/video, CTA), a CTA button (funnel page, calendar, or URL), footer. Images in templates can be toggled and moved but not freely replaced. **No redirect-by-result**; a result only leads somewhere via a button the taker clicks. The generic "On Submit" message/redirect setting is shared with forms and its interaction with the quiz results page is **unconfirmed**.

**Opt-in placement.** There is no separate lead-capture step. Name and email are ordinary elements placed on any page. The results page is the final step after submit, so a required email on the last question page gates the result. Whether an anonymous submission creates a usable contact is **unconfirmed**; make email required.

**Storage on the contact.** Results Template → Settings → Custom Fields lets you sync overall score (number), overall tier (text), per-category scores and tiers, and highest/lowest category name and score. Fields are auto-created on first submission, named like "[Quiz name] - Overall Score," live on the contact, overwrite on retake, and drive workflows and smart lists. Mapping an individual answer to a field only happens if that question is an Object Field element.

**Workflow trigger.** "Quiz Submitted" fires immediately, with filters on quiz name, overall score (comparisons, inclusive Between), category score, and custom field. **Unconfirmed:** quiz-specific merge fields inside the workflow beyond the synced custom fields; use the synced fields in emails.

**Embedding.** "Integrate" gives an iframe embed code for a Code/Custom HTML element on a site page, or a standalone link for email and social. No native drag-in quiz element.

**Branching.** Option-level "Jump To" skip logic exists; score-based page branching does not.

## B. Quiz lead-magnet practice

**Length.** Interact benchmarks 13 questions for scored quizzes, 7 for branching, and recommends 7–10 in its checklist; Landerlab and Jotform converge on 5–10 and two to three minutes. None are controlled studies. Too few questions make the result feel untrustworthy; every question that doesn't sharpen the result adds drop-off. Ten is a defensible target.

**Benchmarks (vendor, observational).** Interact's 2026 report: 65% of starters finish, 40% of starters become leads; service providers 47% / 42%. Riddle reports a 41% average opt-in. Traffic source is the biggest driver: visitors from your own site and list convert far better than ads or cold traffic.

**Opt-in placement.** Dominant practice is after the last question, before the result, framed as "send my result." First name and email only. Copy that says what they get and how often you'll email. Single-field forms beat name+email by 12–18 points in generic survey data, but first name is worth it for the emails.

**Result page.** Title that answers the quiz's question; 75–150 words in short beats: positive overview in "you" language, what it means, an easy win, then the relevant offer; a short bio; one CTA. Copy varies by tier.

**Writing questions as self-discovery.** Questions in the host's voice, answers in the taker's voice. Situations they recognize, not self-ratings. Open with an easy one. Keep qualifier questions (team size) few and late, or capture them as fields rather than dressing them up as insight questions.

**Archetype vs. score.** Archetype (named result) formats get the highest engagement and segment cleanly; scorecards suit "health check" positioning. GHL supports both at once: overall tier for the headline, highest category for the personalized line. That hybrid is what the spec uses.

**Follow-up sequence.** Email 1 immediately, varied by result: restate the result, deliver the promised piece, one reply ask. Email 2 one to three days later: a story tied back to the reader. Only email 1 must vary per result.

## What this changes in the spec

1. Drop the self-report "which lands on your desk most" question. Native category scoring across the ten situations gives the heaviest branch automatically, and it's more honest than self-report.
2. Result tiers are set as percentages in the builder: A 0–30%, B 31–65%, C 66–100% (of 40 points).
3. Result tags are applied by the workflow (If/Else on overall score or overall tier field), not by the quiz.
4. Email merge fields use the auto-synced custom fields, e.g. `{{contact.the_decision_tree_check__highest_category_name}}` (exact key confirmed at build).
5. Opt-in = required First Name + Email elements on the last question page. Seed opt-in = a Yes/No question on the same page, mapped to a custom field, tagged by the workflow.

## Sources
- GHL Quiz Builder Guide: https://help.gohighlevel.com/support/solutions/articles/155000004126-quiz-builder-guide
- GHL scoring, categories and result pages: https://help.gohighlevel.com/support/solutions/articles/155000004750-how-to-set-up-quiz-scoring-categories-and-result-pages
- GHL personality-style quizzes (highest/lowest category): https://help.gohighlevel.com/support/solutions/articles/155000006492-setting-up-personality-style-quizzes-highest-lowest-category-
- GHL individual category personalization: https://help.gohighlevel.com/support/solutions/articles/155000008035-individual-category-result-personalization-for-personality-quizzes
- GHL map quiz results to custom fields: https://help.gohighlevel.com/support/solutions/articles/155000006913-map-quiz-results-directly-to-crm-custom-fields
- GHL Quiz Submitted trigger: https://help.gohighlevel.com/en/support/solutions/articles/155000004437
- GHL on-submit message customisation: https://help.gohighlevel.com/support/solutions/articles/155000007202-forms-surveys-quizzes-on-submit-message-customisation
- GHL changelog, category scoring: https://ideas.gohighlevel.com/changelog/quiz-enhancements-smarter-category-scoring-dynamic-results
- GHL changelog, custom category content: https://ideas.gohighlevel.com/changelog/custom-category-content-for-quiz-results
- Open request, redirect by result: https://ideas.gohighlevel.com/quizzes/p/add-conditionredirect-to-url-in-the-quizz-builder
- Embedding a quiz on a funnel: https://mycrmsupport.helpjuice.com/en_US/how-to-embed-a-quiz-on-your-funnel
- Growthable quiz builder overview: https://growthable.io/blogs/quiz-builder-in-gohighlevel/
- Consultevo, Quiz Submitted workflow: https://consultevo.com/gohighlevel-quiz-submitted-workflow-trigger/
- Interact conversion report: https://tryinteract.com/blog/quiz-conversion-rate-report/
- Interact question count: https://help.tryinteract.com/en/articles/10752954-how-many-questions-should-my-quiz-have-to-maximize-conversions
- Interact lead capture practice: https://help.tryinteract.com/en/articles/4144101-best-practices-for-setting-up-quiz-lead-capture-forms
- Interact email sequences: https://info.tryinteract.com/quiz-course-write-quiz-email-sequences
- Jotform quiz lead magnet: https://www.jotform.com/blog/how-to-create-a-quiz-as-a-lead-magnet/
- Landerlab quiz funnel questions: https://landerlab.io/blog/quiz-funnel-questions
- Lean Marketing scorecards: https://leanmarketing.com/post/how-to-attract-the-best-clients-using-scorecard-marketing
