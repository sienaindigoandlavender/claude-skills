---
name: ux-design
description: Apply UX design principles when building, critiquing, or modifying any user-facing interface — web, mobile, desktop, CLI prompts, dashboards, forms, onboarding flows, emails, error states, empty states, modals, or anything a human has to read, click, type into, or understand. Use this skill whenever the user asks you to design, build, review, improve, "make it more usable," "fix the UX," add a flow, redesign a screen, reduce friction, improve conversion, make something accessible, write microcopy, or when you're generating UI code and need to make interaction decisions. Trigger even when the user doesn't say "UX" — if the output is something a human will interact with, these principles apply.
---

# UX Design

Good UX is mostly about removing things. The default assumption should be that the user is tired, distracted, reading on a phone in bad light, and already halfway to closing the tab. The interface has to earn their attention, not demand it.

This skill gives you a working set of principles to apply when you're designing or reviewing any interface. It's opinionated. When the principles conflict (and they will), the hierarchy near the end tells you how to break ties.

## The actual job

Before anything else, figure out:

1. **Who is using this and what are they trying to do?** Not "user personas." The actual task. "Book a room for next weekend," "cancel a subscription," "understand why my payment failed." If you can't state the task in one sentence, you don't understand it yet.
2. **What's the shortest path from intent to done?** Every screen, field, confirmation, and "are you sure?" that isn't on that path is tax the user pays. Justify each one or cut it.
3. **What happens when it goes wrong?** Empty states, error states, loading states, slow networks, wrong inputs, expired sessions. These are 80% of real use and 10% of most designers' attention.

If the user asks for a "signup flow" or "dashboard" without context, ask one question to anchor the design — what's the primary task, or who's the audience — then commit. Don't interview them to death.

## Core principles

### Hierarchy before decoration
One thing should be the most important thing on the screen. One. If everything is bold, nothing is. If three buttons are the same weight, the user has to read all three. Make the primary action obvious and the secondary action available; tertiary actions can live in a menu or be removed.

### Recognition over recall
Don't make the user remember things across screens. If they picked "Standard shipping" on step 2, show it on step 4. If a form rejects their input, don't clear the field — keep what they typed and point to the problem.

### Match the user's mental model, not your data model
Your database has `users`, `accounts`, `subscriptions`, `billing_profiles`. The user has "my account." Don't expose schema. Don't invent jargon where plain words exist. "Delete account" beats "Terminate user entity."

### Progressive disclosure
Show the common case by default. Hide the rare case behind "Advanced," "More options," or a link. This is not laziness — it's respect for the 95% who don't need the setting. But make the hidden thing findable with one click, not five.

### Feedback is non-negotiable
Every action needs a response within ~100ms, even if the response is "working on it." Buttons that don't show a pressed state, forms that submit silently, operations that disappear into a void — these make interfaces feel broken even when they're working. Loading spinners are a feedback minimum, not a design choice.

### Defaults carry enormous weight
Most users never change defaults. Choose them to serve the typical case, not the flexible case. A signup form with "Subscribe to marketing emails" pre-checked is a dark pattern; one with it unchecked is ethical design. Same checkbox, opposite meaning.

### Forgiving over strict
Let users undo things. Confirm only the destructive and irreversible. "Are you sure?" on every save trains users to click through confirmations without reading — which means the one that actually mattered gets ignored too. Soft delete with an undo toast beats a modal asking "Really delete?"

### Make the irreversible feel irreversible
When something truly can't be undone — deleting an account, canceling a non-refundable booking, sending a transaction — the friction should match the stakes. Type-to-confirm, a second screen, or a cooling-off period are all legitimate here. Everything else should be one click and undoable.

## Information architecture

How you group and name things is the design. Most "bad UX" is actually bad IA — the right button is in the wrong place with the wrong label, so nobody finds it.

- **Group by task, not by feature.** A settings page organized around "what the user wants to do" (change password, manage notifications, export data) beats one organized around "what the engineering team built" (Auth, Prefs, Data Ops).
- **Label with verbs for actions, nouns for things.** Buttons say "Save changes," not "Changes." Nav items say "Orders," not "View orders list."
- **Depth kills.** Three levels of nesting is a lot. Five is a wayfinding problem. Prefer flat structures and good search over deep trees.
- **The back button must work.** If your app breaks the browser's back button or the phone's back gesture, users will get lost and angry. This is not optional.

