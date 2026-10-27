# Emails

Two emails after the quiz, plus the internal notification. House style: plain personal look (no Seed header art), Verdana or system font, gold #BF8756 links, signed "Dr. J" with the Syncovate signature block. No em dashes. Never "Warmly."

Merge fields: `{{contact.first_name}}`, `{{contact.the_decision_tree_check_highest_category_name}}` (custom field; exact merge syntax confirmed in Taft at build time).

Three versions of Email 1, one per result band. The workflow picks by tag.

---

## Email 1A — Result A, sent immediately

**Subject:** Your tree holds its own weight
**Preview:** Here's your result and the one move for Monday.

{{contact.first_name}},

Here's your result from the Decision Tree Check: most of the small stuff gets handled without you, and your people know when to loop you in.

That's the pattern of a company that can grow. The decisions reaching your desk are mostly the ones that should.

Quick version of the model, since you'll want it for your team. Not every decision carries the same weight.

Leaf: you decide, no need to tell me.
Branch: you decide, then tell me.
Limb: you decide, but talk to me before you act.
Trunk: we decide together.
Root: I decide, with input from the people who'll live with it.

One move for Monday. Your answers put the most weight on {{contact.the_decision_tree_check_highest_category_name}}. Find one decision in that lane this week and ask the person who brought it, "What would you do?" Then let them.

Hit reply and tell me what comes up. I read every one.

Dr. J

P.S. The Decision Tree started years ago from Susan Scott's work at Fierce. It's grown a lot in my hands since.

---

## Email 1B — Result B, sent immediately

**Subject:** Half the canopy is on your desk
**Preview:** Here's your result and the one move for Monday.

{{contact.first_name}},

Here's your result from the Decision Tree Check: a good share of the everyday calls still come to you, and a good share don't.

That's normal for a company that grew by you being good at the work. People bring you things because you have the answer, and because they're not sure they're allowed to decide. From your chair it looks like interruptions. From theirs it looks like respect, or caution.

Here's the model. Not every decision carries the same weight.

Leaf: you decide, no need to tell me.
Branch: you decide, then tell me.
Limb: you decide, but talk to me before you act.
Trunk: we decide together.
Root: I decide, with input from the people who'll live with it.

Most growing businesses treat everything like a trunk or root decision. The tree gets weighed down because nothing moves without the person at the center.

One move for Monday. Look at the last five things that landed on your desk. Where do they belong on the tree? Your answers put the most weight on {{contact.the_decision_tree_check_highest_category_name}}. Pick one decision there, hand it back to the person it belongs to, and give them the rule: you decide, then tell me.

Hit reply and tell me which one you picked. I read every one.

Dr. J

P.S. The Decision Tree started years ago from Susan Scott's work at Fierce. It's grown a lot in my hands since.

---

## Email 1C — Result C, sent immediately

**Subject:** Everything runs through you
**Preview:** Here's your result and the one move for Monday.

{{contact.first_name}},

Here's your result from the Decision Tree Check: nearly every situation on the list came to you, or waited for you.

That's how it grew. You were the answer to every question in the building, and it worked. It's also why you can't step away without things slowing down, and why you're the last to hear about the things that matter. Nobody did this to you. It's what happens when a company outgrows one person's ability to see everything and nobody has drawn the lines yet.

Here's the model. Not every decision carries the same weight.

Leaf: you decide, no need to tell me.
Branch: you decide, then tell me.
Limb: you decide, but talk to me before you act.
Trunk: we decide together.
Root: I decide, with input from the people who'll live with it.

One move for Monday. Pick the one decision that came to you this week that you already knew the answer to before they finished asking. Hand it back with a rule attached: "This is yours. Make the call and tell me after." Then do it again next week.

Hit reply and tell me which one you picked. I read every one.

Dr. J

P.S. The Decision Tree started years ago from Susan Scott's work at Fierce. It's grown a lot in my hands since.

---

## Email 2 — All bands, three days later, Mon–Thu 8 AM

**Subject:** Which one did you hand back?
**Preview:** A quick follow-up on your Decision Tree Check.

{{contact.first_name}},

A few days ago you took the Decision Tree Check and I asked you to hand one decision back.

Did you? If yes, what happened? If no, what got in the way?

I ask because the second part is where it gets interesting. Handing a decision back means someone will make it differently than you would. Sometimes a little worse. That moment is the whole job of growing a company past yourself, and it's the part most owners skip.

I'll tell you about an owner who built the tree on the wall outside her office, and what happened to the line at her door. That's in the Saturday Seed, one leadership idea a week you can put into play Monday. [Get the Seed]({{seed_signup_url}})

Hit reply either way. I read every one.

Dr. J

> Note: if the contact already has the Seed opt-in tag, the workflow uses a variant of this email without the Seed paragraph. That variant is the same email with the paragraph starting "I'll tell you about an owner" removed.

---

## Internal notification — Result C only

**To:** Shannon (Particular user, not "contact owner"; fresh contacts have no owner)
**Subject:** Decision Tree Check: {{contact.first_name}} {{contact.last_name}} scored C
**Body:**
New Result C from the Decision Tree Check.
Name: {{contact.first_name}} {{contact.last_name}}
Email: {{contact.email}}
Company size: {{contact.company_size}}
Heaviest branch: {{contact.the_decision_tree_check_highest_category_name}}
Seed opt-in: {{contact.seed_optin}}
No automated pitch was sent. Your call whether to reach out.
