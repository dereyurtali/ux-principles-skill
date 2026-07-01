# UX Principles — a Claude Code skill

A [Claude Code](https://claude.com/claude-code) **skill** that gives Claude practical,
opinionated UX, interaction-design, and visual-design knowledge to use while building and
reviewing user interfaces.

It distills seven classic design books into actionable rules, checklists, and review
heuristics — so that when Claude **designs an interface from scratch**, writes UI code, or
audits a screen, it applies proven design thinking instead of guessing. Each reference file is
grounded in a specific book and teaches that author's **exact vocabulary, rules, numbers, and
examples** — so Claude applies the *named* concept correctly (a "sovereign posture," a "Gulf of
Evaluation," a "river" in justified text) rather than asserting taste.

> Sources behind the skill: Don Norman's design principles, Alan Cooper's *About Face*
> (goal-directed design), Lidwell/Holden/Butler's *Universal Principles of Design*, Ellen
> Lupton's *Thinking with Type*, Bill Buxton's *Sketching User Experiences*, Preece/Rogers/
> Sharp's *Interaction Design*, and Bill Moggridge's *Designing Interactions*.

## What it does

When the skill is active, Claude will, for any user-facing work:

- Design for **user goals**, not just features or tasks, and remove unnecessary busywork (**excise**).
- Match the user's **mental model** and close Norman's **Gulfs of Execution and Evaluation**.
- Choose the right **posture** (sovereign / transient / daemonic) for how the product is used.
- Apply **visual hierarchy and grouping** using Gestalt and layout laws (Fitts, Hick, signal-to-noise, 7±2).
- Use **readable, accessible typography** with real rules — measure, leading, alignment, hierarchy.
- Always show **system status** and design **every UI state** (empty, loading, error, success…).
- **Prevent and forgive errors** — constrain inputs, prefer undo over destructive confirms, never blame the user.
- **Explore alternatives** cheaply before committing — "get the *right* design before getting the design right."
- Review interfaces against **Nielsen's heuristics**, **Shneiderman's rules**, and **WCAG (POUR)** accessibility.
- Avoid **dark patterns** and flag them when asked to build one.

## What's inside

Each reference file distills one (or two) of the source books:

```
skills/ux-principles-skill/
├── SKILL.md                          # entry point: when/how to use, routing, core defaults
└── references/
    ├── design-of-everyday-things.md  # Norman — affordances/signifiers, mapping, feedback,
    │                                 #   conceptual models, the two Gulfs, constraints, error
    ├── goal-directed-design.md       # Cooper (About Face) — goals vs tasks, personas,
    │                                 #   scenarios, requirements, postures, flow, excise
    ├── design-principles.md          # Lidwell (Universal Principles) — ~50 UI laws: Gestalt,
    │                                 #   Fitts, Hick, 7±2, signal-to-noise, 80/20, progressive disclosure
    ├── typography.md                 # Lupton (Thinking with Type) — anatomy, measure, leading,
    │                                 #   alignment, rivers/widows/orphans, grids, punctuation (+ CSS)
    ├── interaction-design-process.md # Preece/Rogers/Sharp + Moggridge — usability goals, Double
    │                                 #   Diamond, interaction types, prototyping, evaluation
    ├── sketching-and-ideation.md     # Buxton — right design vs design right, sketch vs prototype,
    │                                 #   the design funnel, ideation methods (10+10, storyboards…)
    └── usability-heuristics.md       # review toolkit — Nielsen 10, Shneiderman 8, WCAG POUR,
                                      #   severity ratings, finding-report format
summaries/                            # longer (Turkish) chapter summaries of the source books
```

The skill uses **progressive disclosure**: `SKILL.md` is short and always loaded; the
heavier reference files are pulled in only when a task needs them.

> **Note on sources.** The original books are copyrighted and are **not** included in this
> repo — only the distilled reference files ship. The references synthesize and cite the books;
> they do not reproduce their text.

## Installation

### Option A — as a personal skill (works everywhere, simplest)

Copy the skill folder into your Claude Code skills directory:

```bash
git clone https://github.com/dereyurtali/ux-principles-skill.git
# user-level (available in all your projects):
mkdir -p ~/.claude/skills
cp -R ux-principles-skill/skills/ux-principles-skill ~/.claude/skills/
```

Or install it **per project** so your whole team gets it via version control:

```bash
mkdir -p /path/to/your-project/.claude/skills
cp -R ux-principles-skill/skills/ux-principles-skill /path/to/your-project/.claude/skills/
```

Restart Claude Code (or start a new session) and the skill will be auto-discovered.

### Option B — as a plugin (via marketplace)

```text
/plugin marketplace add dereyurtali/ux-principles-skill
/plugin install ux-principles-skill@ux-principles-skill
```

## Usage

You usually don't need to do anything — Claude activates the skill automatically when you
work on UI/UX. You can also nudge it explicitly:

- *"Build the settings screen — apply the ux-principles-skill skill."*
- *"Review this component for usability and accessibility."*
- *"Propose a few layout options for this dashboard before coding."*

## Verifying it's installed

In Claude Code, run `/skills` (or ask "what skills do you have?"). You should see
**ux-principles-skill** listed.

## Contributing

Issues and PRs welcome — especially concrete, implementable rules and real-world examples.
Keep reference content original (no copyrighted excerpts), practical, and oriented to web/
mobile/app UI.

## License

[MIT](LICENSE). The reference material is original writing synthesizing widely-taught design
principles; it does not reproduce text from the source books.
