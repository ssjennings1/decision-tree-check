# Emails

Plain personal look: Verdana or system font, no header art, gold #BF8756 links, "Dr. J" signature block. No em dashes. Never "Warmly."

Merge fields: `{{contact.first_name}}`, `{{contact.dt_stage}}`, `{{contact.dt_state}}`, `{{contact.dt_green_flag}}`, `{{contact.dt_red_flag}}` (custom fields the workflow writes; see taft/build-spec.md).

The five-level model block appears in every result email. Keep it identical:

> Leaf: you decide, no need to tell me.
> Branch: you decide, then tell me.
> Limb: you decide, but talk to me before you act.
> Trunk: we decide together.
> Root: I decide, with input from the people who'll live with it.

---

## Email 1 — Result (one template per seat; owner shown; team and manager variants swap the stage paragraph for the seat paragraph from result-pages.md)

**Template name:** DT Result – Owner
**Subject:** Your desk, on the tree
**Preview:** {{contact.dt_stage}}, {{contact.dt_state}}. Here's the picture and the one move.

{{contact.first_name}},

Here's your picture from the desk check.

You're a {{contact.dt_stage}}. [Workflow inserts the stage-and-state paragraph from copy/result-pages.md by If/Else: Builder/Stretching/Architect × on track/climbing/drifting.]

Green flag: {{contact.dt_green_flag}}

Red flag: {{contact.dt_red_flag}}

Here's the model you just walked around, since you'll want it for your team. Not every decision carries the same weight.

[model block]

One Move for Monday. [Workflow inserts the One Move for the stage and state.]

Hit reply and tell me what came up. I read every one.

Dr. J

P.S. The Decision Tree started years ago from Susan Scott's work at Fierce. It's grown a lot in my hands since. And this was a gut check, not a diagnosis. Send it to your leadership team and compare trees on Thursday. That's where it gets interesting.

---

## Email 2 — All patterns, three days later, Mon–Thu 8 AM

**Template name:** DT Follow-up – Which one did you hand back
**Subject:** Which one did you hand back?
**Preview:** Quick follow-up on your desk check.

{{contact.first_name}},

A few days ago you saw your desk on the tree and I asked you to hand one decision back.

Did you? If yes, what happened? If no, what got in the way?

I ask because that's where it gets interesting. Handing a decision back means someone will make it differently than you would. Sometimes a little worse. That moment is the whole job of growing a company past yourself, and it's the part most owners skip.

There's an owner I worked with who put a tree on the wall outside her office. Every decision her people were cleared to make got a leaf with their name on it. People started stopping at the tree instead of knocking. The line at her door got shorter. I tell that story in the Saturday Seed, one leadership idea a week you can put into play Monday. [Get the Seed]

Hit reply either way. I read every one.

Dr. J

> Variant "(Seed subscriber)": same email with the Seed paragraph cut to "There's an owner I worked with who put a tree on the wall outside her office. I'll tell you about her in a Seed soon."

---

## Email 3 — Personal note from Shannon, owners whose state is climbing or drifting, within 24 hours (she sends by hand)

Delivered to Shannon as the body of a Taft task, not sent automatically. She edits and sends from her own inbox.

**Subject:** Your desk, on the tree

{{first name}},

Saw your desk check come through. {{stage}}, with the weight still climbing (or: with some of the big calls drifting). That picture is very familiar to me. Almost every owner I work with started there, and most of them built something worth running through them.

No pitch. Two things: the one move in the email is real, and it works better than it sounds. And if you want to talk through which decision to hand back first, I keep fifteen minutes open for exactly that. [link]

Either way, reply and tell me what you're building. I'm curious.

Shannon

---

## Internal notification — owners, climbing or drifting

**To:** Particular user → Shannon Jennings (not "contact owner"; fresh contacts have none)
**Subject:** Desk check: {{contact.first_name}} {{contact.last_name}} ({{contact.dt_stage}}, {{contact.dt_state}})
**Body:**
New owner result from the desk check that's worth a personal note.
Name: {{contact.first_name}} {{contact.last_name}} · Email: {{contact.email}}
Size: {{contact.dt_company_size}} · Stage: {{contact.dt_stage}} · State: {{contact.dt_state}} · Red flag: {{contact.dt_red_flag}} · Seed opt-in: {{contact.seed_optin}}
A task with the personal-note draft is waiting in your tasks. Send it within 24 hours.
