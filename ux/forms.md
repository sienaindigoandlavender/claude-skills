# Forms: patterns and failure modes

Forms are the highest-leverage UX surface. Small changes here produce outsized conversion and completion differences.

## Field-by-field rules

### Asking for less

Every field has a cost. Before adding one, answer: what breaks if we don't collect this? "Nice to have for analytics" is not an answer. "We legally need a billing address to issue an invoice" is.

- Signup forms should be email + password + done. Everything else can be collected later in-context.
- Checkout forms should let guests check out. Forced account creation is the number one cart abandonment cause.
- "Confirm email" and "Confirm password" fields: skip both. Use a show/hide toggle on password instead, and send a confirmation email for email typos.

### Field types

Use the most specific input type the platform offers. On mobile this changes the keyboard; on desktop it enables browser validation and autofill.

- `type="email"` — shows @ key on mobile
- `type="tel"` — numeric keypad
- `type="url"` — shows / and .com key
- `type="number"` — for actual numbers; for codes/PINs use `type="text" inputmode="numeric" pattern="[0-9]*"` instead (avoids the spinner)
- `type="date"` — native date picker; but for birthdays, three separate fields or a text input with mask often works better (native pickers are awkward for dates decades in the past)
- `type="search"` — shows a "Search" key and a clear button

### Autocomplete

Set `autocomplete` attributes. Password managers and browser autofill depend on them. Common values:

- `autocomplete="email"`, `autocomplete="username"`
- `autocomplete="current-password"` (sign-in) vs `autocomplete="new-password"` (signup, change password)
- `autocomplete="one-time-code"` for 2FA codes (iOS will offer the code from SMS)
- `autocomplete="name"`, `autocomplete="given-name"`, `autocomplete="family-name"`
- `autocomplete="street-address"`, `autocomplete="postal-code"`, `autocomplete="country"`
- `autocomplete="cc-number"`, `autocomplete="cc-exp"`, `autocomplete="cc-csc"`

## Labels and placeholders

- **Always use `<label>`.** Linked to the input via `for`/`id` or by wrapping. Screen readers need this; click-to-focus needs this.
- **Labels go above inputs.** Floating labels are fashionable but hurt scanability and break for users who rely on zoom.
- **Placeholders are hints, not labels.** Use placeholder for format examples ("jane@example.com") not field names. Placeholder disappears on input and has poor contrast by default.
- **Required vs optional: mark the minority.** If most fields are required, mark the optional ones. If most are optional, mark the required ones. Don't mark both.

## Validation

- **Validate on blur, not on keystroke.** Exception: password strength meters and character counters (these show progress, not errors).
- **Validate on submit for everything, even if blur-validated earlier.** The field may have been valid when they left it but the combination may not work.
- **Error messages live next to the field** — not in a banner at the top, not in a toast. Inline, below or beside, with a consistent color and icon.
- **Error copy: locate, explain, fix.** "Password needs at least one number" beats "Invalid password." "We couldn't find an account with this email — want to sign up?" beats "Email not found."
- **Never clear inputs on error.** Preserve every keystroke. If the server rejects the submission, return to the form with all values intact.
- **Disable the submit button while a request is in flight** (and show a spinner), to prevent double-submit. Re-enable on response.

## Passwords

- **Length over complexity.** A 12-character passphrase beats "P@ssw0rd!" for security and usability both. Require a minimum length (NIST recommends 8+; 12+ is better) and stop requiring a number-symbol-capital-emoji.
- **Allow pasting.** Disabling paste breaks password managers and serves no security purpose.
- **Show-password toggle.** Eye icon that toggles visibility. Especially important on mobile where typing long passwords blind is misery.
- **Don't email passwords in plain text, ever.** If your reset flow does this, the password is stored recoverably — which means it can be stolen recoverably.

## Multi-step forms

Break a long form into steps only if the steps are meaningful chunks (shipping → payment → review), not arbitrary splits to make the form "feel shorter."

- **Show progress.** Step indicator at top. Not a progress bar — a labeled list of steps so users know what's coming.
- **Let users go back without losing data.** This should be obvious. It is somehow not.
- **Save partial progress.** For long forms (job applications, complex signups), save as you go so a lost connection doesn't mean starting over.
- **Final review step before irreversible submission.** Especially for anything involving money or legal commitment.

## Address, phone, and name fields

- **One field for full name** unless you have a specific reason to split. Don't force "First / Last" — it fails for single-name people, people with multiple given names, people whose family name comes first, and basically everyone who isn't American.
- **Don't validate names.** No "letters only" — hyphens, apostrophes, spaces, accented characters are all valid in real names. Unicode is fine.
- **Phone numbers: accept any format, normalize server-side.** Let the user type `(555) 123-4567` or `5551234567` or `+1 555 123 4567`.
- **Address: fewer fields than you think.** Many countries don't have "state." Many don't have ZIP codes in the US format. If you're global, use a single multi-line "address" field and a country dropdown rather than trying to model every address schema.
