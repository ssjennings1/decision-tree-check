# Result pages v2

A picture, not a diagnosis. Every page has the same shape: stage headline said like a compliment, the tree, the fit line, a green flag, a red flag, One Move for Monday, two buttons, the credit. Phone-first. No em dashes in body copy.

Merge fields on the page: `{{contact.first_name}}`. The two flags merge from fields the workflow writes: `{{contact.dt_green_flag}}`, `{{contact.dt_red_flag}}` (see build spec; if page merge of custom fields proves unreliable, the flags live in the email only and the page shows the stage copy).

Share line (all pages): *"I'm a {{stage}}. Bet your desk looks different. Two minutes, no grade. syncovatellc.com/desk"*

Disagreement block (all pages, above the credit; Shannon 2026-10-27):

> **You'll disagree with where I put some of these.** Where a decision sits depends on your company. Buying a truck is routine for a company that runs a fleet and a major decision for one that has never bought a truck. This picture uses broad strokes. The real one is the version you draw with your team, and the places you disagree are where the lines need drawing.

Credit (small type, all pages): *The Decision Tree started years ago from Susan Scott's work at Fierce. It's grown a lot in Dr. J's hands since. This is a gut check, not a diagnosis.*

Buttons (all pages): **Book 15 minutes with Dr. J** · **Send this to someone whose desk you're curious about**

---

## Flag lines (the workflow picks one green and one red; wording by level)

Green (what you let go of well, or carry well):
- Leaf: "The small stuff mostly gets handled without you. That's the hardest habit to build and you've built it."
- Branch: "Day-to-day calls get made and you hear about them after. That's trust, and your people can feel it."
- Limb: "The judgment calls come to you for a conversation, not a rescue. That's the right altitude."
- Trunk: "The decisions that shape the company are still being made together, with you in the room."
- Root: "The make-or-break calls land on your desk. That's exactly where they belong."

