---
name: calm-os
description: The operating philosophy beneath every calm/slow product in the ecosystem — travel apps, hospitality flows, cultural concierges, journals, journey planners, glossaries, food apps. Not a visual style guide (see `slow-dreamy` for surface treatment). This is the kernel: what the software *does* when nothing is happening, what it refuses to do even when asked, what it considers a successful interaction, how it treats attention, time, memory, and notifications. Use this skill whenever building any user-facing product where the brand promise involves slowness, depth, sanctuary, considered-ness, or the explicit rejection of attention-economy patterns. Trigger when the user asks to design, scope, or critique a "calm tech" app, a slow-travel product, a concierge interface, a wellness or journaling tool, an editorial reading experience, or anything positioned against urgency. Also trigger when reviewing notification patterns, default settings, onboarding flows, retention mechanics, or any feature that touches the user's attention. If a feature could plausibly be described as "engagement-driven," this skill applies.
---

# Calm OS

The operating philosophy for every product in the Dancing with Lions ecosystem — Slow Morocco, Riad di Siena, Darija.io, goji.ma, Dancing with Lions, House of Weaves, the cultural intelligence layer, and everything that comes after.

This is not a visual design system. For colors, typography, motion timing, and surface treatment, see the `slow-dreamy` skill — that's the shell. Calm OS is the kernel underneath. It governs what the software *does*, not what it *looks like*.

A product can be visually calm and operationally hostile. Soft cream backgrounds and a daily push notification at 7am asking "How are you feeling?" is calm cosplay, not Calm OS. The surface and the substance have to agree.

## The first principle

> The product respects the user's attention more than the user does.

This is the entire philosophy in one sentence. Calm OS products do not optimize for time-in-app, daily active users, session length, or any metric that requires the user to be there more often than they need to be. They optimize for the user finishing the thing they came to do and leaving — and the product getting better at being useful on the next return.

Engagement is a side effect of usefulness, never a goal. If a feature would only exist to bring the user back, it doesn't exist.

This is not commercial passivity. It's a market position. The ecosystem competes on the axis of "this is the one app that doesn't make me feel worse." That position is defensible, expensive to copy, and increasingly rare. The calm is the moat.

## The four laws

Every product decision can be checked against these four. If a feature violates any, redesign or remove.

### 1. Silence is the default

The product does not speak unless the user has asked it to speak, or there is genuine, time-sensitive, user-relevant information to convey.

- **No** notifications by default. Opt-in, granular, off until requested.
- **No** "we miss you" emails. No re-engagement campaigns. No streaks.
- **No** badges that exist to be cleared. If a badge appears, something genuinely happened that the user wanted to know about.
- **No** modals on load. No "did you know?" tooltips. No tour guides on second visit.
- **No** feed that exists to be scrolled.

A genuine notification: "Your guest checks in tomorrow." A non-genuine notification: "Three new dossiers added this week." The first is information the user is waiting for. The second is the product asking for attention.

### 2. The interface ends

Every flow has a finish line. The product does not invent reasons for the user to stay once the task is complete.

- A booking confirmation page says "You're booked. See you in May." It does not say "While you're here, browse 12 more riads."
- A journal entry, once written, closes. There is no "share to social" prompt. No "add tags." No "five more prompts to try today."
- A search result page returns the answer and stops. No infinite scroll. No "you might also like."

The end of a task is a sacred moment. The product takes its hands off the wheel.

### 3. Memory is owed, not earned

If the user told the product something, the product remembers. If the user did something, the product knows. The user never has to repeat themselves to the same product, and never has to re-explain context the product was present for.

- Forms remember. Preferences persist. Search history is recalled.
- The concierge does not ask "are you traveling alone or with family?" on visit four when it asked on visit one.
- The booking flow does not ask for the user's email when the user is logged in.

The product carries the weight of the relationship. The user shows up; the product has done its homework.

This is also a privacy contract: the product remembers *for the user*, not for advertisers, not for an analytics pipeline, not for a third party. Memory stays inside the trust boundary.

### 4. Speed is silent, expression is slow

Calm is not lag. The product responds to input within 100ms — always. What is slow is the *expression* of the response: the fade, the settle, the considered phrasing. Slowness is a chosen aesthetic on top of a fast machine. It is never an accident of poor performance.

