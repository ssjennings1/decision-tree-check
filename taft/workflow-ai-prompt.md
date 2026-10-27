# Workflow AI builder prompt — "Decision Tree Check – Results"

Paste into the AI "Build" box on a new workflow canvas in Taft. Known quirks after it builds (from the Seed welcome build, Oct 24): it sets each Send Email subject to the template NAME instead of the template's subject line (fix by hand); it links templates with "Sync Edits to Template" on (good); it sets internal notifications to "Contact owner," which is empty for new contacts (switch to Particular user → Shannon Jennings). It never publishes on its own.

Prerequisites before pasting: the five email templates exist in Email Builder → Templates with these exact names, and the tags exist (or will be created on save).

---

Build a workflow named "Decision Tree Check – Results".

Trigger: Quiz Submitted, filter Quiz is "The Decision Tree Check". (If the trigger is not available, use Contact Tag Added, tag "decision-tree-check".)

Step 1: Add tag "decision-tree-check".

Step 2: If/Else on contact tag:
- Branch A: has tag "dt-result-a" → Send Email using template "DT Result A – Your tree holds its own weight".
- Branch B: has tag "dt-result-b" → Send Email using template "DT Result B – Half the canopy is on your desk".
- Branch C: has tag "dt-result-c" → Send Email using template "DT Result C – Everything runs through you", then Internal Notification by email to a particular user, Shannon Jennings, subject "Decision Tree Check: {{contact.first_name}} {{contact.last_name}} scored C", body with name, email, company size, heaviest branch, and the line "No automated pitch was sent. Your call whether to reach out."

Step 3 (all branches rejoin): Wait 3 days.

Step 4: Wait until Monday through Thursday at 8:00 AM, contact's timezone if available, otherwise America/New_York.

Step 5: If/Else on contact tag "seed-optin":
- Has tag → Send Email using template "DT Follow-up – Which one did you hand back (Seed subscriber)". Then Add tag with the Saturday Seed source tag so the Seed welcome sequence starts.
- Does not have tag → Send Email using template "DT Follow-up – Which one did you hand back".

Settings: allow re-entry no; stop on response no (replies go to the inbox as normal). Do not publish.

---

## After it builds, check these by hand

1. Each Send Email step: Subject line matches the template's subject, not the template name.
2. Internal notification: To User Type = Particular user → Shannon Jennings.
3. The Seed source tag in Step 5 is the exact tag the "Saturday Seed – Welcome Sequence" workflow (id 2da7a557-83f4-4600-9bfd-1616172f77f9) triggers on. Confirm the tag name in that workflow's trigger before saving.
4. Orange dots on Add Tag nodes mean the tag doesn't exist yet; saving the action creates it.
5. Test with a real quiz submission from a test contact, not "Test Workflow" mode (it sends stale bodies and blank merge tokens).