## Forms

Forms are where most interfaces go to die. Rules:

- **Ask for the minimum.** Every field is friction. If you don't need it to complete the task, don't ask. "Phone number (optional)" is usually a lie — either you need it or you don't.
- **One column.** Multi-column forms force the eye to jump around and are terrible on mobile.
- **Labels above fields, not beside or inside.** Inside-the-field labels (placeholder-as-label) disappear when the user types and hurt accessibility.
- **Use the right input type.** `type="email"` on mobile shows the `@` key. `type="tel"` shows the number pad. `inputmode="numeric"` for codes. `autocomplete` attributes let password managers do their job.
- **Validate on blur, not on keystroke.** Showing "Invalid email" while someone is typing "j" is hostile. Validate when they leave the field or submit.
- **Errors should point at the field and say what to do.** Not "Invalid input." Not a red banner at the top listing field numbers. Inline, specific, actionable: "Password needs at least one number."
- **Never clear a form on error.** Losing 30 seconds of typing because one field was wrong is grounds for rage-quit.
- **Show password requirements before the user types**, not after they fail. Or better — accept any password with a real strength indicator and enforce length only.

## Microcopy

Words are UI. A button that says "Submit" is worse than one that says "Create account" or "Book room." Specific verbs that describe the outcome always beat generic ones.

- **Plain language over clever.** Clever is a tax on comprehension and a disaster in translation.
- **Second person, active voice.** "Your booking is confirmed" not "The booking has been confirmed by the system."
- **Don't apologize for working correctly.** "We're sorry, but you need to log in" — no you're not. "Log in to continue" is fine.
- **Error messages should locate the problem, explain it, and suggest a fix** — in that order, in one sentence if possible.
- **Empty states are an opportunity, not a void.** "No results" is a dead end. "No results for 'xyz' — try a different search or browse categories" keeps the user moving.

## Accessibility

Accessibility is not a compliance checkbox bolted on at the end. It's a design constraint from the start, and designs that ignore it are worse for everyone, not just disabled users.

- **Color contrast ≥ 4.5:1 for body text, 3:1 for large text.** Gray-on-white trends are an accessibility disaster. Check with a contrast tool, not with your eyes.
- **Never use color as the only signal.** "Required fields are in red" fails for colorblind users. Add an asterisk, a label, an icon — anything additional.
- **Every interactive element needs a name a screen reader can read.** Icon-only buttons need `aria-label`. Inputs need `<label>`. Images need `alt` (or empty `alt=""` if purely decorative).
- **Keyboard navigation must work.** Tab through every interactive element; the focus ring must be visible (never `outline: none` without replacement); order must be logical.
- **Target size ≥ 44×44px on touch devices.** Tiny tap targets are an accessibility issue before they're a usability issue.
- **Don't disable zoom.** `user-scalable=no` is user-hostile. People need to zoom.
- **Motion: respect `prefers-reduced-motion`.** Some users get motion sick from parallax and big transitions. Wrap non-essential animation in the media query.

## Mobile

Design for mobile first, not because it's trendy but because constraints breed clarity. If it works at 375px wide on a bad connection, it'll work everywhere.

- **Thumb reach matters.** The top of the screen is hard to reach on a phone held one-handed. Primary actions belong near the bottom. This is why iOS moved the address bar down.
- **Don't fake native.** Hamburger menus, bottom tabs, and swipe gestures all have platform conventions. Respect them. A web app that tries to look like a native app but misses the details ("back swipe doesn't work, pull-to-refresh doesn't work") is worse than one that just looks like a web app.
- **Forms on mobile: input type and autocomplete are not optional.** See the forms section.
- **Test on a real phone or at least on a throttled connection.** Desktop Chrome on a gigabit line lies about how your site feels.

## Interaction patterns — when to use what

**Modal dialog:** For a task that needs the user's full attention and blocks everything else. Confirming a destructive action. A focused sub-task they need to finish before moving on. Not for marketing. Not for announcements. If you find yourself putting a modal on top of a modal, you've lost.

**Toast / snackbar:** For confirmation of something that already happened — "Saved," "Deleted (undo)." Ephemeral, non-blocking. Not for errors the user needs to act on.

