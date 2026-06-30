# Usability Heuristics — Review & Audit Toolkit

> When to use: reviewing or auditing an interface, screen, flow, or PR for usability, accessibility, and form quality.

This is a checkbox-driven evaluation toolkit. Walk the interface against each heuristic, record violations, rate their severity, and report them in a consistent format. The goal is not to redesign — it is to surface concrete, fixable problems and tie each one to a principle.

## How to run a heuristic review

1. **Scope it.** Decide what you are evaluating (a single screen, an end-to-end flow, or a diff) and who the primary user is. List the key tasks the user is trying to complete.
2. **Walk each task as the user.** Step through the real flow, not just static screenshots. Note where you hesitate, guess, backtrack, or feel uncertain — friction is a signal.
3. **Pass over each heuristic group.** Go through the Usability, Accessibility, and Forms checklists below. Check off what passes; capture every failure as a finding with its exact location.
4. **Rate each finding.** Apply the 0–4 severity scale so the team knows what to fix first. Separate "must fix" (3–4) from "polish" (0–1).
5. **De-duplicate and cluster.** Group findings that share a root cause; a single inconsistent component may generate many symptoms. Fixing the cause beats patching each symptom.
6. **Report.** Emit findings in the Output format below, ordered by severity. Suggest a concrete fix for each, not just a complaint.

## Usability heuristics

### Visibility of system status
The interface should always show what is happening, so the user is never left guessing.
- [ ] Every action gives immediate feedback (loading state, spinner, progress, confirmation).
- [ ] The current location, mode, or step is clearly indicated (active nav item, breadcrumb, step counter).
- [ ] Long or background operations show progress and estimated outcome, not a frozen screen.
- [ ] System state changes (saved, synced, offline) are surfaced without the user having to check.

### Match between system and the real world
Speak the user's language and follow conventions from the world they already know.
- [ ] Labels, terms, and icons use the user's vocabulary, not internal/engineering jargon or codes.
- [ ] Information appears in a natural, expected order; metaphors map to real-world counterparts.
- [ ] Dates, numbers, currency, and units follow the user's locale and conventions.

### User control and freedom
Users make mistakes and change their minds; give them clearly marked exits and a reliable undo.
- [ ] Destructive and significant actions are reversible (undo) or guarded with confirmation.
- [ ] Every dialog, mode, or wizard has an obvious Cancel / Close / Back that does no harm.
- [ ] The user is never trapped in a state with no way out; navigation away does not silently lose work.
- [ ] Multi-step undo/redo is available where users explore or edit freely.

### Consistency and standards
The same thing should look and behave the same way, both inside the product and against platform norms.
- [ ] Identical actions use identical wording, icons, color, and placement across screens.
- [ ] The product follows platform and web conventions (button styles, link behavior, shortcuts).
- [ ] Visually similar elements behave similarly; different behaviors look different.

### Error prevention
The best error message is the one that never needs to appear — design the error out.
- [ ] Invalid options are disabled, hidden, or constrained rather than allowed-then-rejected.
- [ ] Risky actions require deliberate confirmation or a typed acknowledgment.
- [ ] Inputs constrain format at entry (masks, pickers, sensible defaults) to prevent bad data.

### Recognition rather than recall
Make options and information visible so users don't have to remember things across screens.
- [ ] Available actions and choices are shown in context, not hidden behind memory.
- [ ] Previously entered data, recent items, and defaults are surfaced instead of re-requested.
- [ ] Help and field hints appear where they are needed, not in a separate manual.

### Flexibility and efficiency of use
Serve both novices and experts; let frequent users go faster without slowing newcomers.
- [ ] Accelerators exist for power users (keyboard shortcuts, bulk actions, type-ahead).
- [ ] Common tasks have the shortest path; frequent actions are reachable in few steps.
- [ ] Users can tailor or save frequent actions (favorites, presets, remembered preferences).

### Aesthetic and minimalist design
Every element competes for attention; show only what serves the current task.
- [ ] No irrelevant or rarely needed content crowds the primary task.
- [ ] Visual hierarchy guides the eye to the most important element first.
- [ ] Whitespace, grouping, and contrast carry structure instead of clutter and decoration.

