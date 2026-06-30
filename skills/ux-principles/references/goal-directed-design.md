# Goal-Directed Design (Cooper)

> When to use: any time you're deciding what a product or feature should do and how it should behave — before reaching for components or layout, anchor on who the user is and what they're trying to achieve.

## Apply-always rules

- Design for **goals, not features or tasks**. Tasks are the steps; goals are the reason. Shorten the path to the goal instead of polishing the steps.
- Tie every proposed feature to a real user goal. If you can't name the persona and goal it serves, challenge it.
- Optimize for **perpetual intermediates** — most people are neither first-time beginners nor power users for long. Don't punish them with beginner hand-holding or expert-only density.
- **Eliminate excise**: any work the software imposes that doesn't move the user toward their goal is a tax. Remove it or automate it.
- Never make the user feel stupid. Cognitive friction — feeling incompetent — is the deepest cost of bad design.
- Prevent errors instead of reporting them. The best error message is the one that never needs to appear.
- Pick a **single primary persona** and stay loyal. Designing "for everyone" designs for no one.
- Choose the product's **posture** deliberately; it dictates UI density, visual tone, and which skill level to optimize for.
- Behave like **polite software**: remember preferences, anticipate needs, stay out of the way, and never blame the user.
- Protect **flow** — keep the user immersed with direct manipulation, modeless feedback, and forgiving undo.

## Concepts

### User goals vs. tasks

**What:** Goals are durable human motivations; tasks are the transient steps technology forces to reach them.
**Apply in practice:**
- Distinguish three goal types: **experience goals** (how the user wants to feel — in control, unhurried, not dumb), **end goals** (the concrete outcome — "inbox cleared", "flight booked"), and **life goals** (long-term aspirations — "be the best in my field").
- Drive interaction design mainly from end goals; let experience goals shape tone and feel; let life goals inform brand and loyalty.
- Separate user goals from business and technical goals — serving only the latter produces user-hostile products.
**Violation smell:** A feature exists because it was technically possible or matched a competitor's list, not because a persona needed it.

### Personas

