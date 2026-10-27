# Taft build spec — The Decision Tree Check ("What Landed on Your Desk Last Week?")

Click-by-click instructions for building the quiz in Taft (GoHighLevel). Written so Shannon can build it herself, or Claude can drive it in Chrome with Shannon present. Nothing here is done by API: quizzes, result pages and workflows have no API endpoints. Email templates, custom fields and tags can be created by API in Stage 3 if Shannon green-lights it; otherwise they're built here too.

Order matters: fields → email templates → quiz → workflow → page → test.

Login: app.taftsystems.com (location: Syncovate).

---

## 1. Custom fields (Settings → Custom Fields)

Create two fields in a folder called "Decision Tree Check":

| Name | Type | Options |
|------|------|---------|
| Company Size | Dropdown (single) | Under 10 / 10–25 / 26–75 / 76–200 / 200+ |
| Seed Opt-in | Radio or Dropdown | Yes / No |

Both: "Show in forms" on. (The three result fields are auto-created by the quiz later; don't make them by hand.)

Check first: a company-size field may already exist from the Saturday Seed form or other forms. Reuse it if so.

## 2. Tags

Create or confirm: `decision-tree-check`, `dt-result-a`, `dt-result-b`, `dt-result-c`. Confirm the exact Saturday Seed source tag by opening the "Saturday Seed – Welcome Sequence" workflow (id 2da7a557-83f4-4600-9bfd-1616172f77f9) and reading its trigger. Write it here: `________`.

## 3. Email templates (Marketing → Emails → Templates)

Five templates, html editor, plain personal look (Verdana, no header art, gold #BF8756 links, Dr. J signature block). Bodies in `copy/emails.md`. Names must match exactly; the workflow prompt refers to them by name.

| Template name | Subject | Preview |
|---------------|---------|---------|
| DT Result A – The Shade Tree | You're a Shade Tree | Desk Load NN of 40. Here's the one move. |
| DT Result B – The Switchboard | You're a Switchboard | Desk Load NN of 40. Here's the one move. |
| DT Result C – The Builder | You're a Builder | Desk Load NN of 40. Here's the one move. |
| DT Follow-up – Which one did you hand back | Which one did you hand back? | A quick follow-up on your Decision Tree Check. |
| DT Follow-up – Which one did you hand back (Seed subscriber) | Which one did you hand back? | A quick follow-up on your Decision Tree Check. |

Merge field for the heaviest branch: open the custom-values picker in the editor AFTER the quiz has had one test submission (Step 6), because the field doesn't exist until then. Insert it where the copy says `{{contact.the_decision_tree_check_highest_category_name}}`. Until then, leave the placeholder text in.

## 4. The quiz (Sites → Quizzes → + New Quiz)

**Name:** The Decision Tree Check. (Door title "What landed on your desk last week?" goes on the intro page and the landing page; the quiz name stays "The Decision Tree Check" because it prefixes the custom fields.) Theme: cream background #FAF8F5, gold #BF8756 buttons, charcoal #252830 text. Fonts as close to Cormorant Garamond / DM Sans as the builder offers.

**Manage Categories:** create People, Customers, Money, Operations.

**Page 1 (intro):** Text element with the Screen 1 copy from `design/quiz-spec.md`. Button: Start.

**Pages 2–11 (one situation per page):**
- Text element: the situation sentence.
- Single Choice question, label: "Last time this happened, where did it land?" Required.
- Five options, in this order, with scores 0, 1, 2, 3, 4:
  1. Never heard about it. Somebody handled it.
  2. Handled. Then they told me.
  3. They checked with me first.
  4. We hashed it out together.
  5. Came to me. I made the call.
- Assign every option on the page to the page's category (People / Customers / Money / Operations per the table in the spec). Do not use "Overall Only."
- Tip: build page 2 fully, then duplicate the page nine times and change only the situation text and the category.

Situations and categories (from `design/quiz-spec.md`):
1. A customer calls to ask when their order will be ready. (Customers)
2. Two people on a crew or shift want to swap days. (People)
3. A tool breaks and needs replacing. A few hundred bucks, not a few thousand. (Money)
4. A supplier says a delivery is going to be a day late. (Operations)
5. Somebody asks for next Friday off. (People)
6. A regular customer asks if you can squeeze in a rush job. (Customers)
7. Somebody catches a quality problem before it goes out the door. (Operations)
8. A crew needs to know which job to start first tomorrow. (People)
9. A software renewal or a small recurring bill comes due. (Money)
10. A new hire's first week needs a plan. (Operations)

**Page 12 (opt-in):**
- Text: "Your result's ready." + body copy from the spec.
- First Name element, required. Email element, required.
- Object Field: Company Size (dropdown).
- Object Field: Seed Opt-in, label "Also send me the Saturday Seed, one leadership idea a week you can put into play Monday." Default No.
- Text (small): No spam. Unsubscribe any time.
- Submit button text: Show me.

**Results template (Results → Edit Template):**
- Header: Syncovate wordmark, title "Your Decision Tree Check."
- Overall Score display ON, format "actual score", labeled "Desk Load" (out of 40).
- Overall Score section: tiers as percentages. A: 0–30. B: 31–65. C: 66–100. Tier labels exactly "The Shade Tree", "The Switchboard", "The Builder" (these become the Overall Tier field values the workflow branches on, and the headline the taker sees). Tier message = the matching result copy from `copy/result-pages.md`.
- Category Score breakdown: off (it would show four percentages and turn the result into a report card).
- Individual Category section: display Highest. One short line per category, e.g. People: "Right now the heaviest branch is people: schedules, time off, who does what, disagreements." Same pattern for Customers, Money, Operations using the category wording in the spec.
- CTA button on every tier: "Book 15 minutes with Dr. J" → https://link.syncovatellc.com/widget/bookings/book-a-15-min-clarity-call. Second link in the body text: "Send this to an owner you know" (mailto, see `copy/result-pages.md`).
- Footer: syncovatellc.com, LinkedIn.
- Settings → Custom Fields: turn ON sync for Overall Score, Overall Tier, Highest Category Name. Leave the rest off.

**On Submit setting:** Message (not Redirect), so the results page shows. Confirm in a test; this interaction is undocumented.

**Save. Do not publish the page link anywhere yet.**

## 5. Workflow

Paste `taft/workflow-ai-prompt.md` into a new workflow's AI Build box, then do the hand checks listed at the bottom of that file. Leave it in draft.

## 6. First test submission (creates the result fields)

Open the quiz's direct link (Integrate → link). Take it as a test contact (e.g. test+dt@syncovatellc.com) answering all "It came to me, and I decided" → expect tier C. Check the contact: three new fields should exist with values 40 / C / (highest category; with all-4s every category ties at 100%, so note what the builder picked). Now go back to the five email templates and insert the real merge field for Highest Category Name.

Then two more tests: all first answers (expect A, score 0) and a mix landing at 20 (expect B). Test a tie on purpose: answer 4 on both Customers questions and 4 on both Money questions, 0 elsewhere; note which category wins.

## 7. Page (Sites → Websites → the live Syncovate 2026 site)

New page at `/desk` from the sandbox page style. Copy in `copy/landing-page.md`. Quiz embedded via Integrate → embed code pasted into a Custom HTML / Code element under the hero, or the hero button links to the quiz's direct link (simpler, and the quiz page is already mobile-friendly). Recommendation: button to the direct link first; embed later if the bounce is high.

Add `/desk` to the footer under Writing / Resources once it's live.

## 8. Redirect and retire the old tool

- Taft: create redirect `spotter.syncovatellc.com/*` → `https://syncovatellc.com/desk` (API `create-redirect` works, or Sites → Redirects).
- DNS: `spotter` currently CNAMEs to GitHub Pages. Repoint it to Taft per Taft's domain instructions, or drop the subdomain entirely and let the GitHub Pages site go dark (nothing links to it today).
- GitHub: remove `CNAME` from `ssjennings1/scotoma-spotter` and archive the repo.

## 9. Publish checklist

- [ ] Workflow published, test contact got Email 1 within a minute and Email 2 three days later at 8 AM
- [ ] Result C test triggered the internal notification to Shannon
- [ ] Seed opt-in test contact got the Seed source tag and entered the Seed welcome sequence (and did NOT get the Seed paragraph in Email 2)
- [ ] Test contacts deleted
- [ ] Page live on phone and desktop, button works, result page shows the right tier and category
- [ ] Redirect from spotter.syncovatellc.com works
