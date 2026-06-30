# Design Process and Sketching

> When to use: Reach for this before building any non-trivial UI. It governs *how you work* — exploring options, designing states, and choosing cheap representations — not which colors or components to pick.

This file adapts Bill Buxton's *Sketching User Experiences* for an AI coding assistant. The core move: resist the urge to jump straight to one implementation. Explore the right design before you make the design right.

## Apply-always rules

- Before writing UI code, propose 2-3 alternative approaches or layouts (in words or ASCII), then recommend one. Never present a single option as if it were the only choice.
- Diverge before you converge: widen the option space first, narrow it second. Don't collapse to one idea on turn one.
- Stay cheap as long as possible. A text description or ASCII wireframe costs seconds; a coded prototype costs minutes and creates attachment. Climb the fidelity ladder only when the cheaper rung has answered its question.
- Design every state, not just the happy path. Empty, loading, error, and edge states are part of the design, not afterthoughts.
- Think in flows and sequences, not screens. A UI is an experience over time — model the transitions, not just the snapshots.
- Treat early roughness as a feature. Low fidelity signals "still open for discussion" and invites the user to redirect you before code is written.
- Fail early and cheaply. Surface a risky assumption with a 30-second sketch rather than discovering it after a full build.
- Match detail to the question being asked. Don't polish micro-interactions while the overall layout is still unsettled.
- Keep alternatives comparable. Sketch options side by side so their trade-offs are visible — that contrast is what produces a better choice.
- Separate generating from judging. List options first without critiquing; evaluate against goals in a distinct step.

## Concepts

### Right design vs. design right

**What:** "Getting the right design" means finding *which* thing to build; "getting the design right" means refining *that* thing until it's polished.
**Apply as an AI assistant:**
- Spend explicit effort on the "which" before the "how" — ask what problem the UI serves and float a few directions.
- Flag when you're switching modes: "Here are three directions (right design); once you pick, I'll refine the chosen one (design right)."
- Don't let implementation polish substitute for choosing the correct concept. A perfectly coded wrong layout is the most expensive failure.
**Violation smell:** You started coding the first idea that came to mind without naming any alternative.

### Sketches suggest, prototypes refine

**What:** A sketch is a fast, cheap, disposable proposal meant to provoke a decision; a prototype is a slower, costlier artifact meant to test and resolve a chosen idea.
**Apply as an AI assistant:**
- Use text/ASCII/wireframe "sketches" while the concept is open — they're quick to revise and easy to throw away.
- Reserve real code (the "prototype") for after a direction is agreed, when the question shifts from "what?" to "does this actually work?"
- Make the intent legible: say whether a given artifact is exploratory (sketch) or for-keeps (prototype).
**Violation smell:** You built a fully styled, working component to answer a question a one-paragraph description could have settled.

### The design funnel (diverge then converge)

**What:** Good process opens wide (many ideas, high uncertainty) then narrows deliberately (ideas merged, eliminated, committed) — uncertainty is reduced on purpose, not avoided.
**Apply as an AI assistant:**
- At the start of a UI task, generate breadth: multiple layouts, navigation models, or interaction patterns.
- Narrow with stated reasons tied to user goals and constraints, not just the first plausible fit.
- Don't close the funnel too early; premature commitment kills better options you never explored.
**Violation smell:** Your "options" all describe the same idea with cosmetic differences.

### Drawing is thinking / multiple alternatives

**What:** Externalizing an idea cheaply reveals things you can't see by reasoning alone, and ideas gain meaning by comparison, not in isolation.
**Apply as an AI assistant:**
- Lay out alternatives so the user can react — concrete sketches surface problems abstract talk hides.
- Let a comparison spark a better third option; combine the strengths of competing sketches.
- Produce more than you'll keep. Quantity early is the path to quality later.
**Violation smell:** You committed to a single approach before externalizing any of it for review.

### Prototyping the experience over time

**What:** An experience lives in sequence, state, timing, and transition — a single static screen can't capture "what is it like to use this?"
**Apply as an AI assistant:**
- Walk a storyboard: what does the user see and do, step by step, from entry to outcome?
- Name the transitions and state changes between screens, not just the screens.
- For a feature that's expensive to build (AI response, live data, complex backend), describe the experience first — a "Wizard of Oz" stub or faked data — to validate the flow before wiring real logic.
**Violation smell:** You designed isolated screens with no defined path, timing, or state transitions between them.

### Fail early to succeed sooner

**What:** Mistakes caught early and cheaply are valuable learning; mistakes caught late and expensively are damage. Lower the cost of a try so you can take more tries.
**Apply as an AI assistant:**
- Surface the riskiest assumption first, with the cheapest possible representation.
- Welcome a rejected sketch as progress — it cost seconds and removed a wrong path.
- Prefer many small, reversible steps over one large committed build.
**Violation smell:** The first time anyone could react to the design was after the whole thing was coded.

## Fidelity ladder

Climb only as high as the current question requires. Each rung answers a different question.

| Stage | Representation | Cost | When to use |
|---|---|---|---|
| 1. Text description | Prose: "a three-pane layout with a filter rail, list, and detail view" | Seconds | Aligning on concept and scope; comparing many directions fast |
| 2. ASCII / box wireframe | Monospace boxes showing layout, hierarchy, regions | Seconds–minutes | Settling structure, layout, and information priority |
| 3. Low-fi mockup | Greyscale blocks, placeholder labels, no real styling | Minutes | Resolving flow, spacing, and content order before visual design |
| 4. Hi-fi mockup | Real type, color, components, realistic content | Minutes–more | Validating look, feel, and visual hierarchy once structure is fixed |
| 5. Coded prototype | Working component / page in the real stack | Most | Testing real behavior, interaction, performance, and integration |

Rule of thumb: don't climb a rung until the rung below has answered its question, and don't skip straight to rung 5 for a decision that rung 1 or 2 could have made.

## States to always design

Before declaring a UI done, account for every state. For each, decide what the user sees and what they can do next.

- [ ] **Empty** — no data yet (first use, nothing created). Show guidance, not a blank void.
- [ ] **Loading** — data in flight. Skeletons or spinners; preserve layout to avoid shift.
- [ ] **Partial** — some data loaded, more pending or paginating.
- [ ] **Error** — request or action failed. Plain-language cause plus a recovery action.
- [ ] **Success** — action completed. Confirmation and a clear next step.
- [ ] **Zero-results** — valid query, nothing matched. Distinguish from empty; offer to adjust filters.
- [ ] **Offline / connectivity loss** — degraded or queued behavior, clearly communicated.
- [ ] **Permission-denied / unauthorized** — what's blocked and how to gain access.
- [ ] **First-run / onboarding** — the brand-new user with no context yet.

## Quick process checklist

1. Restate the user goal the UI serves and the constraints before designing anything.
2. Diverge: propose 2-3 distinct approaches (text or ASCII), each with a one-line trade-off.
3. Recommend one and explain why it best fits the goal and constraints.
4. Sketch the chosen layout cheaply (ASCII/low-fi) and confirm before coding.
5. Map the user flow and transitions, not just individual screens.
6. Enumerate every state from the checklist above and design each.
7. Climb the fidelity ladder one rung at a time; only write code once structure and flow are agreed.
8. Iterate cheaply — change the sketch, not the codebase — until the direction is right, then build.

## See also

- [Goal-directed design](./goal-directed-design.md) — grounding designs in real user goals before generating options.
- [Interaction design](./interaction-design.md) — refining the behavior, feedback, and states of the chosen design.