### Help users recognize, diagnose, and recover from errors
When something fails, say what happened, why, and how to fix it — in plain language.
- [ ] Error messages are human, specific, and blame the situation, not the user.
- [ ] Each error states the cause and a concrete next step or recovery action.
- [ ] Errors appear next to the thing that caused them, with the offending field highlighted.

### Help and documentation
The product should be usable without docs, but help must be available and findable when needed.
- [ ] Contextual help (tooltips, inline hints, empty-state guidance) is available where tasks get hard.
- [ ] Documentation is searchable, task-oriented, and lists concrete steps.
- [ ] Help is reachable from the point of need, not only from a distant menu.

## Accessibility checklist

Grounded in WCAG essentials. Treat 3–4 severity for anything that blocks a user from completing a task with assistive technology.

**Keyboard**
- [ ] Every interactive element is reachable and operable with the keyboard alone.
- [ ] Tab order is logical and follows visual/reading order; no keyboard traps.
- [ ] Custom widgets (menus, modals, sliders) support expected keys (Esc, arrows, Enter/Space).
- [ ] A "skip to content" link is available to bypass repeated navigation.

**Visual**
- [ ] Focus is always visible with a clear, high-contrast focus indicator.
- [ ] Text meets contrast minimums (4.5:1 body, 3:1 large text); UI controls meet 3:1.
- [ ] Color is never the only way information is conveyed (use icons, text, patterns too).
- [ ] Layout reflows and remains usable when zoomed to 200% and at small viewport widths.

**Semantics**
- [ ] Native semantic HTML is used (button, a, nav, label, headings) before ARIA.
- [ ] Images have meaningful alt text; decorative images have empty alt.
- [ ] Every form control has a programmatically associated label.
- [ ] Headings are properly nested; landmarks (main, nav, header) structure the page.
- [ ] ARIA roles/states are correct and updated; live regions announce dynamic changes.

**Motion**
- [ ] Animations respect `prefers-reduced-motion` and can be disabled.
- [ ] Nothing auto-plays, flashes more than three times per second, or moves without a pause control.

**Targets**
- [ ] Tap/click targets are large enough (aim for ~44×44px) with adequate spacing.
- [ ] Interactions do not rely on hover or precise pointing alone.

## Forms & inputs checklist

- [ ] Every field has a persistent, visible label (placeholder text is not a substitute for a label).
- [ ] Required vs. optional is explicit; mark the rarer case clearly and consistently.
- [ ] Input types and modes match the data (email, tel, number, date) to trigger the right keyboard.
- [ ] Autocomplete/autofill attributes are set for common fields (name, email, address, OTP).
- [ ] Validation is inline and timely — validate on blur or submit, not on every keystroke prematurely.
- [ ] Error messages are specific and adjacent to the field, naming what to fix and how.
- [ ] Valid input is acknowledged; the form remembers entries after an error (no wiping the form).
- [ ] Format expectations are shown upfront (hints, examples, masks), not only after failure.
- [ ] Field grouping and order follow a logical, real-world sequence; related fields are grouped.
- [ ] The primary submit action is clear, and disabled/loading states prevent double submission.
- [ ] Error summaries at the top link to the offending fields for long forms.

## Severity rating

Rate every finding so the team can prioritize. Severity blends frequency, impact, and persistence.

| Score | Label | Meaning |
|-------|-------|---------|
| 0 | Non-issue | Not a usability problem; note only if relevant. |
| 1 | Cosmetic | Minor polish; fix only if time permits. |
| 2 | Minor | Causes some friction or hesitation; low priority. |
| 3 | Major | Frequently blocks or frustrates users; fix soon. |
| 4 | Catastrophe | Prevents task completion or causes data loss; fix before release. |

## Output format

Report each finding as a structured entry, ordered by severity (highest first). Lead with a one-line summary, then the details:

```
[Severity 0–4] Short issue title
- Location: screen / component / file:line or selector
- Heuristic: which heuristic or accessibility/forms rule is violated
- Problem: what the user experiences and why it matters
- Suggested fix: a concrete, actionable change
```

Close the report with a short summary: total findings, counts by severity, and the top 3 things to fix first. Cluster duplicate symptoms under a shared root cause where it applies.

## See also

- [Design principles](./design-principles.md)
- [Interaction design](./interaction-design.md)
- [Typography](./typography.md)
