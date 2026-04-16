# Motion

The feel of an interface lives in its motion. Slow-dreamy motion is slow in *expression* (how things unfold) but fast in *response* (how quickly the interface acknowledges input).

## Timing scale

```css
--duration-fast: 150ms;     /* button press, checkbox tick */
--duration-base: 300ms;     /* state changes, hover, most transitions */
--duration-slow: 500ms;     /* view change, page transitions */
--duration-ambient: 2000ms; /* background effects, breathing */
```

## Easing curves

```css
--ease-gentle: cubic-bezier(0.22, 1, 0.36, 1);   /* the default, settles softly */
--ease-soft: cubic-bezier(0.4, 0, 0.2, 1);       /* slightly tighter, for chrome */
--ease-slow-out: cubic-bezier(0.16, 1, 0.3, 1);  /* even gentler, for arrivals */
```

Use `--ease-gentle` as the default for anything the user triggers. Use `--ease-slow-out` for things that arrive unbidden (page load, content streaming in).

Avoid `linear` (robotic), `ease-in` (feels accelerating), `ease-in-out` (feels snappy), and any bounce (childish for this aesthetic).

## Recipe: fade-and-rise on arrival

Content appears with a soft upward drift:

```css
@keyframes fade-rise {
  from {
    opacity: 0;
    transform: translateY(12px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.fade-rise {
  animation: fade-rise var(--duration-slow) var(--ease-slow-out) both;
}
```

## Recipe: staggered list reveal

Items appear one after another, not all at once:

```css
.list-stagger > * {
  opacity: 0;
  animation: fade-rise var(--duration-slow) var(--ease-slow-out) forwards;
}

.list-stagger > *:nth-child(1) { animation-delay: 0ms; }
.list-stagger > *:nth-child(2) { animation-delay: 60ms; }
.list-stagger > *:nth-child(3) { animation-delay: 120ms; }
.list-stagger > *:nth-child(4) { animation-delay: 180ms; }
.list-stagger > *:nth-child(5) { animation-delay: 240ms; }
.list-stagger > *:nth-child(6) { animation-delay: 300ms; }
/* cap around 8 items; longer lists should use IntersectionObserver */
```

Each item 50–80ms after the previous. Under 50ms, the stagger is imperceptible. Over 100ms, it feels slow.

For long lists, use JavaScript + IntersectionObserver so items only reveal when they scroll into view, not all at once on page load.

## Recipe: breathing (ambient motion)

Very subtle scale/opacity oscillation, for focus indicators, loading states, or empty-state icons. Should be so subtle the user almost doesn't notice — it just feels alive.

```css
@keyframes breathe {
  0%, 100% {
    opacity: 0.6;
    transform: scale(1);
  }
  50% {
    opacity: 1;
    transform: scale(1.04);
  }
}

.breathing {
  animation: breathe var(--duration-ambient) var(--ease-gentle) infinite;
}
```

Period of 2–3 seconds. Faster reads anxious; slower reads dead.

## Recipe: cross-fade view change

Instead of hard-swapping views, cross-fade:

```css
.view {
  transition: opacity var(--duration-base) var(--ease-gentle);
}

.view.leaving {
  opacity: 0;
}

.view.entering {
  opacity: 0;
}

.view.entered {
  opacity: 1;
}
```

In React / JS: mark the outgoing view `leaving`, wait 300ms, unmount and mount the new view as `entering`, on next frame add `entered`. Feels considered.

## Recipe: hover with delay

Hovers that appear too quickly feel jumpy. Adding a tiny delay — 60–100ms — makes them feel more intentional:

```css
.hover-reveal {
  opacity: 0;
  transition: opacity var(--duration-base) var(--ease-gentle) 80ms;
}

.hover-reveal-trigger:hover .hover-reveal {
  opacity: 1;
  transition-delay: 0ms; /* no delay when appearing */
}
```

