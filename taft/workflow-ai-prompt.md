# Workflow AI builder prompt — "Decision Tree Check – Results" (v2)

Paste into the AI "Build" box on a new workflow canvas. Known quirks (from the Seed welcome build): it sets Send Email subjects to the template NAME (fix by hand); it links templates with "Sync Edits to Template" on (good); it sets internal notifications to "Contact owner" (switch to Particular user → Shannon Jennings). It never publishes on its own.

Prerequisites: custom fields and tags from taft/build-spec.md §1–2 exist; the six email templates exist with the exact names in §3.

---

Build a workflow named "Decision Tree Check – Results".

Trigger: Survey Submitted, filter Survey is "The Decision Tree Check".

Step 1: Add tag "decision-tree-check".

Step 2: If/Else on custom field dt_company_size. "Under 10" → Update field dt_stage = "Builder" and Add tag dt-stage-builder. "10–25" or "26–40" → dt_stage = "Stretching", tag dt-stage-stretching. "41–100" or "100+" → dt_stage = "Architect", tag dt-stage-architect.

Step 3: If/Else on dt_role → Add tag dt-role-owner / dt-role-lead / dt-role-mgr / dt-role-fam.

Step 4: Math Operation steps. For each of dt_item_01 … dt_item_25, if the field is "Yes", add 1 to the matching level counter. Items are numbered by screen in design/quiz-spec.md; within each screen the order is Leaf, Branch, Limb, Trunk, Root, so leaf items are 01, 06, 11, 16, 21 → dt_leaf; branch 02, 07, 12, 17, 22 → dt_branch; limb 03, 08, 13, 18, 23 → dt_limb; trunk 04, 09, 14, 19, 24 → dt_trunk; root 05, 10, 15, 20, 25 → dt_root.

Step 5: Decide dt_state and the flags. Use these rules (climbing = items landing from levels that belong lower; drifting = items missing from levels that belong on this desk):
- Owner + Builder: nothing counts as climbing. drifting = (5 − dt_trunk) + (5 − dt_root) + (5 − dt_limb). If drifting ≥ 2 → dt_state "drift", else "ok".
- Owner + Stretching: climbing = dt_leaf. drifting = (5 − dt_limb) + (5 − dt_trunk) + (5 − dt_root). If climbing ≥ 2 and climbing ≥ drifting → "climb"; else if drifting ≥ 2 → "drift"; else "ok".
- Owner + Architect: climbing = dt_leaf + dt_branch. drifting = (5 − dt_trunk) + (5 − dt_root). Same decision rule.
- Leadership team or Family member: climbing = dt_leaf. drifting = (5 − dt_branch) + (5 − dt_limb) + (5 − dt_trunk). Same rule.
- Manager: climbing = 0. drifting = (5 − dt_leaf) + (5 − dt_branch). Same rule.
Then Add tag dt-state-ok / dt-state-climb / dt-state-drift.
Green flag: for owners at Stretching or Architect, if dt_leaf = 0 set dt_green_flag to the Leaf green line; else if dt_branch = 0 (Architect only) the Branch green line; else the Root green line if dt_root = 5, else the Trunk green line. For Builder owners: Root green line if dt_root = 5, else Trunk, else Limb. For team seats: Leaf green line if dt_leaf = 0, else Branch green line. For managers: Leaf green line.
Red flag: if dt_state = "drift", the drifting line for the level with the most missing items (check Root, then Trunk, then Limb, then Branch). Else if climbing > 0, the holding line for the level with the most landed items among the levels that belong lower (Leaf, then Branch, then Limb). Else if drifting > 0, the drifting line for the most-missing level. Else "Nothing jumped out. Take it again in six months and see what moved." The flag sentences are in copy/result-pages.md under "Flag lines".

Step 6: If/Else on dt_role: Owner → Send Email using template "DT Result – Owner". Leadership team or Family member → "DT Result – Leadership team". Manager → "DT Result – Manager".

Step 7: If dt_role is Owner AND dt_state is "climb" or "drift": Internal Notification by email to a particular user, Shannon Jennings, subject "Desk check: {{contact.first_name}} {{contact.last_name}} ({{contact.dt_stage}}, {{contact.dt_state}})", body with name, email, size, stage, state, red flag, seed opt-in. Then Add Task assigned to Shannon Jennings, due in 1 day, title "Send personal note to {{contact.first_name}}", description = the Email 3 draft in copy/emails.md.

Step 8: Wait 3 days. Wait until Monday–Thursday 8:00 AM America/New_York.

Step 9: If/Else on seed_optin: Yes → Send Email "DT Follow-up – Which one did you hand back (Seed subscriber)", then Add tag [Saturday Seed source tag]. No → Send Email "DT Follow-up – Which one did you hand back".

Settings: allow re-entry yes (people retake it); stop on response no. Do not publish.

---

## Hand checks after it builds
1. Subjects match the templates, not the template names.
2. Internal notification → Particular user → Shannon Jennings.
3. The Seed source tag matches the "Saturday Seed – Welcome Sequence" trigger exactly.
4. Math Operation steps add to a Number field; confirm the fields were created as Number, not Text.
5. Run the nine test cases in build-spec.md §8 with real submissions, not Test Workflow mode.
