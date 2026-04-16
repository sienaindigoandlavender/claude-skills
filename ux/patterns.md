# Interaction patterns: when to use what

A catalog of common UI patterns with the cases they're good for and the cases where they're misused.

## Surfaces and containers

### Modal (dialog)

**Use for:** a focused task the user has to complete or dismiss before continuing. Confirmation of a destructive action. A self-contained sub-task (quick-add, edit in place) that would be disruptive as a route change.

**Don't use for:** marketing offers, newsletter signups, announcements, anything the user didn't ask for. Don't nest modals. Don't use a modal to display long content that needs scrolling — that's a page.

**Must:** trap focus inside, close on Esc, close on backdrop click (unless destructive), restore focus to the trigger on close, have a clear "close" affordance.

### Drawer / side panel

**Use for:** secondary content or controls that relate to the current view — filters on a list, details of a selected item, a navigation menu on mobile. Keeps the user in context better than a modal.

**Don't use for:** primary content. If it's the main thing the user is doing, it should be a page or a main-area panel, not a drawer they have to open.

### Popover / dropdown

**Use for:** short menus, small forms (a date picker, a quick filter), non-essential detail. Anchored to a trigger.

**Must:** close on outside click, close on Esc, manage focus, not contain so much content that scrolling is needed.

### Tooltip

**Use for:** secondary info on hover/focus. Keyboard shortcuts. What an icon means.

**Must not:** contain essential info (touch users can't hover). Contain interactive elements (buttons, links). Appear instantly — add a short delay so the user doesn't get a cloud of tooltips while moving the cursor.

### Tabs

**Use for:** parallel views of the same object — "Details / Reviews / Related" on a product page. All tabs are peers; the user picks which facet to see.

**Don't use for:** sequential steps (that's a wizard/stepper). Navigation between unrelated pages (that's nav).

### Accordion

**Use for:** FAQ-style content, settings grouped by category, any list where users want to drill into one item at a time.

**Don't use for:** primary content you want everyone to read. If it's important, don't hide it.

## Feedback surfaces

### Toast / snackbar

**Use for:** confirmation of a completed action. "Saved." "Email sent." "Deleted — Undo."

**Don't use for:** errors that need user action (those go inline). Long messages. Multiple messages at once (stack carefully).

**Must:** dismiss on their own after a few seconds, be readable by screen readers (`aria-live`), not cover essential UI.

### Inline message

**Use for:** errors attached to a field, warnings about a specific section, status of a specific item.

Always better than a toast for anything the user needs to act on, because it's located where the action happens.

### Banner

**Use for:** persistent state that affects the whole app — "You're offline," "Your trial ends in 3 days," "Scheduled maintenance tonight."

**Must:** be dismissible (unless blocking), not cover primary content, reappear if the condition persists.

### Empty state

**Use for:** lists, tables, search results, dashboards with no data yet.

A good empty state has: an illustration or icon (optional), a clear heading ("No invoices yet"), an explanation ("Invoices you receive will appear here"), and a next action ("Create your first invoice" or "Import existing invoices"). The default "no data" is a failure of imagination.

### Loading states

- **Skeleton loaders** for content with predictable shape. Feels faster than spinners because the layout appears immediately.
- **Spinner** for action-in-progress or short waits (<3 seconds expected).
- **Progress bar** for long operations where progress is known.
- **Indeterminate progress bar** for long operations where progress is unknown.
- **Optimistic UI** — showing the action as complete before the server confirms — for fast perceived performance. Must gracefully handle failure (revert + error message).

## Navigation

### Top nav

Works for 3–7 main destinations. More than that, it's cluttered; fewer, it's wasted space.

### Side nav

Works for deeper hierarchies and apps with many top-level sections. Collapsible on mobile.

### Bottom tabs (mobile)

For 3–5 primary destinations. Must stay visible; don't hide on scroll unless the content needs it.

### Breadcrumbs

For deeply nested content where the user's path matters. Skip for shallow hierarchies — they add clutter without value.

### Search

If your app has enough content that users can't find things by navigation in under 10 seconds, add search. Good search beats good nav for large content sets. Make sure search works — autocomplete, typo tolerance, result ranking.

## Input patterns

### Select / dropdown

**Use for:** picking one option from a short-to-medium list (3–15 options).

**Don't use for:** fewer than 3 options (use radios), more than 15 (use a searchable combobox), boolean choices (use a toggle).

### Radio buttons

**Use for:** picking one option from 2–5 alternatives, all visible.

**Must:** have one option selected by default (the safest default for the user).

### Checkboxes

**Use for:** independent binary choices, or selecting multiple items from a list.

Checkbox vs toggle: checkbox applies on submit ("these are my preferences for this form"). Toggle applies immediately ("dark mode on/off"). Don't mix metaphors.

### Toggle switch

**Use for:** immediate on/off for a setting. Light switch, not a form field.

**Must:** have a clear on/off state visually. "Does the blue mean on or is the gray side selected?" is a real problem.

### Stepper / numeric input

**Use for:** small integers with clear up/down semantics (quantity, people, number of rooms).

**Must:** allow typing directly, not just clicking +/-. Enforce bounds (can't go below 1 for quantity).

### Slider

**Use for:** values where approximation is fine and the range is visual (volume, brightness, price range with a min and max).

**Don't use for:** precise values (use a number input). Values where the user knows exactly what they want to enter.

### Date picker

**Use for:** picking a calendar date.

**Must:** allow typing the date as well as picking. Handle birth dates without forcing a tap through decades.

For date ranges, show both start and end visually and let the user set them by clicking two dates on a calendar.

## Data display

### Table

**Use for:** comparing records across the same attributes. Numeric data. Dense information.

**Must on mobile:** either become a card list, horizontally scroll with sticky first column, or hide columns with a "show more" option. Squeezed-down tables are unreadable.

### Card grid

**Use for:** browsing items where visual comparison matters (products, articles, places).

**Don't use for:** dense data (use a table). So much content that the grid becomes infinite-scroll with no structure.

### List

**Use for:** sequential content, notifications, messages — things with a natural order.

### Dashboard

A dashboard is not "all the data on one screen." It's "the answers to the questions this user has." Start with the questions. One or two primary metrics, a few secondary, context below. If the user has to scroll through six charts to find the number they came for, the dashboard failed.

## Confirmations

### Inline undo

**Use for:** most destructive actions. Delete immediately, show a toast with "Undo" for 5–10 seconds. Much better UX than "Are you sure?"

### Confirmation modal

**Use for:** actions that can't be undone by inline undo — irreversible, high-stakes, or affecting others (publishing, sending, transferring money).

**Must:** state what will happen in plain language, not "Are you sure?" Use specific action verbs on the confirm button ("Delete account," not "Yes").

### Type-to-confirm

**Use for:** truly dangerous actions — deleting a project with months of work, deleting an account. Force the user to type the name of the thing. This friction is proportional to the stakes.

## Onboarding

- **Don't explain the whole app up front.** Progressive onboarding beats tutorials. Show one tip in context when the user reaches the relevant feature.
- **Let users skip.** The skip button should be as visible as "continue." Experienced users skip; new users proceed. Both are served.
- **Empty states are your best onboarding surface.** The user is already looking at the feature and wondering what to do. Tell them there.
