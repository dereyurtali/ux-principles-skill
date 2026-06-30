# Universal Design Principles for UI

> When to use: Reach for this when laying out, structuring, or reviewing any screen — deciding what goes where, how to group it, what to show, and what to cut.

## Apply-always rules

- Group related controls with whitespace and alignment before reaching for borders, boxes, or dividers — proximity does the work for free.
- Make interactive targets at least 44x44px and place frequent actions large, close to where the eye already is, or against a screen edge/corner.
- Limit any single choice point to a handful of options; split long menus into categories and offer a sensible default.
- Show only what the user needs now; push advanced or rare options behind "More", an accordion, or a settings panel.
- Establish one clear visual hierarchy per screen using size, weight, color, and spacing — there should be an obvious first thing to look at.
- Raise signal-to-noise: delete decoration, redundant labels, and chrome that doesn't help the user act.
- Keep patterns consistent — same component, same label, same placement, same behavior across the whole product.
- Let the user recognize options (visible menus, lists, icons) instead of recalling them from memory.
- Carry critical meaning on more than one channel (color + icon + text), never color alone.
- Polish the visuals; perceived beauty raises perceived usability and buys tolerance for minor flaws.

## Principles

### Proximity (Gestalt)
**What:** Elements placed close together are read as one group.
**Apply in UI:**
- Tighten spacing within a group, widen it between groups (e.g. 8px inside a field cluster, 24–32px between sections).
- Put labels adjacent to their inputs so the pairing is unambiguous.
- Drop dividers once spacing already communicates the grouping.
**Violation smell:** Uniform spacing everywhere, so nothing reads as belonging together.

### Similarity (Gestalt)
**What:** Elements sharing color, shape, size, or style are perceived as the same kind of thing.
**Apply in UI:**
- Give all links/clickable text one consistent treatment (color + weight).
- Style every primary button identically; style secondary actions as a distinct, consistent class.
- Don't reuse the "interactive" look on static text.
**Violation smell:** Two buttons that do the same job look different, or static text mimics a link.

### Closure (Gestalt)
**What:** The mind completes incomplete shapes, so full outlines aren't always needed.
**Apply in UI:**
- Imply a card or group with background tint or partial framing instead of a full heavy border.
- Trust alignment and whitespace to define regions; let the eye close the boundary.
**Violation smell:** Every container is boxed in, producing a cluttered grid of lines.

### Common Fate (Gestalt)
**What:** Elements that move the same way at the same time are seen as related.
**Apply in UI:**
- Animate items that belong together so they enter, scroll, or expand in unison.
- Reserve independent motion for genuinely independent objects.
**Violation smell:** Unrelated elements animate together and imply a relationship that doesn't exist.

### Continuation (Gestalt)
**What:** The eye follows the smoothest line or curve, so aligned elements feel connected.
**Apply in UI:**
- Lay content on a consistent grid; align edges and baselines.
- Keep form fields and list items on a shared left edge to create a clean scan line.
**Violation smell:** Ragged, unaligned edges that break the reading flow.

### Figure-Ground (Gestalt)
**What:** The mind splits a view into a foreground object and a background.
**Apply in UI:**
- Make the active layer obviously "on top" — overlay a dim scrim behind modals and popovers.
- Use contrast, shadow, or elevation so the primary surface separates from the background.
**Violation smell:** A dialog floats with no backdrop and blends into the page behind it.

### Fitts's Law
**What:** Time to hit a target shrinks as the target gets bigger and closer.
**Apply in UI:**
- Size frequent/primary actions generously; keep tap targets ≥44px with adequate spacing.
- Place key actions near the pointer's likely path or current focus.
- Exploit edges and corners — they act as infinitely large targets for toolbars, menus, and docks.
**Violation smell:** A tiny, isolated primary button stranded far from the related content.

### Hick's Law
**What:** Decision time grows as the number and complexity of choices grow.
**Apply in UI:**
- Cap visible options at a point of choice; collapse the rest under categories or "More".
- Preselect a smart default to remove a decision entirely.
- Break multi-step tasks into a sequence rather than one dense screen.
**Violation smell:** A flat menu of 20+ equally weighted items with no grouping.

### 80/20 Rule (Pareto)
**What:** Most use comes from a small fraction of features.
**Apply in UI:**
- Identify the ~20% of actions that drive ~80% of usage and make them prominent and frictionless.
- Demote rarely used features; don't give them equal real estate.
**Violation smell:** The everyday action and an obscure one share identical prominence.

### Progressive Disclosure
**What:** Reveal only what's needed now; defer advanced or rare options until requested.
**Apply in UI:**
- Hide power options behind accordions, "Advanced settings", or a secondary panel.
- Default to the simplest path; let users opt into depth.
**Violation smell:** A first-run screen exposes every setting at once and overwhelms newcomers.