If the product is slow because the database is slow, that's a bug, not a feature. Calm OS demands the engineering be excellent so that the slowness can be a choice.

## What the product refuses to do

Calm OS is defined as much by refusal as by capability. The following patterns are forbidden in any product in the ecosystem, regardless of how much they would improve a metric:

- **Streaks.** Counting consecutive days of use. Punishes absence, weaponizes guilt.
- **Daily-use guilt.** "You haven't journaled in 4 days." The product has no opinion about how often the user should show up.
- **Loss aversion framing.** "Don't lose your progress!" "Your draft will be deleted in 24 hours!"
- **Manufactured scarcity.** "Only 2 rooms left at this price!" unless that is literally and verifiably true *right now*.
- **Auto-playing media.** Video, audio, animation that starts without consent.
- **Pop-up exit intent modals.** "Wait! Before you go..." — never.
- **Newsletter modals on first visit.** The user has been on the page for nine seconds and has not yet earned a request.
- **Cookie banners that hide the "reject all" button.** If the product has cookies that need consent, the reject path is at least as easy as the accept path. Ideally, the product doesn't have those cookies.
- **Dark patterns of any kind.** Confirm-shaming ("No thanks, I don't want to save money"), forced continuity, hidden subscriptions, roach motels. All forbidden. No exceptions.
- **Engagement-tuned recommendations.** A "you might also like" engine that exists to extend session time. Recommendations exist only when they answer a question the user is actively asking.
- **Fake activity.** "23 people are looking at this room right now." Even if true, it's a manipulation. Calm OS does not manipulate.
- **A/B tests that test the user's resistance to dark patterns.** Some optimization is fine. Optimizing toward "how much friction can we add to cancellation before users break" is not.

Each of these can probably lift a metric in the short term. Each is forbidden anyway, because the metric they lift is the wrong one. The right metric is whether the user, six months from now, still trusts this product enough to come back when they actually need it.

## The notification doctrine

Notifications get their own section because they are the single most violated principle in modern software, and the easiest place for a "calm" product to slip.

### The default state

Off. Everything off. The user opts into specific channels, by category, with full transparency about what each channel sends and how often.

### The four legitimate notification types

Only these. If a notification doesn't fit one of these, it doesn't get sent.

1. **Pre-arranged.** The user explicitly asked for this notification. ("Remind me about my booking the day before check-in.") The user wrote the contract; the product is fulfilling it.
2. **Time-critical and user-relevant.** Something is about to happen that affects the user materially. Their flight is delayed. Their guest just checked in. The riad's water is being cut tomorrow.
3. **Action-required.** Something is waiting on the user that won't resolve without them. Payment failed. Review needed before publication. Document expires in 7 days.
4. **Confirmation of a thing the user just did.** "Saved." "Sent." "Booked." Brief, in-context, often inline rather than a system notification.

### What is not a legitimate notification

- "We added new content."
- "Your friend joined."
- "Trending in your region."
- "Don't forget us!"
- "How was your stay?" sent for the fifth time.
- Anything the marketing team wants to send.

### Tone

When the product does notify, it sounds like a thoughtful friend, not a brand. Lowercase if it fits. Plain language. No exclamation points except in confirmation of a single specific positive action. No emoji clusters. The notification reads like a sentence someone would actually say out loud.

| Wrong | Right |
|---|---|
| "🎉 Welcome back to Slow Morocco!" | "Your trip starts in 3 days." |
| "⚠️ ACTION REQUIRED: Your booking is at risk!" | "Your card on file expired. The booking is held for 48 hours." |
| "5 new dossiers you'll love!" | (no notification) |
| "Your stay was unforgettable! Rate us!" | "Was the riad ready for you? A short note helps the next guest." |

## Time as a design material

Calm OS treats time differently than transactional software does.

### The product knows what time it is for the user

Local time. Local season. Local light. A travel concierge in Marrakech in July does not behave the same as the same concierge in January. A wellness app at 11pm does not push the same content as the same app at 8am. The product is environmentally aware in the sense that a person is — it knows the weather, it knows whether it's Ramadan, it knows the user is probably tired.

This isn't surveillance. It's contextual courtesy. Every signal the product uses to be contextually appropriate must come from data the user knowingly provides or that is genuinely public (sunset time, weather, calendar of public holidays). No tracking. No inference from third-party data brokers.

