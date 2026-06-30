---
name: ux-principles
description: >-
  Apply established UX, interaction-design, and visual-design principles when
  designing, building, or reviewing any user-facing interface or flow. Use when
  creating or editing UI components, screens, forms, navigation, layouts, or
  design systems; when reviewing or auditing usability, accessibility, visual
  hierarchy, or typography; and when making product or interaction-design
  decisions. Grounded in the work of Norman, Cooper, Lidwell, Lupton, Buxton,
  Preece & Rogers, and Moggridge.
---

# UX Principles

A practical toolkit for applying decades of UX, interaction-design, and visual-design
wisdom while building software. Use it to make better design decisions as you write
UI code, and to review interfaces against proven heuristics.

## When to use this skill

Activate this skill whenever the work touches a human-facing interface, including:

- Creating or modifying UI components, screens, forms, modals, navigation, or layouts.
- Setting up or extending a design system, theme, or component library.
- Writing or adjusting CSS, spacing, typography, color, or visual hierarchy.
- Reviewing a PR, screen, or flow for usability, accessibility, or polish.
- Making product/interaction decisions (information architecture, flows, states, copy).

If the task is purely backend/infrastructure with no user-facing surface, this skill
usually does not apply.

## How to use it

1. **Decide the mode** — are you *creating* an interface or *reviewing* one?
2. **Load the relevant reference(s)** below — read only what the task needs (progressive
   disclosure). Don't dump all of them; pick by topic.
3. **Apply the principles concretely** in the code/design you produce.
4. **Self-check** against the relevant checklist before finishing.

When *creating*, lean on `process-and-sketching.md` first (explore alternatives, design
every state), then `goal-directed-design.md`, `interaction-design.md`, `design-principles.md`,
and `typography.md`. When *reviewing*, start from `usability-heuristics.md` and pull in the
others to justify findings.

## Reference files

| File | Use it for |
|------|-----------|
| [references/design-principles.md](references/design-principles.md) | Layout, grouping, visual hierarchy — Gestalt, Fitts's & Hick's law, 80/20, progressive disclosure, signal-to-noise. |
| [references/interaction-design.md](references/interaction-design.md) | Behavior over time — affordances, feedback, system status, mental models, error handling, perceived performance, ethics. |
| [references/goal-directed-design.md](references/goal-directed-design.md) | Users & product strategy — goals vs tasks, personas, scenarios, postures, removing busywork (excise). |
| [references/typography.md](references/typography.md) | Readable, hierarchical type on screens — measure, leading, scale, pairing, responsive & accessible type (with CSS values). |
| [references/process-and-sketching.md](references/process-and-sketching.md) | How to work — explore alternatives before committing, fidelity ladder, design every UI state. |
| [references/usability-heuristics.md](references/usability-heuristics.md) | Reviewing/auditing — Nielsen-style heuristics, accessibility & forms checklists, severity ratings, report format. |

## Core defaults (apply even without opening a reference)

These are the highest-leverage rules. They rarely conflict with anything; default to them.

1. **Design for goals, not features.** Ask what the user is trying to accomplish, then make
   the shortest sound path to it. Remove steps that exist only to serve the system (excise).
2. **Always show system status.** Every action gets visible feedback within ~100ms; anything
   slow gets a spinner/progress; nothing silently succeeds or fails.
3. **Design every state, not just the happy path.** Empty, loading, partial, error, success,
   zero-results, offline, first-run. Missing states are the #1 source of bad UX in real apps.
4. **Make actions reversible.** Prefer undo over confirmation dialogs; never destroy data
   without a way back. Confirm only the truly irreversible.
5. **Recognition over recall.** Show options and context instead of forcing users to remember;
   label everything; don't hide critical actions behind memory.
6. **Respect hierarchy and grouping.** Use proximity, alignment, size, weight, and whitespace
   so the eye lands on the most important thing first. One clear primary action per screen.
7. **Prevent errors, then forgive them.** Constrain inputs, validate inline, write error
   messages that say what happened and how to fix it — never blame the user.
8. **Be consistent.** Match platform conventions and your own patterns; same thing looks and
   behaves the same everywhere.
9. **Readable type by default.** Body ≥16px, line-height ~1.5, measure 45–75 characters,
   contrast ≥4.5:1. (See typography reference for the full scale.)
10. **Accessibility is not optional.** Keyboard-operable, visible focus, semantic HTML,
    labels on inputs, sufficient contrast, don't rely on color alone, respect reduced motion.
11. **Explore before you commit.** For non-trivial UI, propose 2–3 alternative approaches
    (in words or quick wireframes) before implementing one.

## Quick workflows

**Creating a new screen/component**
1. State the user goal and primary action in one sentence.
2. Sketch 2–3 layout options (words or ASCII wireframe); pick one and say why.
3. Enumerate every state (empty/loading/error/success/edge) and design each.
4. Build it applying hierarchy, feedback, type, and accessibility defaults.
5. Self-review against `usability-heuristics.md`.

**Reviewing an interface / PR**
1. Identify the primary user goal of the screen.
2. Walk the heuristics in `usability-heuristics.md`; note violations with location + severity.
3. Check accessibility and forms checklists.
4. Report findings as: *issue → where → principle violated → severity → suggested fix.*

## Guardrails

- Principles are defaults, not dogma. State the tradeoff when you deviate, and deviate
  toward the user's benefit — not the implementation's convenience.
- Never design dark patterns (forced continuity, confirm-shaming, hidden costs, sneak-into-
  basket, hard-to-cancel). If asked, flag the ethical issue and offer an honest alternative.
- Match the existing project's conventions and design system first; introduce new patterns
  only with a reason.