The delay on disappearance (not appearance) means the element stays visible just a moment longer when the mouse leaves — prevents flicker if the user accidentally moves off then back.

## Recipe: gentle focus ring

Default browser focus outlines are harsh. Replace with a soft warm ring:

```css
*:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 3px;
  transition: outline-offset var(--duration-base) var(--ease-gentle);
}

/* Or a glow style */
.focus-glow:focus-visible {
  outline: none;
  box-shadow: 0 0 0 3px var(--accent-soft),
              0 0 0 4px var(--accent);
}
```

## Recipe: checkbox check-draw

When a checkbox is ticked, draw the check rather than pop it in. See `components.md` for the full pattern. The principle: the check element exists at scale(0), and on :checked transitions to scale(1) with ease-gentle over 200ms. Small detail, huge feel.

## Recipe: page-load sequence

On page load, don't dump everything at once. Orchestrate:

1. Background fades in (0–200ms, ease-out)
2. Heading appears with fade-rise (200–700ms)
3. Body text appears with fade-rise, 100ms after heading (300–800ms)
4. CTA appears last, fade-rise (500–1000ms)
5. Secondary content (sidebar, footer) stagger in 800ms+

Total choreography: under 1.5 seconds. The user feels the page "compose itself" rather than "land all at once."

```css
.hero-intro > * {
  opacity: 0;
  animation: fade-rise var(--duration-slow) var(--ease-slow-out) forwards;
}

.hero-intro > *:nth-child(1) { animation-delay: 200ms; }
.hero-intro > *:nth-child(2) { animation-delay: 400ms; }
.hero-intro > *:nth-child(3) { animation-delay: 600ms; }
.hero-intro > *:nth-child(4) { animation-delay: 800ms; }
```

## Things not to do

**Don't parallax.** The single least calm effect on the web. If your instinct is "add some parallax to make the page feel alive" — resist. Parallax adds motion unrelated to user input, which is the opposite of slow-dreamy.

**Don't bounce.** `cubic-bezier` curves with overshoot (values > 1) read childish. No spring physics unless it's a very specific moment.

**Don't auto-scroll.** No carousels that move on their own. No text that scrolls on arrival. The user controls scroll; the interface responds.

**Don't loop attention-seeking animation.** A button that pulses until clicked is begging. A breathing empty-state icon is ambient; an infinitely animated CTA is needy. Know the difference.

**Don't chain too many staggered animations.** Past about 8 items, the user has stopped waiting. Cap stagger sequences around 6–8 items; beyond that, items should appear together or on scroll.

**Don't ignore `prefers-reduced-motion`.** Wrap all non-essential motion:

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

Some users get vestibular symptoms from motion. Honoring their preference is non-negotiable.

## Framework-specific notes

### Framer Motion (React)

```jsx
import { motion } from 'framer-motion'

const fadeRise = {
  initial: { opacity: 0, y: 12 },
  animate: { opacity: 1, y: 0 },
  transition: {
    duration: 0.5,
    ease: [0.16, 1, 0.3, 1]
  }
}

<motion.h1 {...fadeRise}>Good morning</motion.h1>
```

For staggered children:

```jsx
const container = {
  animate: {
    transition: { staggerChildren: 0.07 }
  }
}

const child = {
  initial: { opacity: 0, y: 12 },
  animate: { opacity: 1, y: 0, transition: { duration: 0.5, ease: [0.16, 1, 0.3, 1] } }
}

<motion.ul variants={container} initial="initial" animate="animate">
  {items.map(item => <motion.li variants={child}>{item}</motion.li>)}
</motion.ul>
```

### CSS-only page load

If you don't want JS for entrance animations:

```css
@media (prefers-reduced-motion: no-preference) {
  .enter-on-load {
    opacity: 0;
    animation: fade-rise 0.6s cubic-bezier(0.16, 1, 0.3, 1) forwards;
  }
}
```

Browsers will animate this once on page load, nothing more. Lighter than JS for landing pages.