### The product slows down at endings

The end of a session, the end of a day, the end of a trip — these are moments where the product does less, not more. The journal app at 11pm offers a one-line evening prompt and then suggests the user close the app. The concierge after a trip ends asks one gentle question, once, and then goes quiet for a month. The booking flow, after confirmation, says "We have everything we need" and dims the page.

Endings are sacred. Most software treats them as conversion opportunities ("rate us!" "share!" "book again!"). Calm OS treats them as exhalations.

### The product can wait

If the user starts a flow and abandons it, the product does not panic. It saves state. It says nothing. If the user returns three weeks later, the product picks up where it was left, without commentary on the absence. There is no "Welcome back! It's been 23 days!" message. The product was fine. The user was fine. Time passed.

## Memory and privacy

Calm OS products keep memory inside a tight trust boundary.

### Local first, then encrypted, then careful

- Whenever feasible, sensitive state lives on-device.
- When it must travel, it is encrypted in transit and at rest.
- When it is held server-side, it is held in the smallest set of services possible, with the shortest retention possible, accessed by the smallest set of humans possible.
- Logs are scrubbed. Analytics are aggregated, not individual. Email content is not mined.

### The user can leave

Every Calm OS product has a working export and a working delete. Both are findable, both work, both complete in reasonable time. The user can take their data and disappear, and the product's response is "thanks for being here" — not a retention flow.

### No third-party tracking by default

No Facebook pixel. No Google Tag Manager firing on first paint. No session replay tools recording mouse movements. If analytics are necessary, they are first-party, aggregated, and disclosed in plain language. The user is not a product.

### The AI variant of this

For products with AI concierges, glossaries, or generative components: the user's conversation is theirs. It is not used to train models without explicit, granular, informed consent. Uploads stay private. Voice samples stay private. The Darija audio Zahra records is hers, not the platform's.

## Onboarding, defaults, and the cost of choice

### Defaults are the design

Most users never change defaults. The default state of a Calm OS product is what the product *is*, for nearly everyone. This is why notifications are off by default, tracking is off by default, recommendations are off by default. The opt-in user is consenting; the default user is protected.

### Onboarding is short

Three screens, ideally fewer. The product earns the right to ask more questions later, after it has demonstrated value. A 14-step onboarding flow is a confession that the product doesn't trust itself to be useful without exhaustive setup.

### The product reveals capability over time

A Calm OS product is allowed to be more capable than it appears. Features unfold as the user finds reason for them. The first session shows the core promise. The tenth session reveals the depth. This is the opposite of the modern SaaS pattern of front-loading every feature in onboarding to "drive activation."

### Empty states are welcomes, not voids

When there's no content, the empty state is generous. A short sentence, a small invitation, no pressure. "Nothing here yet — when you save your first dossier, it'll live here." Not "You have no items! Click here to get started!"

## Copy and tone (operational)

The visual side of voice belongs in slow-dreamy and the brand voice guides. The operational side — the words the product says to do its job — belongs here.

- **The product does not perform.** No "we're so excited" energy. No "yay you did it!" celebrations. Saved is saved.
- **The product is not a friend.** It is a useful, considered tool with manners. It is not trying to be a relationship.
- **The product never apologizes when nothing went wrong.** "Sorry to bother you, but..." is forbidden. The product is not sorry to be there; it has a reason.
- **The product is honest about its limits.** "I don't know" is allowed. "I can't help with that here, but [specific other thing] might" is allowed. Pretending to be more capable than it is is not.
- **The product never uses urgency it didn't earn.** "Hurry!" "Last chance!" "Only today!" are forbidden unless they are literally and verifiably true and the user asked to be told.

## What this looks like in the ecosystem

Concrete applications across active products:

**Riad di Siena (booking flow)**
The booking confirmation page is the end of the flow. No "while you wait, here's what to pack" — that goes in a pre-arranged email two weeks before arrival, only if the user wanted it. No upsells in confirmation. The page says what time check-in is, who Zahra is, and stops.

**Slow Morocco (reading)**
No newsletter modal. No "subscribe to keep reading." No related-posts carousel that exists to extend session time. Articles end. The reader leaves. SEO and quality bring them back, not retention mechanics.

