# Design tokens

Ready-to-paste CSS custom properties for the slow-dreamy aesthetic. Use these as a starting point — adjust the accent to match the project.

## Full token set

```css
:root {
  /* Backgrounds — warm neutrals */
  --bg-base: #FBF9F4;           /* candlelight cream, the default page background */
  --bg-subtle: #F7F2EA;         /* warmer parchment, for hero sections */
  --bg-muted: #EEE8DB;          /* soft linen, for recessed surfaces */
  --bg-elevated: #FFFFFF;       /* pure white for modals and input interiors */

  /* Ink — warm dark */
  --ink-primary: #2B2623;       /* near-black, headlines */
  --ink-body: #3E3630;          /* body text */
  --ink-secondary: #6B5F55;     /* captions, metadata */
  --ink-tertiary: #9C8E82;      /* hints, dividers-as-text */
  --ink-inverse: #EDE5D8;       /* text on dark surfaces */

  /* Accent — pick one per project, comment out the rest */
  --accent: #A8826F;            /* terracotta — default warm */
  /* --accent: #8B9D7F; */      /* sage — nature, success contexts */
  /* --accent: #C4A574; */      /* soft gold — premium, emphasis */
  /* --accent: #7B8A99; */      /* dusty blue — trust, calm */
  /* --accent: #B08A8A; */      /* muted rose — wellness, warmth */
  /* --accent: #6B7B6E; */      /* forest — depth, outdoor */

  --accent-soft: color-mix(in oklab, var(--accent) 15%, var(--bg-base));
  --accent-strong: color-mix(in oklab, var(--accent) 80%, var(--ink-primary));

  /* Semantic */
  --success: #8B9D7F;           /* sage */
  --warning: #C4A574;           /* soft gold */
  --danger: #B07A6F;            /* muted brick — never pure red */
  --info: #7B8A99;              /* dusty blue */

  /* Borders & dividers */
  --border-subtle: #E5DCCF;
  --border-default: #D4C8B8;
  --border-strong: #B8A997;

  /* Shadows — warm-toned */
  --shadow-xs: 0 1px 2px rgba(75, 58, 47, 0.04);
  --shadow-sm: 0 2px 8px rgba(75, 58, 47, 0.04),
               0 1px 3px rgba(75, 58, 47, 0.06);
  --shadow-md: 0 2px 8px rgba(75, 58, 47, 0.04),
               0 8px 24px rgba(75, 58, 47, 0.06);
  --shadow-lg: 0 4px 12px rgba(75, 58, 47, 0.06),
               0 16px 40px rgba(75, 58, 47, 0.08);
  --shadow-xl: 0 8px 24px rgba(75, 58, 47, 0.08),
               0 32px 64px rgba(75, 58, 47, 0.10);

  /* Radii */
  --radius-sm: 6px;
  --radius-md: 10px;            /* default for cards, inputs */
  --radius-lg: 16px;
  --radius-xl: 24px;            /* modals, sheets */
  --radius-full: 9999px;        /* tags, chips, pill buttons only */

  /* Typography */
  --font-serif: "Fraunces", "Tiempos", Georgia, serif;
  --font-sans: "General Sans", "Söhne", "Inter", -apple-system, system-ui, sans-serif;
  --font-mono: "JetBrains Mono", "IBM Plex Mono", ui-monospace, monospace;

  --size-xs: 0.75rem;           /* 12px — captions, labels */
  --size-sm: 0.875rem;          /* 14px — metadata */
  --size-base: 1.0625rem;       /* 17px — body (bigger than usual) */
  --size-lg: 1.25rem;           /* 20px — lead paragraphs */
  --size-xl: 1.5rem;            /* 24px — small headlines */
  --size-2xl: 2rem;             /* 32px */
  --size-3xl: 2.75rem;          /* 44px */
  --size-4xl: 4rem;             /* 64px — hero */

  --leading-tight: 1.25;        /* headlines */
  --leading-snug: 1.4;
  --leading-normal: 1.6;        /* default body */
  --leading-relaxed: 1.75;      /* long-form reading */

  --tracking-tight: -0.02em;    /* large headlines */
  --tracking-normal: 0;
  --tracking-wide: 0.05em;      /* labels, small caps */

  /* Spacing — 8px baseline */
  --space-1: 0.25rem;           /* 4px */
  --space-2: 0.5rem;            /* 8px */
  --space-3: 0.75rem;
  --space-4: 1rem;              /* 16px */
  --space-5: 1.25rem;
  --space-6: 1.5rem;
  --space-8: 2rem;              /* 32px */
  --space-10: 2.5rem;
  --space-12: 3rem;             /* 48px */
  --space-16: 4rem;             /* 64px — section separation */
  --space-20: 5rem;
  --space-24: 6rem;             /* 96px — major section breaks */
  --space-32: 8rem;              /* 128px — chapter breaks on marketing */

  /* Motion */
  --ease-gentle: cubic-bezier(0.22, 1, 0.36, 1);
  --ease-soft: cubic-bezier(0.4, 0, 0.2, 1);

  --duration-fast: 150ms;
  --duration-base: 300ms;
  --duration-slow: 500ms;
  --duration-ambient: 2000ms;

  /* Layout */
  --content-reading: 680px;     /* prose max-width */
  --content-ui: 1120px;         /* app layout max-width */
  --content-marketing: 1280px;
}

/* Dark mode */
@media (prefers-color-scheme: dark) {
  :root {
    --bg-base: #1F1B17;
    --bg-subtle: #25211C;
    --bg-muted: #2A2521;
    --bg-elevated: #322C27;

    --ink-primary: #EDE5D8;
    --ink-body: #D9CFBF;
    --ink-secondary: #9C8E82;
    --ink-tertiary: #6B5F55;
    --ink-inverse: #2B2623;

    --accent: #C49B85;           /* lightened terracotta */

    --border-subtle: #3A332D;
    --border-default: #4A4038;
    --border-strong: #5C4F45;

    --shadow-sm: 0 2px 8px rgba(0, 0, 0, 0.2),
                 0 1px 3px rgba(0, 0, 0, 0.15);
    --shadow-md: 0 2px 8px rgba(0, 0, 0, 0.2),
                 0 8px 24px rgba(0, 0, 0, 0.25);
  }
}

/* Reduced motion */
@media (prefers-reduced-motion: reduce) {
  :root {
    --duration-fast: 0ms;
    --duration-base: 0ms;
    --duration-slow: 0ms;
    --duration-ambient: 0ms;
  }
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

## Base styles

```css
html {
  font-family: var(--font-sans);
  font-size: 17px;
  line-height: var(--leading-normal);
  color: var(--ink-body);
  background: var(--bg-base);
  -webkit-font-smoothing: antialiased;
  text-rendering: optimizeLegibility;
}

