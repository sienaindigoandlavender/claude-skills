# Component recipes

Worked examples for the most common UI elements, tuned to the slow-dreamy aesthetic. All assume the tokens from `tokens.md` are loaded.

## Buttons

### Primary

```css
.btn-primary {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: var(--space-2);
  padding: var(--space-3) var(--space-6);
  background: var(--accent);
  color: var(--bg-base);
  font-family: var(--font-sans);
  font-size: var(--size-sm);
  font-weight: 500;
  letter-spacing: 0.01em;
  border: none;
  border-radius: var(--radius-md);
  box-shadow: var(--shadow-sm),
              inset 0 1px 0 rgba(255, 255, 255, 0.15);
  cursor: pointer;
  transition: transform var(--duration-fast) var(--ease-gentle),
              box-shadow var(--duration-base) var(--ease-gentle),
              background var(--duration-base) var(--ease-gentle);
}

.btn-primary:hover {
  background: var(--accent-strong);
  box-shadow: var(--shadow-md),
              inset 0 1px 0 rgba(255, 255, 255, 0.15);
}

.btn-primary:active {
  transform: translateY(1px);
  box-shadow: var(--shadow-xs),
              inset 0 1px 0 rgba(255, 255, 255, 0.15);
}

.btn-primary:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 3px;
}
```

### Secondary (ghost with border)

```css
.btn-secondary {
  padding: var(--space-3) var(--space-6);
  background: transparent;
  color: var(--ink-primary);
  border: 1px solid var(--border-default);
  border-radius: var(--radius-md);
  font-family: var(--font-sans);
  font-size: var(--size-sm);
  font-weight: 500;
  cursor: pointer;
  transition: background var(--duration-base) var(--ease-gentle),
              border-color var(--duration-base) var(--ease-gentle);
}

.btn-secondary:hover {
  background: var(--bg-subtle);
  border-color: var(--border-strong);
}
```

### Tertiary (text link)

```css
.btn-text {
  background: transparent;
  border: none;
  color: var(--accent-strong);
  font-family: var(--font-sans);
  font-size: var(--size-sm);
  padding: var(--space-2) 0;
  cursor: pointer;
  border-bottom: 1px solid transparent;
  transition: border-color var(--duration-base) var(--ease-gentle);
}

.btn-text:hover {
  border-bottom-color: var(--accent);
}
```

## Inputs

### Underline input (most editorial)

```css
.input-underline {
  display: block;
  width: 100%;
  padding: var(--space-3) 0;
  font-family: var(--font-sans);
  font-size: var(--size-base);
  color: var(--ink-primary);
  background: transparent;
  border: none;
  border-bottom: 1px solid var(--border-default);
  transition: border-color var(--duration-base) var(--ease-gentle);
}

.input-underline:focus {
  outline: none;
  border-bottom-color: var(--accent);
  border-bottom-width: 2px;
  padding-bottom: calc(var(--space-3) - 1px);
}

.input-underline::placeholder {
  color: var(--ink-tertiary);
}

.input-label {
  display: block;
  font-size: var(--size-xs);
  font-weight: 500;
  letter-spacing: var(--tracking-wide);
  text-transform: uppercase;
  color: var(--ink-secondary);
  margin-bottom: var(--space-2);
}
```

### Boxed input (more conventional)

```css
.input-boxed {
  width: 100%;
  padding: var(--space-3) var(--space-4);
  font-family: var(--font-sans);
  font-size: var(--size-base);
  color: var(--ink-primary);
  background: var(--bg-elevated);
  border: 1px solid var(--border-default);
  border-radius: var(--radius-md);
  transition: border-color var(--duration-base) var(--ease-gentle),
              box-shadow var(--duration-base) var(--ease-gentle);
}

.input-boxed:focus {
  outline: none;
  border-color: var(--accent);
  box-shadow: 0 0 0 3px var(--accent-soft);
}
```

## Cards

```css
.card {
  background: var(--bg-elevated);
  border-radius: var(--radius-md);
  padding: var(--space-6);
  box-shadow: var(--shadow-sm);
  transition: box-shadow var(--duration-base) var(--ease-gentle),
              transform var(--duration-base) var(--ease-gentle);
}

.card-interactive:hover {
  box-shadow: var(--shadow-md);
  transform: translateY(-2px);
}

.card-quiet {
  background: var(--bg-subtle);
  border-radius: var(--radius-md);
  padding: var(--space-6);
  box-shadow: none;
  border: 1px solid var(--border-subtle);
}
```

## Navigation

### Quiet top bar

```css
.nav-top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: var(--space-6) var(--space-8);
  background: var(--bg-base);
  border-bottom: 1px solid var(--border-subtle);
}

.nav-brand {
  font-family: var(--font-serif);
  font-size: var(--size-lg);
  color: var(--ink-primary);
  letter-spacing: -0.01em;
}

.nav-links {
  display: flex;
  gap: var(--space-8);
  list-style: none;
  padding: 0;
  margin: 0;
}

.nav-link {
  font-size: var(--size-sm);
  color: var(--ink-secondary);
  text-decoration: none;
  border: none;
  padding: var(--space-2) 0;
  position: relative;
  transition: color var(--duration-base) var(--ease-gentle);
}

.nav-link::after {
  content: '';
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  height: 1px;
  background: var(--accent);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform var(--duration-slow) var(--ease-gentle);
}

.nav-link:hover {
  color: var(--ink-primary);
}

.nav-link:hover::after,
.nav-link.active::after {
  transform: scaleX(1);
}
```

