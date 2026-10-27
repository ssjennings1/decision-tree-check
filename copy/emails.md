# Emails

Plain personal look: Verdana or system font, no header art, gold #BF8756 links, "Dr. J" signature block. No em dashes. Never "Warmly."

Merge fields: `{{contact.first_name}}`, `{{contact.the_decision_tree_check_overall_score}}`, `{{contact.the_decision_tree_check_highest_category_name}}` (Taft auto-creates these when result sync is on; confirm exact keys in the custom-values picker after the first test submission).

The five-level model block appears in every result email. Keep it identical:

> Leaf: you decide, no need to tell me.
> Branch: you decide, then tell me.
> Limb: you decide, but talk to me before you act.
> Trunk: we decide together.
> Root: I decide, with input from the people who'll live with it.

---

## Email 1A — The Shade Tree (sent immediately)

**Template name:** DT Result A – The Shade Tree
**Subject:** You're a Shade Tree
**Preview:** Desk Load {{contact.the_decision_tree_check_overall_score}} of 40. Here's the one move.

{{contact.first_name}},

Your Desk Load came in at {{contact.the_decision_tree_check_overall_score}} of 40. Most of the small stuff never reaches you, and your people know when to loop you in. People work under your tree, not around it.

The heaviest branch right now is {{contact.the_decision_tree_check_highest_category_name}}.

Here's the model you just took a lap around, since you'll want it for your team. Not every decision carries the same weight.

[model block]

One Move for Monday. Find the one leaf that still climbs. Pick one decision in {{contact.the_decision_tree_check_highest_category_name}} this week and ask the person who brought it, "What would you do?" Then let them. That question is how people grow into the next branch.

Hit reply and tell me what comes up. I read every one.

Dr. J

P.S. The Decision Tree started years ago from Susan Scott's work at Fierce. It's grown a lot in my hands since. And this was a gut check, not a diagnosis. Take it again in six months and see what moved.

---

## Email 1B — The Switchboard (sent immediately)

**Template name:** DT Result B – The Switchboard
**Subject:** You're a Switchboard
**Preview:** Desk Load {{contact.the_decision_tree_check_overall_score}} of 40. Here's the one move.

{{contact.first_name}},

Your Desk Load came in at {{contact.the_decision_tree_check_overall_score}} of 40. A good share of the everyday calls still route through you, and a good share don't. You're the connection point. Everybody knows that if they plug into you, they get an answer.

That's how a company grows when the owner is good at the work. People bring you things because you have the answer, and because they're not sure they're allowed to decide. From your chair it looks like interruptions. From theirs it looks like respect, or caution.

The heaviest branch right now is {{contact.the_decision_tree_check_highest_category_name}}.

Here's the model. Not every decision carries the same weight.

[model block]

Most growing businesses treat everything like a trunk or root decision. The tree gets weighed down because nothing moves without the person at the center, and nobody grows into the next branch because nobody told them it was theirs. The point of the tree is clarity: everyone knows what they can decide, what to report back on, and what not to do alone. That's what clears your desk for the next hire, the next customer, the next year.

One Move for Monday. Look at the last five things that landed on your desk. Pick one from {{contact.the_decision_tree_check_highest_category_name}}, hand it back to the person it belongs to, and give them the rule: you decide, then tell me. Say it out loud. Clarity is the gift.

Hit reply and tell me which one you picked. I read every one.

Dr. J

P.S. The Decision Tree started years ago from Susan Scott's work at Fierce. It's grown a lot in my hands since. Gut check, not a diagnosis.

---

## Email 1C — The Builder (sent immediately)

**Template name:** DT Result C – The Builder
**Subject:** You're a Builder
**Preview:** Desk Load {{contact.the_decision_tree_check_overall_score}} of 40. Here's the one move.

{{contact.first_name}},

Your Desk Load came in at {{contact.the_decision_tree_check_overall_score}} of 40. Nearly everything on the list came to you, or waited for you. That's because you built this. You were the answer to every question in the building, and that's exactly how it grew.

It's also why you can't step away without things slowing down, and why you're the last to hear about the things that matter. Nobody did this to you. It's what happens when a company outgrows one person's ability to see everything and nobody has drawn the lines yet. Builders are good at drawing lines. You just haven't pointed that at this yet. And the people bringing you things are ready for more than they're getting. Every decision you hand back with a clear rule is one they grow on, and one less thing between you and the work only you can do: where this company goes next.

The heaviest branch right now is {{contact.the_decision_tree_check_highest_category_name}}.

Here's the model. Not every decision carries the same weight.

[model block]

One Move for Monday. Pick the one decision that came to you this week that you already knew the answer to before they finished asking. Hand it back with a rule attached: "This is yours. Make the call and tell me after." Then do it again next week. Watch who steps up.

Hit reply and tell me which one you picked. I read every one.

Dr. J

P.S. The Decision Tree started years ago from Susan Scott's work at Fierce. It's grown a lot in my hands since. Gut check, not a diagnosis.

---

## Email 2 — All patterns, three days later, Mon–Thu 8 AM

**Template name:** DT Follow-up – Which one did you hand back
**Subject:** Which one did you hand back?
**Preview:** Quick follow-up on your Desk Load.

{{contact.first_name}},

A few days ago you found out you're a {{pattern name via If/Else or three template variants}} and I asked you to hand one decision back.

Did you? If yes, what happened? If no, what got in the way?

I ask because that's where it gets interesting. Handing a decision back means someone will make it differently than you would. Sometimes a little worse. That moment is the whole job of growing a company past yourself, and it's the part most owners skip.

There's an owner I worked with who put a tree on the wall outside her office. Every decision her people were cleared to make got a leaf with their name on it. People started stopping at the tree instead of knocking. The line at her door got shorter. I tell that story in the Saturday Seed, one leadership idea a week you can put into play Monday. [Get the Seed]

Hit reply either way. I read every one.

Dr. J

> Variant "(Seed subscriber)": same email with the Seed paragraph cut to "There's an owner I worked with who put a tree on the wall outside her office. I'll tell you about her in a Seed soon."
> Simplest build: skip the pattern-name merge and write "found out where your Desk Load sits" instead. Use that unless the builder exposes a clean tier merge field.

---

## Email 3 — Personal note from Shannon, Result C only, within 24 hours (she sends by hand)

Delivered to Shannon as the body of a Taft task, not sent automatically. She edits and sends from her own inbox.

**Subject:** Your Desk Load

{{first name}},

Saw your Desk Load come through ({{score}} of 40, heaviest branch {{category}}). That number is very familiar to me. Almost every owner I work with started there, and most of them built something worth running through them.

No pitch. Two things: the one move in the email is real, and it works better than it sounds. And if you want to talk through which decision to hand back first, I keep fifteen minutes open for exactly that. [link]

Either way, reply and tell me what you're building. I'm curious.

Shannon

---

## Internal notification — Result C only

**To:** Particular user → Shannon Jennings (not "contact owner"; fresh contacts have none)
**Subject:** Builder result: {{contact.first_name}} {{contact.last_name}}
**Body:**
New Builder (Result C) from the Desk check.
Name: {{contact.first_name}} {{contact.last_name}} · Email: {{contact.email}}
Company size: {{contact.company_size}} · Heaviest branch: {{contact.the_decision_tree_check_highest_category_name}} · Seed opt-in: {{contact.seed_optin}}
A task with the personal-note draft is waiting in your tasks. Send it within 24 hours.