**What:** A persona is a concrete, research-grounded archetype of a user, defined by goals and behavior rather than demographics.
**Apply in practice:**
- Ground personas in observed behavior; never invent an "elastic user" who conveniently wants whatever justifies the current idea.
- Use persona types intentionally: **primary** (the one the interface is designed for — each needs its own interface), **secondary** (mostly satisfied but with one extra need met without breaking the primary design), **supplemental** (already covered, no new decisions), **customer** (buys but doesn't use — e.g. IT admin, parent), **served** (affected by the product without using it — e.g. patient receiving the X-ray), and **negative** (explicitly not designed for, to sharpen scope).
- Keep it lightweight: a named character with goals, context, and frustrations is enough to ask "would Linda do this?" in a decision.
**Violation smell:** The persona is a demographic profile (age, income) with no goals, or it shifts to fit whatever the team already wants to build.

### Context scenarios

**What:** A plain-language story of a persona's ideal interaction with the product, written before any interface exists.
**Apply in practice:**
- Write the day-in-the-life narrative in an "ideal world" with no UI specifics — describe what happens, not which button.
- Mine the story for genuine requirements; needs should emerge from the narrative, not from a wishlist.
- Follow up with **key path scenarios** (the most common journeys) and **validation scenarios** (edge cases) to stress-test the design.
**Violation smell:** Requirements were written as a feature checklist before anyone described how a real person would actually move through the product.

### The six-stage process

**What:** Research, Modeling, Requirements, Framework, Refinement, Support — an iterative pipeline from observation to shipped design.
**Apply in practice:**
- **Research**: contextual interviews, stakeholder input, competitive scan. **Modeling**: distill behavior patterns into personas. **Requirements**: derive needs from persona goals and context scenarios.
- **Framework**: establish the overall interaction skeleton, grouping, and navigation with low-fidelity sketches before any detail. **Refinement**: detailed screens, micro-interactions, visuals, copy. **Support**: preserve design integrity as engineering realities surface.
- Treat it as iterative, not waterfall; each stage validates and feeds back into the prior one. Compress it for lean teams, but never skip to "lightweight research" instead of "no research."
**Violation smell:** Visual design and component choices begin before personas, requirements, or a structural framework exist.

### Product posture

**What:** A product's behavioral stance toward the user's attention — how foreground it should be.
**Apply in practice:**
- Identify whether the product is **sovereign** (full-screen, long sessions, optimize for experienced users, calm neutral visuals), **transient** (brief focused use, large self-explanatory controls), **daemonic** (background, visible only when attention is needed), or **auxiliary** (always visible but rarely the focus).
- Let posture set UI density: sovereign tolerates rich, dense, keyboard-accelerated interfaces; transient demands big obvious controls and zero memory burden.
- Let posture set visual tone: muted for something stared at for hours, bold and clear for something glanced at briefly.
**Violation smell:** A glance-at utility is crammed with dense panels, or a primary all-day app shouts with high-saturation chrome.

### Excise

**What:** Any extra work the software demands that doesn't contribute to the user's actual goal.
**Apply in practice:**
- Hunt excise on every screen: needless confirmation dialogs, manual save, repositioning windows, redundant settings steps.
- Automate what the machine can do — autosave instead of asking the user to remember to save.
- Reduce navigation excise; every extra hop between the user and their goal is a tax.
**Violation smell:** Users must remember, re-enter, or reconfigure things the software could have remembered or done itself.

### Flow & direct manipulation

**What:** Keeping the user in an uninterrupted, immersed state by letting them act on objects directly.
**Apply in practice:**
- Let users see, grab, and move the real object (drag a file, resize from a handle) so the screen matches their mental model.
- Avoid modal interruptions that trap the user in one state; prefer **modeless** interaction.
- Provide robust, multi-step undo as a tool for fearless exploration — not just error correction — and make destructive actions reversible.
**Violation smell:** A blocking modal interrupts the main task, or a destructive action has no undo, so users hesitate and stop exploring.

### Modeless feedback & polite software

**What:** Software that informs without interrupting and behaves like a well-mannered person.
**Apply in practice:**
- Surface status in place (modeless) rather than in dialogs that demand acknowledgment.
- Make the product remember preferences, anticipate shortcuts, ask few questions, stay deferential, fix problems quietly, and apologize rather than blame.
- Prevent invalid input up front (disable impossible options) instead of scolding after the fact.
**Violation smell:** The app repeatedly asks the same questions, forgets prior choices, or throws blaming error dialogs.

### Designing across skill levels

**What:** Cater to beginners, perpetual intermediates, and experts at once, weighting the intermediate.
**Apply in practice:**
- Make beginners comfortable getting started (clear defaults, gentle onboarding) without locking them into a beginner mode forever.
- Reward experts with accelerators (shortcuts, power features) that stay out of the intermediate's way.
- Design the standard experience for the intermediate who knows the basics but doesn't remember every detail.
**Violation smell:** Permanent tutorials and tooltips clutter the interface, or only power users can accomplish ordinary tasks.

## Lightweight persona template

```
Persona: [First name + memorable one-line label, e.g. "Linda, the time-pressed clinic manager"]
Primary / Secondary / Customer / Served / Negative: [type]

Goals
  - End goal:        [the concrete outcome they want from this product]
  - Experience goal: [how they want to feel while using it]
  - Life goal:       [the longer-term aspiration this connects to]

Context
  - Where & when they use it: [environment, device, time pressure, interruptions]
  - Frequency & session length: [all day / a few times a week / brief bursts]

Frustrations
  - [pain point 1 with current tools/workflow]
  - [pain point 2]

Tech comfort: [low / intermediate / high — and any relevant domain expertise]
One sentence to remember them by: [e.g. "She'd abandon anything that makes her feel slow in front of patients."]
```

## Posture → UI implications

| Posture | Typical app type | UI density & attention guidance |
|---|---|---|
| Sovereign | Primary all-day apps (editor, email client, IDE) | Owns the screen; rich/dense tools, keyboard accelerators; optimize for experienced users; muted, neutral visuals for long sessions |
| Transient | Quick single-purpose tools (calculator, file-copy dialog) | Big, clear, self-explanatory controls; no memory burden; instantly understandable on reopening |
| Daemonic | Background processes (print queue, sync service) | Invisible by default; surfaces only when attention is genuinely required |
| Auxiliary | Always-on companions (system monitor, chat widget) | Continuously visible but never the focus; informative, low-noise, glanceable |

## Quick review checklist

1. Is there a named primary persona, and does this design serve their goal?
2. Does each feature map to a real user goal, not just a business/technical one?
3. Did a context scenario precede the interface decisions?
4. Have I removed or automated excise on every screen?
5. Is the product's posture chosen, and does UI density match it?
6. Is the standard experience tuned for perpetual intermediates?
7. Are there beginner on-ramps and expert accelerators without cluttering the middle?
8. Is undo robust and are destructive actions reversible?
9. Are interruptions modeless, and have I removed unnecessary modal dialogs?
10. Does the software prevent errors rather than blame the user — and would it pass as a "polite person"?

## See also

- [Interaction design principles](./interaction-design.md)
- [Process and sketching](./process-and-sketching.md)
- [Usability heuristics](./usability-heuristics.md)
