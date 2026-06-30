# Interaction Design Principles

> When to use: applying or reviewing interaction-design fundamentals (Norman's principles, feedback, mental models, direct manipulation, microinteractions) while building or auditing any web/mobile UI.

## Apply-always rules

- Every user action gets visible feedback within 100ms; if work takes longer, show progress, not silence.
- Make the next available action obvious. If a thing is interactive, it should look interactive (signifiers), and what it does should match how it looks (affordances).
- Match the user's mental model, not the database schema. Label and group things the way users think, not the way the system stores them.
- Prevent errors before recovering from them: constrain inputs, disable invalid actions, confirm destructive ones, and always offer undo.
- Keep state and current mode visible at all times. The user should never have to guess "what will this keystroke/tap do right now?"
- Be consistent within your product and with platform conventions; surprise is a usability cost, not a feature.
- Reflect system status honestly: loading, saving, saved, error, offline, empty. No ambiguous in-between states.
- Prefer recognition over recall: surface options and defaults rather than making users remember syntax or prior values.
- Optimistically update the UI for likely-successful actions, but reconcile and roll back gracefully on failure.
- Treat persuasion as a responsibility: nudge toward the user's goals, never trick them (no dark patterns).

## Core concepts

### Visibility & Signifiers
**What:** Functions and the cues that point to them must be perceivable, so users discover what they can do without hunting or memorizing.
**Apply in UI:**
- Give interactive elements clear signifiers: button styling, underlined links, cursor changes, focus rings, hover/pressed states.
- Surface primary actions; tuck secondary actions into overflow menus rather than hiding everything equally.
- Prefer disabled-with-reason over hidden for actions that exist but aren't currently available; hide only what is truly irrelevant in this context.
**Violation smell:** Users have to hover randomly or read docs to find out what's clickable.

### Feedback & System Status
**What:** Each action produces an immediate, intelligible response telling the user what happened and what the system is doing now.
**Apply in UI:**
- Acknowledge taps/clicks instantly (pressed state) even when the result is async.
- Use skeletons or spinners for waits, progress bars for measurable work, and toasts/inline messages for completion or failure.
- Show explicit saved/saving/error states for autosave; never leave the user unsure whether their work persisted.
- Reflect connection and background states (offline, syncing, retrying).
**Violation smell:** The user clicks, nothing visibly changes, and they click again.

### Affordances, Constraints & Mapping
**What:** Affordances are what an element lets you do; constraints limit wrong actions; mapping aligns controls with their effects spatially and logically.
**Apply in UI:**
- Constrain input at the source: typed/masked fields, steppers, date pickers, dropdowns instead of free text where values are bounded.
- Map controls to outcomes naturally: a left/right toggle for previous/next, sliders that increase to the right, switches whose on-state reads as "on."
- Disable or block invalid combinations rather than letting users submit and fail.
**Violation smell:** A field accepts garbage, then a server error scolds the user after submit.

### Conceptual & Mental Models
**What:** The conceptual model is the designer's intended way the product works; it succeeds when it matches the user's mental model of the task.
**Apply in UI:**
- Use familiar metaphors and object models (folders, cards, drafts, trash) consistently across the app.
- Name and structure features around user goals and vocabulary, not internal architecture.
- When introducing a novel model, teach it once with onboarding, empty states, or inline hints.
**Violation smell:** Users repeatedly do the "wrong" thing because the interface implies a model the system doesn't honor.

### Gulf of Execution & Gulf of Evaluation
**What:** The execution gulf is the gap between intent and knowing how to act; the evaluation gulf is the gap between the system's state and the user understanding it.
**Apply in UI:**
- Close execution gulfs by making valid actions visible and the next step obvious (clear CTAs, sensible defaults, suggested actions).
- Close evaluation gulfs by surfacing results and state changes clearly (confirmation, updated counts, diffs, status badges).
- After any action, the user should be able to answer "Did it work? What now?" without investigation.
**Violation smell:** Users complete a task but ask "did that actually do anything?"

### The Four Interaction Types
**What:** Users engage products by instructing (commands), conversing (dialogue), manipulating (direct handling of objects), and exploring (navigating a space or data).
**Apply in UI:**
- Instructing: keep commands fast and reversible (buttons, menus, keyboard shortcuts, command palettes).
- Conversing: in chat/voice/search, set expectations, handle misunderstandings, and let users correct or rephrase.
- Manipulating: support drag, resize, reorder with real-time visual response and snap/constraint cues.
- Exploring: provide clear wayfinding, breadcrumbs, filters, and "you are here" orientation.
**Violation smell:** A drag-and-drop board with no drop targets, or a chatbot that dead-ends on any unexpected phrasing.

### Direct Manipulation, State & Modes
**What:** Direct manipulation lets users act on visible objects and see immediate effects; modes change what the same input does and must be unmistakable.
**Apply in UI:**
- Manipulate the real object where possible (inline edit, drag to reorder) instead of opening a separate dialog for everything.
- Make modes loud: distinct edit vs. view styling, visible selection, clear "you are editing X" banners.
- Prefer modeless or spring-loaded modes; if a mode persists, give an obvious exit (Esc, Done, Cancel).
- Manage focus deliberately: move focus into opened dialogs, return it on close, trap it within modals.
**Violation smell:** The same key deletes a card in one mode and a character in another, with no visible cue which.

### Error Prevention & Recovery
**What:** Good systems make errors hard to commit and easy to undo, treating mistakes as expected rather than punished.
**Apply in UI:**
- Validate inline as users type, with specific, human, fix-oriented messages near the field.
- Confirm only genuinely destructive/irreversible actions; otherwise prefer undo over a confirmation dialog.
- Provide undo/redo, soft-delete with restore, and safe defaults for risky operations.
- Preserve user input on error; never wipe a form because one field failed.
**Violation smell:** A modal asks "Are you sure?" for trivial actions but permanently deletes data with no undo.

### Latency, Loading & Perceived Performance
**What:** Perceived speed often matters more than actual speed; how you handle waits shapes whether the product feels responsive.
**Apply in UI:**
- Respond to input instantly even when results lag; use optimistic UI for high-confidence actions.
- Use skeleton screens to convey structure, and reserve spinners for short, indeterminate waits.
- For long jobs, run in the background and notify on completion instead of blocking the UI.
- Prioritize above-the-fold content and stream results progressively.
**Violation smell:** A blank white screen or frozen UI with no indication anything is happening.

### Microinteractions
**What:** Small, single-purpose moments (toggles, likes, pull-to-refresh, validation ticks) that communicate state and add polish.
**Apply in UI:**
- Give each microinteraction a clear trigger, rules, feedback, and end state.
- Use motion to explain (where something came from/went), not just to decorate; keep it short (~150-300ms).
- Respect reduced-motion preferences and never block interaction waiting for an animation.
**Violation smell:** Animations that delay the user or fire so often they become noise.

### Emotional & Affective Interaction (Ethics)
**What:** Designs shape feelings; pleasant, humane interactions build trust, but emotional techniques can be abused.
**Apply in UI:**
- Write errors and empty states with empathy and a path forward, never blame.
- Be cautious with anthropomorphism: a friendly assistant tone helps, but don't fake sentience or imply capabilities you lack.
- Use persuasive techniques (defaults, reminders, gamification) only to advance the user's own goals.
- Ban dark patterns: no forced continuity, confirmshaming, hidden costs, or roach-motel cancellation flows.
**Violation smell:** The "No thanks" button is styled to make users feel guilty, or unsubscribe is buried.

## Feedback timing cheatsheet

| Latency | User perception | Right feedback |
|---|---|---|
| < 100ms | Feels instant | No special indicator; just apply the change |
| 100ms - 1s | Slight but noticeable lag | Subtle cue: pressed state, inline spinner, optimistic update |
| 1 - 10s | Clearly waiting | Visible spinner or, if measurable, a progress bar; keep UI responsive |
| > 10s | Attention drifts | Run in background, show progress/ETA, allow other work, notify on completion |

## Quick review checklist

- [ ] Every interactive element looks interactive and has visible focus/hover/active states.
- [ ] Every action gives feedback within 100ms; waits show appropriate progress.
- [ ] Loading, empty, error, and success states are all designed (not just the happy path).
- [ ] Invalid actions are disabled-with-reason or prevented; inputs are constrained at the source.
- [ ] Destructive actions are confirmed or, better, undoable; user input survives errors.
- [ ] Current mode and selection are always visible; focus is managed on dialog open/close.
- [ ] Optimistic updates reconcile and roll back cleanly on failure.
- [ ] Labels, grouping, and metaphors match the user's mental model and vocabulary.
- [ ] Behavior is consistent within the app and with platform conventions.
- [ ] No dark patterns; persuasion serves the user's goals and respects reduced-motion settings.

## See also

- [Design principles](./design-principles.md)
- [Usability heuristics](./usability-heuristics.md)
- [Goal-directed design](./goal-directed-design.md)
