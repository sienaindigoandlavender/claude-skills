---
name: slow-dreamy
description: Design interfaces in a calm, unhurried, slightly dreamy aesthetic — the "Sunsama school" of productivity design, softened with more warmth and poetry. Use this skill whenever the user asks for a calm/soft/dreamy/gentle/unhurried/serene/peaceful/zen/mindful interface, asks you to emulate Sunsama, Things 3, Linear's softer moments, Stripe's press pages, Craft, Bear, or the "productivity but make it beautiful" genre. Also use when the user asks for an interface that should feel slow on purpose, reduce anxiety, support deep work, welcome rather than demand, or when they use words like "warm," "editorial-calm," "gentle," "breath," "quiet," or "sanctuary" about a UI. Trigger even if the user doesn't name Sunsama — if the vibe is slow, soft, warm, or dreamy, these principles apply.
---

# Slow, Dreamy Interfaces

A design system for interfaces that do the opposite of demanding attention. They welcome. They let the user arrive.

The reference points: Sunsama's calm productivity plane, early-morning light through a window, a well-made notebook, a quiet room. Not minimal in the austere Swiss-poster sense — minimal in the way a tended garden is minimal. Restrained, not cold.

This skill is about the *feel*, not the literal visual of any one app. You're encoding a philosophy that can dress a calendar, a meditation app, a private journal, a boutique hotel's booking flow, or a wellness dashboard — anything that should feel like the user is the most important thing in the room.

## The core ethos

### Time is a design material

Slow interfaces don't rush the user, and they don't rush themselves. Animations are 300–600ms, not 150. Transitions ease out, settling like a book closing. Hover states bloom, they don't snap. The interface moves at the pace of a long exhale.

But slow is not sluggish. Response time — the gap between input and first feedback — should still be under 100ms. What's slow is the *expression*, not the acknowledgment.

### Warmth over whiteness