Red (what you hold, or what's happening without you):
- Leaf (holding): "The small stuff still finds its way to you. Friday off, a broken printer, a swapped schedule. None of it needs you, and all of it waits for you."
- Branch (holding): "The everyday calls still route through you before they happen. Your people have the judgment. They're not sure they have the permission."
- Limb (holding): "The judgment calls come to you to be decided, not discussed. One sentence changes that: what would you do?"
- Trunk (drifting): "Some of the decisions that shape the company are getting made without you in the room. That's worth a look this week."
- Root (drifting): "At least one make-or-break call didn't reach your desk. Those are the ones nobody else should be carrying alone."

---

## OWNER PAGES

### Builder, on track

**You're a Builder, and you're right where you should be.**

{{contact.first_name}}, at your size, everything runs through you because you built it, and that's the right answer. The tree is small enough that you can see all of it, and your people know exactly who to ask. Most owners at this stage feel like they should be delegating more. Not yet. Right now your job is to keep the whole tree in view and notice who's starting to make good calls on their own.

{{contact.dt_green_flag}}

{{contact.dt_red_flag}}

**One Move for Monday.** Pick one person who brought you something this week they could have handled. Next time, ask: "What would you do?" Then let them. You're not handing off the decision yet. You're finding out who's ready for the next branch.

The next stage puts new weight on the tree, and it's the stage where owners get stuck. When you're close, I'm glad to talk.

### Builder, roots drifting

**You're a Builder, and some of the big calls are getting made without you.**

{{contact.first_name}}, at your size the whole tree should be in your line of sight, and most of it is. But at least one of the decisions that can make or break the company didn't reach your desk last week. That happens when an owner is heads-down in the work and the big stuff shows up quietly.

{{contact.dt_green_flag}}

{{contact.dt_red_flag}}

**One Move for Monday.** Ask one question of your people: "What's the biggest thing you decided last week?" Then listen for the one that should have been yours.

If you want help drawing the lines for who decides what, that's a conversation I'm glad to have.

### Stretching, on track

**You're in the stretch, and you're doing it right.**

{{contact.first_name}}, 10 to 40 people is where the tree has to change shape. Doug Tatum calls it No Man's Land; I call it stretching, because that's what it feels like. The small stuff is supposed to stop reaching you here, and from your answers, it mostly has. The decisions on your desk are the ones that should be there: the judgment calls, the direction, the make-or-break.

{{contact.dt_green_flag}}

{{contact.dt_red_flag}}

**One Move for Monday.** Find the one leaf that still climbs. Hand it back with the rule out loud: "You decide. Tell me after." Clarity is the gift.

The stretch is also where your people are ready for more than they're getting. If you want to draw the lines with the whole team in one room, that's the work I love.

### Stretching, weight climbing

**You're in the stretch, and the weight is still climbing to you.**

{{contact.first_name}}, 10 to 40 people is where the tree has to change shape, and it's the hardest stretch in the life of a company. The small stuff is supposed to stop reaching you here. From your answers, a lot of it still does. That's not a flaw. It's what happens when a company grows faster than the lines get drawn, and your people keep bringing you things because you have the answer and they're not sure they're allowed to.

{{contact.dt_green_flag}}

{{contact.dt_red_flag}}

**One Move for Monday.** Look at the last five things that landed on your desk. Pick the smallest one. Hand it back to the person it belongs to and say the rule out loud: "This is yours. Make the call and tell me after." Then watch who steps up.

If you'd rather draw the lines with your whole management team instead of one decision at a time, that's the kind of room I hold. Fifteen minutes is enough to see if it fits.

### Stretching, roots drifting

**You're in the stretch, and some of the big calls are drifting.**

{{contact.first_name}}, you've done the hard part: the small stuff isn't reaching you anymore. But at least one decision that should have come to you didn't. In the stretch, that's common. The owner finally gets out of the weeds and the big calls start getting made by whoever's standing closest.

{{contact.dt_green_flag}}

{{contact.dt_red_flag}}

**One Move for Monday.** Tell your leadership team which three kinds of decisions always come to you, in one sentence each. Most owners have never said it out loud.

Drawing those lines with your team in the room is what I do. Fifteen minutes is enough to see if it fits.

### Architect, on track

**You're an Architect, and the tree holds its own weight.**

{{contact.first_name}}, at your size the small stuff shouldn't reach you, and from your answers it doesn't. Your desk holds the decisions that shape the company and the ones that can make or break it. That's the whole point of the tree, and most owners never get here.

{{contact.dt_green_flag}}

{{contact.dt_red_flag}}

**One Move for Monday.** Ask your leadership team to take this check. Compare trees on Thursday. The gaps between what you think they decide and what they think they decide are where the next year gets won.

When you want a second set of eyes on where the lines should move next, I'm glad to talk.

### Architect, weight climbing

**You're an Architect, and the small stuff is still finding you.**

{{contact.first_name}}, at your size the leaves and branches should be handled long before they reach you. From your answers, some still do. Usually that's not about your people. It's about lines that were drawn for a smaller company and never redrawn.

{{contact.dt_green_flag}}

{{contact.dt_red_flag}}

**One Move for Monday.** Pick the one small decision that came to you this week that you already knew the answer to before they finished asking. Hand it back with a rule. Then ask your leadership team why it got to you in the first place. That answer is the real finding.

Redrawing the lines with your team in the room is the work I do. Fifteen minutes is enough to see if it fits.

### Architect, roots drifting

**You're an Architect, and the roots need you.**

{{contact.first_name}}, the small stuff doesn't reach you, which is right. But at least one make-or-break decision didn't either, and at your size those are the ones only the owner should carry. This is the quiet version of being the last to know.

{{contact.dt_green_flag}}

{{contact.dt_red_flag}}

**One Move for Monday.** Ask your leadership team one question: "What's the biggest thing we decided last month that I wasn't in the room for?" Say it with curiosity, not alarm.

If you want help naming which decisions are always yours, that's a conversation I'm glad to have.

---

## OTHER SEATS

### Leadership team, on track

**Your desk fits your seat.**

{{contact.first_name}}, the everyday calls and the judgment calls land on you, the small stuff gets handled below you, and the make-or-break decisions go up. That's what a leadership-team desk is supposed to look like. It also means the owner trusts you with the middle of the tree, which is the part that holds everything else up.

{{contact.dt_green_flag}}

{{contact.dt_red_flag}}

**One Move for Monday.** Send this to the owner and ask to compare trees. Where your picture and theirs disagree is where the lines need drawing.

### Leadership team, weight climbing

**Your desk is carrying more small stuff than your seat calls for.**

{{contact.first_name}}, a lot of the leaves are landing on you. Either your people aren't clear they can decide, or you're the kind of leader people like to check with. Both are fixable, and both start with saying the rule out loud.

{{contact.dt_green_flag}}

{{contact.dt_red_flag}}

**One Move for Monday.** Pick one decision that came to you this week that your people could have made. Hand it back: "You decide. Tell me after."

### Leadership team, roots drifting

**Your desk is lighter than your seat.**

{{contact.first_name}}, the judgment calls and the direction decisions that should be reaching you mostly aren't. Sometimes that's an owner who still holds the middle of the tree. Sometimes it's lines that were never drawn. Either way, you're ready for more than you're getting.

{{contact.dt_green_flag}}

{{contact.dt_red_flag}}

**One Move for Monday.** Ask the owner one question: "Which decisions do you want me making without checking first?" Write down the answer.

### Manager / team lead (variant lines for the three states above)

- On track: "The small stuff and the day-to-day calls land on you, and the big ones go up. That's exactly the seat."
- Climbing: not applicable (leaves belong here); use the "roots drifting" copy only if trunk items appear, otherwise show On track.
- Drifting: "A lot of the everyday calls that should be yours are going up over your head. That's worth a conversation with whoever's above you."

### Family member (variant opening paragraph, then Leadership team copy)

"{{contact.first_name}}, in a family business, decisions sometimes land by last name instead of by seat. Your desk picture is below. The question worth asking is whether what lands there is yours because of your role, or because of your family. Both can be true. Knowing which is which is where the clarity starts."
