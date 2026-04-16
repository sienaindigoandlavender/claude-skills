# Accessibility: the working subset

WCAG is long. These are the pieces that catch 90% of real issues. Treat them as a floor, not a ceiling.

## Semantic HTML first

Before reaching for ARIA, use the right element. A `<button>` is keyboard-accessible, screen-reader-announced, and focusable by default. A `<div onclick>` is none of those — and making it accessible requires `role`, `tabindex`, keyboard handlers, and focus styles you'll probably get wrong.

Rule of thumb: **no ARIA is better than bad ARIA.** If you're using `role="button"` on something, you should have used `<button>`.

Common swaps:
- Use `<button>` for actions in the page
- Use `<a href>` for navigation to another page
- Use `<label>` for form fields
- Use `<nav>`, `<main>`, `<header>`, `<footer>` for landmarks
- Use `<h1>`–`<h6>` in order, not skipping levels, not chosen for size
- Use `<ul>`/`<ol>` for lists, not `<div>`s with bullets

## Color contrast

- **4.5:1** for body text against background
- **3:1** for large text (18pt+ or 14pt+ bold)
- **3:1** for UI components (borders of inputs, icons that convey meaning)

Gray text on white is the most common violation. `#999` on white is 2.8:1 — fails. `#757575` is 4.5:1 — passes. Check with a contrast checker (browser DevTools now have one built in), don't guess.

Don't lower contrast for "elegance." Thin gray text is a readability problem before it's an accessibility problem.

## Color alone is never the signal

If the only thing distinguishing required fields is red, or the only thing distinguishing an error from normal is color, you've failed colorblind users (about 1 in 12 men) and anyone on a bad screen.

Add a second channel: icon, asterisk, label, underline, shape, text.

## Keyboard navigation

Every interactive element must be reachable and operable with keyboard alone.

- **Tab order follows visual order.** If tab jumps around the page randomly, you've probably broken it with `tabindex` values greater than 0. Use `tabindex="0"` (include in natural order) or `tabindex="-1"` (focusable by script, not in tab order). Never positive values.
- **Focus must be visible.** Never `outline: none` without a replacement. The default browser outline is ugly; fine, replace it with a ring that matches your design. Don't remove it.
- **Esc closes modals and dropdowns.** Enter submits forms and activates buttons. Space activates buttons and toggles checkboxes. Arrow keys navigate within radio groups, menus, tabs, and custom widgets.
- **Skip links.** "Skip to main content" link as the first focusable element, hidden until focused. Lets keyboard users bypass nav.

## Focus management

When something appears or moves, focus usually needs to follow.

- **Opening a modal**: move focus into the modal, trap it there (tab cycles within), restore focus to the trigger on close.
- **Route change in SPA**: move focus to the new page's heading or main landmark. Without this, screen reader users don't know they're on a new page.
- **Deleting a row**: move focus to the next row, or to the table caption if it was the last.
- **Submitting a form with errors**: move focus to the first error field.

## Screen reader essentials

- **Every image needs `alt`.** Decorative images get `alt=""` (empty, not missing) to signal "skip this." Functional images (icons in icon-only buttons) need descriptive alt or an `aria-label` on the button.
- **Every form input needs a label.** `<label for>`, wrapping `<label>`, or `aria-label` / `aria-labelledby` when a visible label isn't possible.
- **Icon-only buttons need `aria-label`.** `<button aria-label="Close">✕</button>`.
- **Loading states need announcement.** `aria-live="polite"` region that updates when content loads, so screen readers announce it.
- **Errors need announcement.** `role="alert"` on the error message element, or `aria-live="assertive"` for urgent errors.

## Zoom and reflow

- **Don't disable zoom.** `<meta name="viewport" content="..., user-scalable=no">` is hostile. Remove it.
- **Content must reflow at 400% zoom** without horizontal scrolling (WCAG 1.4.10). This means fluid layouts, relative units, no fixed-width containers past a certain size.
- **Line length: 45–80 characters** for readable body text. Full-width text on a wide monitor is unreadable.

## Motion and animation

- **Respect `prefers-reduced-motion`.** Some users get vestibular symptoms (dizziness, nausea) from parallax, big transitions, and autoplay video. Wrap non-essential motion:

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

- **Don't autoplay video with sound.** Ever.
- **Flashing content**: nothing should flash more than 3 times per second (seizure risk).

## Target sizes

- **44×44 CSS pixels minimum** for touch targets (WCAG 2.5.5). This is about a fingertip.
- Small icons can stay small visually if the hit area is padded out to 44×44 with `padding` on the button.

## Testing

Minimum passes before shipping:

1. **Tab through the whole page.** Can you reach everything? Is the order logical? Is focus visible?
2. **Run axe DevTools** (browser extension) or Lighthouse accessibility audit. Fix everything it flags.
3. **Turn on a screen reader** (VoiceOver on Mac is Cmd+F5; NVDA on Windows is free) and navigate the page. Does it make sense?
4. **Zoom to 200% and 400%.** Does anything break?
5. **Check contrast on every text/background combination.**

Automated tools catch ~30% of issues. Manual keyboard and screen reader testing is not optional for anything serious.