**Inline message:** For errors and warnings next to the thing they're about. A form field error belongs next to the field, not in a toast.

**Banner:** For persistent system-wide state — "You're offline," "Payment method expiring." Dismissible, but reappears if the condition persists.

**Tooltip:** For progressive disclosure of secondary info. Must not contain essential info (not keyboard-accessible for touch users). Never put a button inside a tooltip.

**Skeleton loader vs spinner:** Skeleton for content that has a predictable shape (list, card, article). Spinner for action-in-progress or unknown shape. Skeleton feels faster because the user's brain starts parsing layout before data arrives.

## Things to stop doing

Patterns that keep appearing in AI-generated UIs and should not:

- **The purple gradient.** Every AI demo looks the same. Commit to a real palette.
- **"Get started" and "Learn more" side-by-side with equal weight.** Pick a primary. One button. The other is a text link.
- **Three-card feature grids with an icon, a heading, and one sentence each.** Generic. Says nothing. Usually the heading and sentence are interchangeable.
- **Glassmorphism everywhere.** A frosted-glass card on a frosted-glass background on a gradient makes text unreadable. Use it for one thing, at most.
- **Modal on page load.** Newsletter popup before the user has read anything. Cookie banner that covers the content. These are the interface equivalent of a stranger stopping you at the door.
- **Infinite scroll with a footer.** Users can never reach the footer. Either paginate or move footer content elsewhere.
- **"Are you sure?" on every action.** See "Forgiving over strict."
- **Carousels that auto-advance.** Nobody reads them. They move away before the user finishes the sentence. If you must have a carousel, let the user control it.
- **Disabled buttons with no explanation.** A grayed-out "Submit" button with no hint why it's disabled is a puzzle. Say what's missing, or don't disable it — validate on click and show the error.

## Dark patterns — don't

The line between persuasion and manipulation is whether the design serves the user's goal or only the business's goal. Don't:

- Pre-check consent boxes. Pre-select expensive options. Hide the free tier.
- Make the unsubscribe link tiny and gray while the "stay subscribed" button is huge and colored.
- Use guilt copy ("No thanks, I don't want to save money").
- Add confusing double negatives to opt-outs.
- Auto-renew subscriptions silently without a reminder before the charge.
- Fake urgency ("Only 1 left!" when there are 10,000).

These tactics work short-term and destroy trust long-term. If you're asked to implement one, flag it.

## Reviewing an existing interface

When the user hands you a screenshot, a URL, or code and asks you to improve the UX, work in this order:

1. **Identify the task.** What is the user here to do? Can they do it?
2. **Find the primary action.** Is it obvious within 2 seconds? Is there exactly one?
3. **Trace the happy path.** How many clicks, fields, and decisions from start to done? Can any be cut?
4. **Stress-test the unhappy paths.** What happens on error, empty, slow, offline?
5. **Audit copy.** Does every label, button, and message describe the actual outcome in plain language?
6. **Check accessibility basics.** Contrast, focus states, labels, keyboard nav, target sizes.
7. **Then and only then consider visual polish.** A beautiful interface that doesn't work is just a rendering.

Give the user your top 3-5 issues, not a 40-item list. Ranked by impact, not by how easy they are to fix.

## Tie-breaking hierarchy

When principles conflict:

1. **Safety and accessibility** beat everything. Don't ship interfaces that mislead users into losing data or exclude users who can't see color.
2. **Task completion** beats aesthetics. A plain form that works beats a gorgeous one that confuses.
3. **Clarity** beats cleverness. If you have to explain a joke or metaphor in the UI, cut it.
4. **Consistency** beats novelty. Users have learned where the close button goes. Don't be creative about it without a reason.
5. **Then** optimize for delight, brand, and memorability.

## When to push back

If the user asks you to build something that violates these principles — "make the unsubscribe link gray," "pre-check the marketing consent," "hide the cancel button" — say so. You don't have to refuse, but name it. They may have a reason. They may not have thought about it. Either way, the conversation is more useful than silent compliance.

---

For deeper reference on specific areas, see:
- `references/forms.md` — detailed form patterns, validation, autofill
- `references/accessibility.md` — WCAG essentials, ARIA patterns, testing
- `references/patterns.md` — full catalog of interaction patterns with use cases
