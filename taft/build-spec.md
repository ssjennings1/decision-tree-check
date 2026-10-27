# Taft build spec v2 — survey → scored redirect → designed pages → workflow

The mechanism the 2026 contractor build used, with none of its content. Nothing here is done by API except where marked; surveys, pages and workflows are built in the browser. Shannon builds, or Claude drives Chrome with Shannon present.

Order: custom fields → tags → email templates → result pages → survey → workflow → test → redirect and retire.

Login: app.taftsystems.com. Location yCTzggMS1VT4xrqF3lML.

**Verify first (10 minutes, Shannon):** open Surveys → the old "Scotoma Spotter™" survey → Settings, and confirm the survey builder has (a) a score/points value per answer option and (b) "redirect by score range" (the old build routed on "Score less than 30," so it should). If scoring per answer is missing, the fallback is the Quiz Builder for scoring plus its results page (see `research/quiz-practice.md`), and the designed pages become the email instead.

---

## 1. Custom fields (API-able; folder "Decision Tree Check")

| Field | Type | Notes |
|-------|------|-------|
| dt_item_01 … dt_item_25 | Yes/No (radio) | one per item, mapped from the survey; "Yes" = landed on my desk |
| dt_company_size | Dropdown | Under 10 / 10–25 / 26–40 / 41–100 / 100+ |
| dt_role | Dropdown | Owner / Leadership team / Manager / Family member |
| dt_stage | Text | Builder / Stretching / Architect (workflow writes) |
| dt_state | Text | ok / climb / drift (workflow writes) |
| dt_leaf, dt_branch, dt_limb, dt_trunk, dt_root | Number | items lit per level (workflow Math Operation) |
| dt_green_flag, dt_red_flag | Text (long) | workflow writes the flag sentence |
| seed_optin | Yes/No | from the opt-in page |

Check first whether a company-size field already exists (Saturday Seed form); reuse if so.

## 2. Tags (API-able)

`decision-tree-check`, `dt-stage-builder`, `dt-stage-stretching`, `dt-stage-architect`, `dt-state-ok`, `dt-state-climb`, `dt-state-drift`, `dt-role-owner`, `dt-role-lead`, `dt-role-mgr`, `dt-role-fam`. Plus the Saturday Seed source tag (read it from the "Saturday Seed – Welcome Sequence" workflow trigger; write it here: `________`).

## 3. Email templates (API-able; names exact)

| Template | Subject |
|----------|---------|
| DT Result – Owner | Your desk, on the tree |
| DT Result – Leadership team | Your desk, on the tree |
| DT Result – Manager | Your desk, on the tree |
| DT Follow-up – Which one did you hand back | Which one did you hand back? |
| DT Follow-up – Which one did you hand back (Seed subscriber) | Which one did you hand back? |
| DT Event – Thanks for scanning | The one idea from today |

Bodies in `copy/emails.md`. The result emails merge `{{contact.dt_stage}}`, `{{contact.dt_state}}` copy blocks (via If/Else in the workflow or three owner variants), `{{contact.dt_green_flag}}`, `{{contact.dt_red_flag}}`.

## 4. Result pages (Sites → Websites → Syncovate 2026 → Add new page)

Eleven pages, all under `/desk/`: `builder-on-track`, `builder-drifting`, `stretching-on-track`, `stretching-climbing`, `stretching-drifting`, `architect-on-track`, `architect-climbing`, `architect-drifting`, `team-on-track`, `team-climbing`, `team-drifting`. Copy in `copy/result-pages.md`. Build one from the sandbox page style, then duplicate ten times and swap headline, paragraph, tree image, One Move.

Each page: Syncovate header · eyebrow "The Decision Tree Check" · H1 (the stage line) · `{{contact.first_name}}` intro · the tree illustration for that stage (three illustrations: Builder = full tree lit gold; Stretching = leaves fading, mid-tree gold; Architect = canopy quiet, trunk and roots gold; Shannon makes these in Claude Design or Canva from the prototype's layout) · green flag and red flag (merge `{{contact.dt_green_flag}}` / `{{contact.dt_red_flag}}`; if custom-field merge doesn't render on pages, the workflow redirects with `?g=…&r=…` URL params and a small page script shows them, or the flags live only in the email) · One Move · two buttons · credit line · footer. No nav to Services/About; this page has one job.

Set every page to noindex.

## 5. The survey (Sites → Surveys → + New Survey)

**Name:** The Decision Tree Check. Theme: cream, gold button, Cormorant/DM Sans as available.

**Slide 1 (door text):** "What landed on your desk last week?" + the two lines from the spec. Button: Let's see.

**Slides 2–4 (People / Customers / Money and operations):** one Checkbox (multi-select) question per slide, label as in the spec ("Tap every decision that landed on you last week."), options = the items for that screen. Per-option points (if the builder scores checkbox options individually): Leaf +2, Branch +2, Limb +1. Map each option to its dt_item field (if the builder maps a checkbox question to a single field, map the whole question to a text field and let the workflow parse; see §7 alternative).