## Checkboxes

```html
<label class="check">
  <input type="checkbox" />
  <span class="check-box"></span>
  <span class="check-label">Read tonight</span>
</label>
```

```css
.check {
  display: inline-flex;
  align-items: center;
  gap: var(--space-3);
  cursor: pointer;
}

.check input {
  position: absolute;
  opacity: 0;
  width: 0;
  height: 0;
}

.check-box {
  width: 20px;
  height: 20px;
  border: 1.5px solid var(--border-strong);
  border-radius: var(--radius-sm);
  background: var(--bg-elevated);
  position: relative;
  transition: all var(--duration-base) var(--ease-gentle);
}

.check input:checked + .check-box {
  background: var(--accent);
  border-color: var(--accent);
}

.check-box::after {
  content: '';
  position: absolute;
  left: 5px;
  top: 2px;
  width: 6px;
  height: 10px;
  border: solid var(--bg-base);
  border-width: 0 1.5px 1.5px 0;
  transform: rotate(45deg) scale(0);
  transition: transform var(--duration-base) var(--ease-gentle);
}

.check input:checked + .check-box::after {
  transform: rotate(45deg) scale(1);
}

.check-label {
  font-size: var(--size-base);
  color: var(--ink-body);
  transition: color var(--duration-base) var(--ease-gentle);
}

.check input:checked ~ .check-label {
  color: var(--ink-tertiary);
  text-decoration: line-through;
  text-decoration-color: var(--ink-tertiary);
}
```

## Empty state

```html
<div class="empty-state">
  <div class="empty-state__icon">✦</div>
  <h3 class="empty-state__title">Nothing here yet</h3>
  <p class="empty-state__body">
    Your day is still open. Add something you'd like to move toward.
  </p>
  <button class="btn-text">Begin</button>
</div>
```

```css
.empty-state {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  padding: var(--space-16) var(--space-8);
  max-width: 420px;
  margin: 0 auto;
}

.empty-state__icon {
  font-size: 2rem;
  color: var(--ink-tertiary);
  margin-bottom: var(--space-6);
  animation: breathe var(--duration-ambient) var(--ease-gentle) infinite;
}

.empty-state__title {
  font-family: var(--font-serif);
  font-size: var(--size-xl);
  color: var(--ink-primary);
  margin-bottom: var(--space-3);
}

.empty-state__body {
  font-size: var(--size-base);
  color: var(--ink-secondary);
  line-height: var(--leading-relaxed);
  margin-bottom: var(--space-8);
}

@keyframes breathe {
  0%, 100% { opacity: 0.6; transform: scale(1); }
  50% { opacity: 1; transform: scale(1.05); }
}
```

## Hero section (landing page)

```html
<section class="hero">
  <p class="hero__eyebrow">A daily planner</p>
  <h1 class="hero__title">
    Work calmly.<br />
    <em>Return to yourself.</em>
  </h1>
  <p class="hero__lead">
    One plan, made slowly in the morning. Room for the unexpected.
    A gentle close at the end of the day.
  </p>
  <div class="hero__actions">
    <button class="btn-primary">Begin</button>
    <button class="btn-text">Read the philosophy</button>
  </div>
</section>
```

```css
.hero {
  max-width: 720px;
  padding: var(--space-32) var(--space-8) var(--space-24);
  margin: 0 auto;
  text-align: left; /* not centered — more editorial */
}

.hero__eyebrow {
  font-size: var(--size-xs);
  letter-spacing: var(--tracking-wide);
  text-transform: uppercase;
  color: var(--ink-secondary);
  margin-bottom: var(--space-4);
}

.hero__title {
  font-family: var(--font-serif);
  font-size: var(--size-4xl);
  font-weight: 400;
  line-height: 1.1;
  letter-spacing: -0.025em;
  color: var(--ink-primary);
  margin-bottom: var(--space-8);
}

.hero__title em {
  font-style: italic;
  color: var(--accent-strong);
}

.hero__lead {
  font-size: var(--size-lg);
  line-height: var(--leading-relaxed);
  color: var(--ink-body);
  margin-bottom: var(--space-10);
  max-width: 560px;
}

.hero__actions {
  display: flex;
  align-items: center;
  gap: var(--space-6);
}
```

## Toast / gentle notification

```css
.toast {
  position: fixed;
  bottom: var(--space-8);
  left: 50%;
  transform: translateX(-50%) translateY(20px);
  background: var(--bg-elevated);
  color: var(--ink-primary);
  padding: var(--space-3) var(--space-5);
  border-radius: var(--radius-full);
  box-shadow: var(--shadow-lg);
  font-size: var(--size-sm);
  opacity: 0;
  transition: all var(--duration-slow) var(--ease-gentle);
}

.toast.visible {
  opacity: 1;
  transform: translateX(-50%) translateY(0);
}
```
