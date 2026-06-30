# UX Principles — a Claude Code skill

A [Claude Code](https://claude.com/claude-code) **skill** that gives Claude practical,
opinionated UX, interaction-design, and visual-design knowledge to use while building and
reviewing user interfaces.

It distills ideas from seven classic design books into actionable rules, checklists, and
review heuristics — so that when Claude writes UI code or audits a screen, it applies proven
design thinking instead of guessing.

> Sources behind the skill: Don Norman's design principles, Alan Cooper's *About Face*
> (goal-directed design), Lidwell/Holden/Butler's *Universal Principles of Design*, Ellen
> Lupton's *Thinking with Type*, Bill Buxton's *Sketching User Experiences*, Preece/Rogers/
> Sharp's *Interaction Design*, and Bill Moggridge's *Designing Interactions*.

## What it does

When the skill is active, Claude will, for any user-facing work:

- Design for **user goals**, not just features, and remove unnecessary busywork.
- Always show **system status** and design **every UI state** (empty, loading, error, success…).
- Apply **visual hierarchy, grouping, and spacing** using Gestalt and layout laws.
- Use **readable, accessible typography** with sane defaults.
- **Prevent and forgive errors**, prefer undo over destructive confirms.
- Review interfaces against **usability heuristics** and **accessibility** checklists.
- Avoid **dark patterns** and flag them when asked to build one.

## What's inside

```
skills/ux-principles-skill/
├── SKILL.md                         # entry point: when/how to use + core defaults
└── references/
    ├── design-principles.md         # Gestalt, Fitts, Hick, hierarchy, progressive disclosure
    ├── interaction-design.md        # affordances, feedback, mental models, perceived perf
    ├── goal-directed-design.md      # goals vs tasks, personas, scenarios, postures, excise
    ├── typography.md                # measure, leading, scale, responsive & accessible type
    ├── process-and-sketching.md     # explore alternatives, fidelity ladder, design all states
    └── usability-heuristics.md      # review toolkit: heuristics, a11y, forms, severity, report
summaries/                           # detailed (Turkish) summaries of the source books
```

The skill uses **progressive disclosure**: `SKILL.md` is short and always loaded; the
heavier reference files are pulled in only when a task needs them.

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