body {
  margin: 0;
  min-height: 100vh;
}

h1, h2, h3, h4 {
  font-family: var(--font-serif);
  color: var(--ink-primary);
  font-weight: 500;
  line-height: var(--leading-tight);
  letter-spacing: var(--tracking-tight);
  margin: 0;
}

h1 { font-size: var(--size-4xl); }
h2 { font-size: var(--size-3xl); }
h3 { font-size: var(--size-2xl); }
h4 { font-size: var(--size-xl); }

p {
  margin: 0;
  max-width: var(--content-reading);
}

a {
  color: var(--accent);
  text-decoration: none;
  border-bottom: 1px solid color-mix(in oklab, var(--accent) 30%, transparent);
  transition: border-color var(--duration-base) var(--ease-gentle);
}

a:hover {
  border-bottom-color: var(--accent);
}

::selection {
  background: var(--accent-soft);
  color: var(--ink-primary);
}
```

## Tailwind config translation

If using Tailwind, extend the theme:

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        bg: {
          base: '#FBF9F4',
          subtle: '#F7F2EA',
          muted: '#EEE8DB',
          elevated: '#FFFFFF',
        },
        ink: {
          primary: '#2B2623',
          body: '#3E3630',
          secondary: '#6B5F55',
          tertiary: '#9C8E82',
        },
        accent: {
          DEFAULT: '#A8826F',
          soft: '#E8DDD4',
          strong: '#6B4E3D',
        },
      },
      fontFamily: {
        serif: ['Fraunces', 'Tiempos', 'Georgia', 'serif'],
        sans: ['General Sans', 'Söhne', 'Inter', 'system-ui', 'sans-serif'],
      },
      fontSize: {
        base: ['1.0625rem', { lineHeight: '1.6' }],
      },
      boxShadow: {
        sm: '0 2px 8px rgba(75, 58, 47, 0.04), 0 1px 3px rgba(75, 58, 47, 0.06)',
        md: '0 2px 8px rgba(75, 58, 47, 0.04), 0 8px 24px rgba(75, 58, 47, 0.06)',
        lg: '0 4px 12px rgba(75, 58, 47, 0.06), 0 16px 40px rgba(75, 58, 47, 0.08)',
      },
      transitionTimingFunction: {
        gentle: 'cubic-bezier(0.22, 1, 0.36, 1)',
      },
      transitionDuration: {
        400: '400ms',
        600: '600ms',
      },
    },
  },
}
```