**Dancing with Lions (cultural platform)**
Door 1 (the dark map) does not push. Door 2 (the editorial pages) does not interrupt. The freemium upgrade prompt appears at most once per session, after the user has hit a meaningful boundary, and is skippable without dark-pattern friction.

**Darija.io (language learning)**
No streaks. No "you haven't practiced in 3 days." The user comes back when they need a word. The product is a dictionary, not a Duolingo owl.

**goji.ma (food/grocery)**
Order confirmation is the end of the flow. No "you might also like" at checkout. Notifications are limited to: order confirmed, out for delivery, delivered, payment issue. That's the entire notification set.

**The cultural intelligence company (separate entity)**
Calm OS still applies, but the user is now an institutional client. The principles translate: no fake urgency in dashboards, no engagement-tuned alerts, no manipulation of the analyst's attention. The intelligence layer is calm because calm is how serious clients want to work — the same reason a Bloomberg terminal isn't full of dancing emoji.

**The AI concierge (across properties)**
Does not initiate conversations. Does not ping. Does not "check in." Speaks when spoken to. Knows what it knows, says what it doesn't. Shuts up when the answer is delivered.

## Edge cases and when Calm OS bends

Calm OS is a strong default, not a religion. There are edge cases.

- **Genuine emergencies.** If a guest's check-in is tomorrow and the booking has a real problem, the product can break the silence. The threshold is high.
- **Legal and financial obligations.** Tax notices, invoice reminders, document expirations — these are allowed, framed clearly, sent once.
- **User-initiated urgency.** If the user said "remind me daily until I do this," the product reminds them daily. The user wrote the contract.
- **Children and accessibility.** Some adaptations of Calm OS may need slightly more guidance, more explicit empty states, more prompting. The principle (respect for attention) holds; the implementation flexes.

When Calm OS bends, it bends transparently. The product can say, in effect, "this is louder than usual because [specific reason]." It does not slowly drift toward noisier defaults over time — that's the death by a thousand notifications that ruined every other category of software.

## The Calm Software Audit

Every product in the ecosystem should be auditable against the same eight principles, in the same order, every time. This is the canonical framework — adapted from the Calm Technology lineage (Mark Weiser and John Seely Brown, codified by Amber Case) — and it is the standard. When auditing a product, walk through all eight, give each a verdict (passes, mostly passes, fails), and write the specific evidence in plain language. Vague verdicts are not allowed. "Mostly passes" must say what it almost-failed on.

### The eight principles

**1. Smallest possible amount of attention.** The product should ask for the least attention it can while still being useful. One job per section. One H1. No competing focal points. No motion in the periphery the user did not request — including sticky headers that re-style on scroll, hero counters that animate, badges that pulse, or anything that draws the eye away from the task.

**2. Inform and create calm.** When the product communicates, it informs without alarming. Server-rendered over skeleton-flickered. No popups, no toasts, no streaks, no badges. Gentle ambient touches (a daily-rotating word, a quiet weather note) are allowed because they inform without demanding response.

**3. Use of the periphery.** The product's transitions and state changes happen at the edge of attention, not the center. Locale switches, theme switches, view changes — these should soft-transition, not white-flash and reload. A user changing a setting should never lose scroll position, focus, or context. If a state change requires a hard reload, that's a calm-tech failure even if the destination is correct.

**4. Amplify human + machine.** The product makes the human better at something they were already trying to do. It is a reference, an instrument, a tool — not an oracle, a coach, or a companion. No "AI suggestions" pushed unsolicited. No chatbot ambient on every page. No gamification. The user is the agent; the machine is the leverage.

**5. Communicate without speaking.** Where possible, communicate state through layout, type, color, and presence — not through copy, alerts, or sound. Hide what isn't ready: a disabled button with "coming soon" tooltip is permanent visible debt across every page it sits on. Render controls only when they work. Absence is information.

**6. Work even when it fails.** The product degrades gracefully. Static content stays available when dynamic services are down. Empty queries return empty arrays, not crashes. The user can still get value if the database, the API, or the network is misbehaving. Calm tech does not have a single point of catastrophic failure visible to the user.