**Slides 5–6 (The big stuff / The really big stuff):** eleven Radio questions, "Did this decision come to you?" Yes/No. Points: Trunk items Yes 0 / No +2; Root items Yes 0 / No +3. Map each to its dt_item field.

**Slide 7 (size and role):** text block with the "map looks different" line. Dropdown company size → dt_company_size, with points: Under 10 −10, 10–25 −4, 26–40 −2, 41–100 0, 100+ 0. Radio role → dt_role, with points: Owner 0, Leadership team −2, Manager −6, Family member −2. (These are starting values; tune against the prototype and the §8 cases. With ten big-stuff items the drifting points are larger than before, so expect to lower the "No" points to +1 / +2.)

**Slide 8 (opt-in):** "Your picture's ready." First Name (required), Email (required), Seed opt-in radio Yes/No default No → seed_optin. Submit: Show me.

**Scoring and redirect (Settings):** with the points above, the total approximates fit: strongly negative = roots drifting, around zero = on track, positive = weight climbing. Bands to start: ≤ −6 → drifting page; −5 to 5 → on-track page; ≥ 6 → climbing page. Redirect targets are role-and-stage-specific, so if the survey only supports score→URL, redirect to a single `/desk/result` page whose workflow-set custom fields drive the content, OR use three redirect bands and let the page merge the stage name. The cleanest version is: survey redirects by score band to `/desk/{state}`, and that page shows `{{contact.dt_stage}}` in its headline. Three pages instead of eleven. **Recommendation: start with three pages (on track / climbing / drifting) with the stage merged in, and expand to eleven only if the merge doesn't render.**

Tune the points against the prototype using the test cases in §8 before publishing.

## 6. The workflow ("Decision Tree Check – Results")

Trigger: Survey Submitted, survey = The Decision Tree Check.
1. Add tag `decision-tree-check`.
2. If/Else on dt_company_size → Update field dt_stage (Builder / Stretching / Architect) + stage tag.
3. If/Else on dt_role → role tag.
4. Math Operation steps: dt_leaf = count of Yes across the five leaf items (one Math step per item adding 1 if Yes; GHL's Math Operation adds to a number field), same for branch, limb, trunk, root.
5. If/Else tree on role, stage and the five level counts → Update field dt_state, dt_green_flag, dt_red_flag using the sentences in `copy/result-pages.md` (flag lines). This is the longest part of the build; the AI builder prompt in `taft/workflow-ai-prompt.md` lays out the branches.
6. Send Email: DT Result – Owner / Leadership team / Manager by role.
7. Owner + state climb or drift → Internal Notification to Shannon (particular user) + Task "Send personal note within 24h" with the Email 3 draft.
8. Wait 3 days → wait until Mon–Thu 8 AM → If seed_optin = Yes: send the Seed-subscriber follow-up + add the Seed source tag; else send the standard follow-up.

## 7. Alternative if checkbox options can't map to individual fields

Ask every item as its own Yes/No radio (18 short slides, or 4 slides of 4–6 radios). Slower by 20 seconds, perfectly mappable, and the "No" answers on big-stuff items carry points. If this is the case, use it everywhere for consistency.

## 8. Test cases (take the survey as test contacts; compare to the prototype)

| Case | Size | Role | Taps | Expect |
|------|------|------|------|--------|
| Builder all on | Under 10 | Owner | everything Yes | Builder, on track |
| Stretch everything | 26–40 | Owner | everything Yes | Stretching, climbing |
| Stretch ideal | 26–40 | Owner | limb, trunk, root only | Stretching, on track |
| Stretch out of the weeds | 26–40 | Owner | limb only | Stretching, drifting |
| Architect ideal | 41–100 | Owner | trunk, root only | Architect, on track |
| Architect everything | 100+ | Owner | everything | Architect, climbing |
| Lead ideal | 26–40 | Leadership | branch, limb, trunk | Team, on track |
| Lead buried | 26–40 | Leadership | leaf, branch | Team, climbing |
| Mgr ideal | 41–100 | Manager | leaf, branch | Team (manager copy), on track |

Delete test contacts after.

## 9. Redirect and retire

- Redirect `spotter.syncovatellc.com/*` → `https://syncovatellc.com/desk` (API `create-redirect` or Sites → Redirects).
- Unpublish workflow "Scotoma Spotter App" (4f1982ad-…, still published with a live inbound webhook). Rename both old workflows "OLD – DO NOT USE – …".
- Old survey "Scotoma Spotter™" and site "Scotoma Spotter Pages": leave parked, or delete after launch.
- GitHub: remove CNAME from `ssjennings1/scotoma-spotter`, archive the repo.

## 10. Publish checklist

- [ ] All nine test cases land on the right page and the right email
- [ ] Flags render (page or email)
- [ ] Owner climbing/drifting test created the task and notification
- [ ] Seed opt-in test entered the Seed welcome sequence
- [ ] Phone check of every page
- [ ] Old workflows renamed, Scotoma Spotter App unpublished
- [ ] Redirect live