### Signal-to-Noise Ratio
**What:** The ratio of relevant information to irrelevant clutter determines clarity.
**Apply in UI:**
- Remove decorative borders, drop shadows, and filler text that don't aid the task.
- Reduce competing accent colors; reserve emphasis for what matters.
**Violation smell:** Heavy ornamentation or dense copy burying the one thing the user came to do.

### Chunking
**What:** Information is easier to process when split into small, meaningful groups (~4 units).
**Apply in UI:**
- Format long strings in groups (phone, card, code: 1234 5678 9012).
- Break long forms into labeled sections or steps.
**Violation smell:** A wall of fields or an unbroken 16-digit input with no grouping.

### Performance Load
**What:** Performance drops as the mental and physical effort to reach a goal rises.
**Apply in UI:**
- Cut steps, clicks, and typing — use autocomplete, smart defaults, and saved data.
- Provide shortcuts for experts without forcing them on novices.
**Violation smell:** Re-asking for data the system already knows, or a 6-click path to a common task.

### Consistency
**What:** Similar things should look and behave similarly across the product.
**Apply in UI:**
- Reuse the same component, label, icon, and placement for the same function everywhere.
- Match platform conventions so learned behavior transfers in.
**Violation smell:** "Save" lives top-right on one screen and bottom-left on another.

### Mapping
**What:** Controls should relate to their effects in an intuitive, spatial way.
**Apply in UI:**
- Order controls to mirror the layout or order of what they affect.
- Make direction natural: up/right increases, a toggle's position reflects on/off.
**Violation smell:** A slider that moves left to increase, or arrows wired to the opposite direction.

### Constraints
**What:** Limiting possible actions prevents errors before they happen.
**Apply in UI:**
- Disable or hide actions that aren't currently valid; grey out unavailable buttons.
- Use input masks, steppers, and pickers to make invalid entries impossible.
**Violation smell:** A submit button stays active and only errors after the user commits.

### Aesthetic-Usability Effect
**What:** People perceive attractive designs as more usable and forgive their minor flaws.
**Apply in UI:**
- Invest in spacing, alignment, type, and color quality — it pays back as trust.
- Treat visual polish as functional, not decorative.
**Violation smell:** Sloppy alignment and clashing styles eroding confidence before anyone tests function.

### Visual Hierarchy
**What:** Importance and relationships expressed visually guide the eye from most to least important.
**Apply in UI:**
- Differentiate levels with size, weight, color, contrast, and spacing (clear H1 > H2 > body).
- Give each screen one dominant focal point and a clear primary action.
**Violation smell:** Everything is bold/large, so nothing stands out and the eye has no entry point.

### Von Restorff Effect (Isolation)
**What:** An item that visually differs from its peers draws attention and is better remembered.
**Apply in UI:**
- Make the primary CTA the only button with the strong fill; keep others quiet.
- Highlight the recommended plan with distinct color, size, or a badge.
**Violation smell:** Three equally loud buttons, so the intended action doesn't lead.

### Serial Position Effect
**What:** Items at the start and end of a list are remembered better than the middle.
**Apply in UI:**
- Place the most important nav items or actions first or last.
- Don't bury a critical option in the middle of a long list.
**Violation smell:** The key menu item sits dead-center in a long list and gets overlooked.

### Recognition Over Recall
**What:** Recognizing options from a set is far easier than recalling them from memory.
**Apply in UI:**
- Surface choices in menus, lists, and visible icons rather than requiring memorized commands.
- Show recently used items, suggestions, and inline labels; keep info in the world, not the head.
**Violation smell:** Users must remember an exact term or syntax with no visible hint.

### Redundancy
**What:** Carrying critical info on multiple channels ensures it lands even if one channel fails.
**Apply in UI:**
- Signal errors/status with color plus an icon plus text.
- Pair iconography with a label for ambiguous actions.
**Violation smell:** Status communicated by color alone, invisible to colorblind users.

## Quick review checklist

- [ ] Related elements grouped by spacing/alignment, not just borders?
- [ ] One clear visual hierarchy with an obvious focal point per screen?
- [ ] Exactly one prominent primary action; secondary actions visually quieter?
- [ ] Choices at each step limited and grouped, with a sensible default?
- [ ] Tap/click targets ≥44px, frequent actions large and easy to reach?
- [ ] Advanced/rare options deferred via progressive disclosure?
- [ ] Long strings and forms chunked into digestible groups?
- [ ] Components, labels, and placements consistent across screens?
- [ ] Critical info carried on color + icon + text (never color alone)?
- [ ] Decoration and redundant chrome trimmed to raise signal-to-noise?

## See also

- [./interaction-design.md](./interaction-design.md)
- [./typography.md](./typography.md)
- [./usability-heuristics.md](./usability-heuristics.md)