The default "clean" interface is pure white (#FFFFFF) with gray (#666666) text. That reads sterile — hospital, spreadsheet, office. Dreamy interfaces live in warm off-whites: creams, parchments, bone, candlelight. Text is never black; it's a deep warm gray or near-black with hue. The whole palette shifts half a degree toward warm.

### Restraint is the flex

The temptation with a "beautiful productivity app" aesthetic is to pile on: gradients, soft shadows, illustrated icons, rounded-everything, pastels. Stop at about 40% of what feels like enough. One or two soft accents on a warm neutral background beats three pastels, a gradient, and a watercolor illustration.

### Breath

Whitespace is the feature, not the absence of a feature. A slow-dreamy interface should feel under-populated on first glance, then reveal its density as the user settles in. If the page is full above the fold, it's too full.

## The palette

### Backgrounds — warm neutrals

These replace pure white:

- `#FBF9F4` — candlelight cream, the most versatile base
- `#F7F2EA` — warmer parchment, for hero sections or focus mode
- `#FAF7F0` — bone, cooler than cream but still warm
- `#EEE8DB` — soft linen, for surfaces that need to recede (sidebars, cards on cream)

Pure white (#FFFFFF) is reserved for elevated surfaces — input fields, modal interiors — where you want a subtle lift. The white pops *against* cream and reads as "bright," which it couldn't do against itself.

### Ink — warm dark

Replace black with:

- `#2B2623` — the darkest you should go, a warm near-black for headlines
- `#3E3630` — body text
- `#6B5F55` — secondary text, captions
- `#9C8E82` — tertiary, dividers, hints

These read dark without the sharpness of true black on true white. The whole page has a slight sepia undertone.

### Accents — muted, not pastel

Pick one or two, never more. All muted to around 50–60% saturation:

- `#A8826F` — terracotta, the most Sunsama-adjacent
- `#8B9D7F` — sage, for success and nature contexts
- `#C4A574` — soft gold, for emphasis and premium feel
- `#7B8A99` — dusty blue, for calm/trust
- `#B08A8A` — muted rose, for wellness, warmth
- `#6B7B6E` — forest, darker sage, for depth

Avoid pastel-candy colors (#FFE4E1, #E0F7FA). They read childish, not calm. Muted warm-undertone colors read adult and considered.

### What to avoid

- Pure white on black or pure black on white (too much contrast is un-calm)
- Saturated primaries (red #FF0000, blue #0000FF) — reads as alert, not welcome
- Gradients with more than two stops, or any gradient involving purple
- Pure cool grays (they read corporate)
- Neon anything

## Typography

The typography does enormous work here. This is where most "calm" attempts fail — they use Inter or system sans on warm cream and wonder why it still feels like a SaaS dashboard.

### Pairing strategy

A dreamy interface needs **one serif** (for warmth and slowness in reading) and **one humanist sans** (for UI controls, small text, anything that needs to be scanned quickly). Possibly a third face for numerals or display.

### Good serif choices

- **Fraunces** — variable, warm, a little theatrical, free on Google Fonts
- **Tiempos** — the Kinfolk/Cereal choice, paid but worth it
- **GT Sectra** — editorial, elegant, has great italic
- **Cormorant Garamond** — free, romantic, extremely slow-feeling (use with restraint — can get precious)
- **Lora** — free, friendly, more approachable than the above
- **Newsreader** — free, designed for long-form reading, warm

### Good sans choices

- **Inter** — workhorse; use it for UI chrome if you must, but pair it with a real serif
- **Söhne** — not free, but the go-to for premium calm products
- **General Sans** — free, friendly, a little rounded without being childish
- **Satoshi** — free, humanist, modern
- **ABC Diatype** — editorial, calm, paid
- **Public Sans** — free, US government-issued; surprisingly good for UI

### Type scale

Slow interfaces use larger type than conventional UIs. Body text 16–18px minimum, often 18–20px. Line-height generous — 1.6 to 1.8 for body, 1.3 to 1.4 for headlines. Letter-spacing: slight positive tracking on small caps and labels (+0.05em); slight negative on large headlines (-0.02em).

Serif for headlines and any text the user is meant to *read*. Sans for labels, buttons, metadata, navigation — things they're meant to scan.

## Layout

### Generous margins, not edge-to-edge

The 21st-century default is content spanning the full viewport width. Slow interfaces pull content inward. Max content width 640–720px for reading, 1100–1200px for app layouts. On wide screens, the empty side space is the point — it's the matte around the photograph.

### Vertical rhythm

Establish a baseline (usually 8px) and stick to it. Sections separated by generous multiples — 64px, 96px, 128px between major blocks. Cramped sections feel anxious; spacious ones feel like chapters.

### Asymmetry and off-center composition

Perfect centering reads corporate. Slight off-center layouts — content skewed 55/45 on a split, images offset, text blocks not quite aligned to images — feel more natural, more editorial. Think of a magazine spread, not a slide deck.

### No visual noise at rest

The interface should look almost empty when nothing's happening. No persistent notification badges unless there's genuine news. No "You have 3 unread" counters glowing at the user. No promotional banners. The interface is a room, and a calm room is tidy.

## Motion

### Timing

- **Fast feedback** (button press, checkbox toggle): 120–180ms
- **Transitions** (view change, expand/collapse): 300–450ms
- **Arrivals** (page load, content appearing): 500–700ms, often with stagger
- **Ambient** (background shifts, breathing animations): 2–6 seconds

### Easing

Use ease-out or custom cubic-bezier curves that decelerate gently. Default to `cubic-bezier(0.22, 1, 0.36, 1)` — it settles. Avoid linear (robotic), ease-in-out (snappy), or bounce (childish). Slow-dreamy motion always ends gentler than it begins.

### Specific moves

- **Fade + subtle rise** (10–20px translateY) for content appearing. Not "zoom in," not "slide from the right."
- **Staggered reveals** on lists — each item 50–80ms after the previous. Creates a sense of the page "composing itself."
- **Breathing** — very subtle scale (0.98 → 1.02) on focus indicators or loading states, over 2–3 seconds.
- **Cross-fade** for view changes — not hard swaps.
- **Respect `prefers-reduced-motion`** — all of this must gracefully degrade. Some users get sick from motion. Non-negotiable.

### What to avoid

- Parallax scrolling (the least calm effect ever invented)
- Elements flying in from off-screen at high speed
- Loading spinners that spin fast (use a slow pulse instead)
- Anything that loops forever unprompted (attention-seeking)

## Surfaces and shadows

### Shadows are soft and warm

Pure-black shadows (rgba(0,0,0,0.1)) read sharp. Use warm-toned shadows:

```css
/* Soft, warm shadow for cards */
box-shadow: 0 2px 8px rgba(75, 58, 47, 0.04),
            0 8px 24px rgba(75, 58, 47, 0.06);
```

The color (#4B3A2F-ish, warm brown) tints the shadow to sit correctly on cream.

### Borders are hair-thin or absent

- 1px borders in a warm low-saturation color (#E5DCCF) for dividers
- No borders at all on cards — let soft shadows do the work
- Never use borders of multiple weights in the same view

### Rounded corners, moderately

- 8–12px on cards and inputs (not 4, not 24)
- 16–24px on modals and sheets
- Full-round (pill) only on tags, chips, and maybe primary buttons — not on everything

Rounded-everything is a cliché. Specific things are rounded; others aren't.

## Interaction details

### Buttons

Primary buttons are solid but muted — never saturated. The accent color at 90% opacity on cream, with 1–2px inset highlight on top for dimension. Hover raises shadow and slightly lightens (3-5% only). Press state depresses by 1px — don't go bigger.

Secondary buttons are transparent with a 1px warm border, filling gently on hover.

Tertiary actions are text links with a subtle underline or an underline-on-hover. Don't disguise buttons as text; tertiary actions should read as links.

### Inputs

- Underline-only inputs (just a bottom border) feel more editorial than boxed inputs. Both work.
- On focus, the border thickens and color-shifts to the accent, with a very gentle glow (2–4px, 10% opacity).
- Labels above inputs, never placeholders-as-labels (standard UX, but extra important here — placeholders disappearing is a small anxiety).

### Checkboxes and toggles

Custom, not browser default. Checked state animates with a slight bounce-free ease, the check drawing in over 200ms. Toggles glide; never snap.

### Hover states

Subtle. A shift in background by 2–4% lightness. A color change on icons by 5–10% opacity. Nothing dramatic — the user shouldn't feel a jolt when moving the cursor.

## Copy and microcopy

Design doesn't stop at pixels. Calm interfaces sound calm.

- **Plain language.** "Good morning" over "Welcome back, User!"
- **Present tense, active voice.** "Your day is ready" not "Your day has been prepared."
- **No exclamation points** except in the one place they belong (a genuine celebration, maybe once). "Saved!" is fine. "Welcome!" and "Let's go!" and "Amazing!" are not.
- **No urgency language.** "Last chance!" "Don't miss out!" "Act now!" — none of it. If the product is actually calm, the marketing should be too.
- **Warmth without performance.** "We're so excited to see you!" is performative warmth. "Hi, Jacqueline." is real warmth.
- **The interface can be a little poetic** in moments that deserve it — empty states, end-of-day, welcome screens. Not every button. Save poetry for when it lands.

Example transformations:

| Default SaaS | Slow-dreamy |
|---|---|
| "Welcome back!" | "Good morning, Jacqueline." |
| "3 tasks remaining" | "Three things left today." |
| "No items found" | "Nothing here yet." |
| "Error: Invalid email" | "That doesn't look like an email — mind checking?" |
| "Success!" | "Saved." |
| "Sign Up Now" | "Begin" |

## Imagery and illustration

### Photography

If you use photos, use film-graded ones. Warm, soft-focus, natural light — not stock-photo polished. People photographed from behind or in action, never smiling at the camera. Still life over lifestyle.

### Illustrations

Hand-drawn, single-line, or watercolor — never flat-vector-with-gradients (the "Corporate Memphis" illustration style is the antithesis of dreamy). Use sparingly. One illustrated moment in an interface is memorable; five is a kids' app.

### Icons

- **Feather** or **Lucide** — thin, open, consistent. Good default.
- **Phosphor (thin weight)** — slightly warmer feel, good for this aesthetic.
- 1.5px stroke weight, rarely filled.
- Never more than one icon style in the same interface.

## Dark mode

Slow-dreamy dark mode is hard. Most dark modes are cold blue-black (#1A1D2E territory). That ruins the warmth.

Instead:

- Background: `#1F1B17` — warm near-black, like burnt sienna dragged to near-black
- Surface: `#2A2521` — a step up, for cards
- Text: `#EDE5D8` — off-white with warm undertone (not #FFFFFF)
- Accents: take the light-mode accent and lighten by 10-15%, keep the same hue

Test by squinting. If it feels like a coffee shop at dusk, it's right. If it feels like a Discord window, it's wrong.

## Common mistakes and how to avoid them

**Mistake:** Using cream background + pure black text.
**Fix:** Warm near-black (#2B2623). Pure black on cream is uncomfortably high contrast and kills the softness.

**Mistake:** Adding a "soft shadow" using `rgba(0,0,0,0.1)`.
**Fix:** Warm-toned shadow. The black tint reads cold against cream.

**Mistake:** Using one serif for everything.
**Fix:** Serif for reading, sans for interface chrome. Pure-serif UIs become precious and hard to scan.

**Mistake:** Pastel color palette (mint + peach + lavender + butter).
**Fix:** One or two muted accents, max. Pastel overload reads baby product, not adult sanctuary.

**Mistake:** Floating, floaty, full-of-decoration.
**Fix:** Calm is usually *less* ornament, not more. Trust the typography and spacing to carry the feel.

**Mistake:** "Calm" landing page that then opens into a normal SaaS dashboard.
**Fix:** The whole experience must hold the aesthetic. If the login screen is dreamy and the app interior is Material Design, the spell breaks the moment the user logs in.

**Mistake:** Motion that's merely slow, not *eased*.
**Fix:** Slowness without easing is just lag. A 500ms linear transition feels broken. A 500ms ease-out transition feels considered.

## When to use this aesthetic

- Productivity tools that explicitly position as "calm" or "mindful"
- Journaling, meditation, wellness apps
- Reading apps, writing apps, note-taking apps
- Personal finance for humans (not day-traders)
- Boutique hospitality, small luxury, slow-travel
- Editorial publications, long-form content
- Creative tools (for writers, designers, artists) where focus is the value proposition

## When not to use it

- Transactional flows where speed is the virtue (checkout, trading, emergency)
- Utility apps where calm would read as slow performance (maps, search, messaging)
- Anything where a loud brand is the value (gaming, sports, entertainment)
- Dashboards where alerts need to actually alert

The aesthetic trades urgency for considered-ness. If urgency is the feature, pick a different aesthetic.

---

For deeper detail, see:
- `references/tokens.md` — complete CSS custom properties for the design system
- `references/components.md` — worked examples for buttons, cards, inputs, nav
- `references/motion.md` — specific timing functions and animation recipes