**7. Minimum tech needed.** Use the smallest set of moving parts that delivers the value. This is about *complexity*, not *capability* — on-demand rendering for 10,000 URLs can be calmer than prerendering 200, depending on what's actually built. The question is: for the value being delivered, is there a simpler architecture? If yes, that's the calmer one. Build less, not more.

**8. Respect social norms.** The product behaves the way thoughtful humans behave. It doesn't break URLs that have been indexed for years. It doesn't override settings the user clearly chose elsewhere. It honors locale, time zone, accessibility preferences, and platform conventions. It does not surprise the user with behavior that violates the unwritten rules of its category.

### How to run an audit

For each of the eight, write three to six lines:

- **Verdict.** Passes / Mostly passes / Fails. No "partial credit" hedging without specifics.
- **What's working.** The concrete evidence the principle is honored.
- **What's not.** The specific violation, with file path or component name where possible.
- **Cost to fix.** Two-line edit / a day's work / architectural decision. Distinguishes polish from real debt.

The audit is done in order, every time. Order matters because the principles compound: a product that fails on attention (#1) can't be saved by passing on graceful degradation (#6). Walk all eight even when the early ones fail — the exercise reveals patterns.

### Worked example: Darija.io audit

This is the kind of audit a product should produce. Real, specific, written by someone who knows where the bodies are buried.

> **1. Smallest possible amount of attention — Mostly passes.** Single H1, one search box, one job per section. But: the hero has 3 stat counters fighting for attention right under the search, and the SiteHeader is fixed and goes solid on scroll — that's motion in the periphery the user didn't ask for.
>
> **2. Inform and create calm — Passes.** Daily-rotating Word of the Day is gentle. Server-rendered, no skeleton flickers, no popups, no toasts, no notifications, no streaks, no badges.
>
> **3. Use of the periphery — Fails.** The locale switcher reload (`window.location.reload()`) is the opposite of peripheral — full white flash, scroll position lost, the whole world jumps. A user changing language deserves a soft transition, not a page reset.
>
> **4. Amplify human + machine — Passes.** We're a reference, not an oracle. No "AI suggestions", no chatbot, no gamification.
>
> **5. Communicate without speaking — Mostly passes.** No sound. But: the AudioButton I built shows up disabled on every word page right now, with a tooltip saying "audio coming soon" — that's a permanent visible stub on 10,000 pages. Calm tech says: hide what isn't ready. Don't pre-announce future features in the UI. Render the button only when `audio_url` exists.
>
> **6. Work even when it fails — Passes.** JSON files, no DB, no API dependency at runtime. SSG pages work even if the server is down. `getWordsByRoot` returns `[]` gracefully.
>
> **7. Minimum tech needed — Worth revisiting.** Configured 200 prerendered + on-demand SSG for how-to-say. Build infrastructure can potentially generate 10,000 pages — the open question is whether 10,000 URLs is the right *content surface area*, which is an SEO question rather than a calm-tech question. The render architecture itself is fine. (Reversible in 2 lines if the answer is no.)
>
> **8. Respect social norms — Passes.** Cookie-based locale honors the user's existing setting. No URL surgery on indexed pages. We respect Google's sensitivity around URL changes.

Three failures, three passes, two mostly-passes. That's a healthy audit — the product has a calm spine but specific debts that are now visible and ranked. The next sprint addresses the three failures (or downgrades) before adding any new feature. That's the rule: an audit fails forward — you fix what it surfaces, you don't ship past it.

## Why this is also a business strategy

This skill ends here, but the operational principle continues into product strategy: the calm position is a defensible market position, not a constraint. The ecosystem competes on the axis of "the rare software that respects you," and that axis gets less crowded every year as the rest of the industry races toward more notifications, more friction in cancellation, more dark patterns, more LLM-flavored noise.

Building Calm OS is not building a slower product. It's building a product that will still be trusted in five years, when the user has finally uninstalled everything else.

---

For surface treatment (palette, typography, motion, components), see the `slow-dreamy` skill. For brand-specific voice (Dancing with Lions, Slow Morocco, Riad di Siena, Derb 37), see the relevant voice guides in the project. For UX-level interaction principles (forms, errors, accessibility), see the `ux-design` skill. Calm OS sits beneath all of these and governs the questions they don't answer: what the software does when no one is looking, and what it refuses to do when someone is.
