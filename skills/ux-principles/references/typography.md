# Typography for Screens

> When to use: any time you set text in a UI — picking fonts, sizing, spacing, hierarchy, or polishing copy for web and app interfaces.

Typography is not decoration; it carries meaning and guides the eye. Good interface type is nearly invisible — it serves the reader, not the designer. The rules below adapt Ellen Lupton's *Thinking with Type* to fluid, accessible screens.

## Apply-always rules

- Body text: minimum **16px** (`1rem`); never ship interface body copy below 14px.
- Line-height (leading): **1.5** for body (`line-height: 1.5`), tighter **1.1–1.3** for large headings.
- Measure (line length): **45–75 characters**, target ~66 — cap with `max-width: 65ch` on text blocks.
- Build a modular type scale with one ratio (~**1.25**, major third) instead of arbitrary px values.
- Default alignment is **flush-left / ragged-right** (`text-align: left`); avoid justified text on the web.
- Establish hierarchy with few signals — size, weight, space — not a dozen competing styles.
- Body contrast: **≥ 4.5:1** against background; large text (≥24px or ≥19px bold) **≥ 3:1** (WCAG AA).
- Limit to **1–2 typefaces**; get variety from weights and sizes within a family.
- Size in **relative units** (`rem`/`em`) so user zoom and browser font-size settings work.
- Prefer high **x-height**, screen-tuned fonts (Inter, Source Sans, system-ui) for small sizes.
- Use real font weights and italics — never CSS faux-bold/faux-italic on a single weight.
- Never rely on color alone to convey meaning, emphasis, or state — pair it with weight, icon, or text.

## Topics

### Choosing & classifying typefaces
**What:** Each typeface carries a tone and history; match it to the product's voice.
**Apply in UI:**
- Match content to register: humanist sans (Inter, Frutiger) for neutral product UI; geometric sans (Futura-like) for bold brand; serif (Georgia, Charter) for long-form reading.
- For screens, favor fonts with generous x-height and open apertures — they survive small sizes and low DPI.
- Load `font-display: swap` and a `system-ui` fallback stack to avoid invisible text.

**Violation smell:** A playful display face used for dense data tables, or five typefaces on one screen.

### Type anatomy & font vs. typeface
**What:** A typeface is the design (Inter); a font is one file/variant (Inter Bold Italic). x-height, ascenders, counters, and apertures drive screen legibility.
**Apply in UI:**
- Prefer faces with large x-height and open counters for body text at 14–16px.
- Use a typeface's true italic and true small-caps (`font-variant: small-caps`), not synthetic ones.
- Reference the family once via `font-family`; switch variants with `font-weight`/`font-style`.

**Violation smell:** `font-style: italic` faked on a font that ships no italic, smearing the glyphs.

### Measure (line length)
**What:** Lines that are too long lose the eye on the return sweep; too short break rhythm.
**Apply in UI:**
- Constrain prose: `max-width: 65ch` (roughly 45–75 characters including spaces).
- For multi-column layouts, keep each column inside the same character range.
- Don't let body text span a full 1440px viewport edge to edge.

**Violation smell:** A paragraph running the entire width of a wide monitor.

### Leading (line-height)
**What:** Vertical space between baselines; screens need more air than print.
**Apply in UI:**
- Body: `line-height: 1.5` (1.4–1.6 acceptable). WCAG asks ≥1.5 for blocks of text.
- Headings: tighten to `1.1`–`1.3` since they wrap less and read as shapes.
- Longer measures want more leading; increase it as line length grows.

**Violation smell:** 16px body text crammed at `line-height: 1.2`, lines visually touching.

### Tracking & kerning
**What:** Kerning adjusts space between specific pairs; tracking adjusts a whole run.
**Apply in UI:**
- Add slight positive tracking to all-caps and small-caps: `letter-spacing: 0.05em`.
- Tighten large display headings a touch: `letter-spacing: -0.01em` to `-0.02em`.
- Never add letter-spacing to lowercase body text — it hurts word recognition.

**Violation smell:** Lowercase paragraph copy with `letter-spacing: 2px`.

### Hierarchy
**What:** A visual ranking that tells the reader what to read first.
**Apply in UI:**
- Differentiate levels with size + weight + space; change one or two at a time, consistently.
- Use semantic HTML (`<h1>`–`<h6>`, `<p>`) so structure survives for screen readers and SEO.
- Prefer italic or weight for inline emphasis before reaching for color.

**Violation smell:** Everything bold and large — so nothing stands out.

### Alignment
**What:** Flush-left keeps even word spacing; justified equalizes both edges at a cost.
**Apply in UI:**
- Default body and UI labels to `text-align: left`.
- Avoid `text-align: justify` on the web — weak hyphenation creates "rivers" of white space.
- Reserve `center` for short, ceremonial text (empty states, hero headlines), never long copy.

**Violation smell:** Justified paragraphs in a narrow card with gaping word gaps.

### Type scale & modular scale
**What:** A consistent ratio between sizes creates harmony and predictable rhythm.
**Apply in UI:**
- Pick one ratio (1.2, 1.25, or 1.333) and derive all steps from a 16px base.
- Express in `rem` so the whole scale responds to root font-size.
- Tokenize sizes (`--font-h2`) rather than hardcoding px per component.

**Violation smell:** Headings at 22px, 27px, 31px with no relationship between them.

### Pairing fonts
**What:** Two faces should contrast clearly while sharing a mood.
**Apply in UI:**
- Pair across categories (serif heading + sans body) for obvious contrast; avoid two similar sans.
- Match x-heights so the pair sits comfortably at shared sizes.
- One personality font max; let a neutral workhorse carry the body.

**Violation smell:** Two grotesque sans-serifs so alike the pairing reads as a mistake.

### Font weights & web performance
**What:** Every weight and style is a separate file to download.
**Apply in UI:**
- Subset to the weights you use (e.g. 400/600/700); drop unused styles.
- Prefer **variable fonts** to cover a weight range in one file.
- Self-host `woff2` with `preload` for the critical face; always declare a fallback stack.

**Violation smell:** Loading 9 static weights when the UI uses 3.

### Responsive & fluid type
**What:** Screen type should scale smoothly, not jump at breakpoints.
**Apply in UI:**
- Size in `rem`; set `:root { font-size: 100%; }` to honor user defaults — never disable zoom.
- Use `clamp()` for fluid headings: `font-size: clamp(1.5rem, 1rem + 2.5vw, 3rem);`.
- Keep a minimum (the lower clamp bound) at or above readable body size.

**Violation smell:** Fixed `font-size: 14px` everywhere, ignoring viewport and user settings.

### Accessibility
**What:** Type must be readable for low-vision, color-blind, and zooming users.
**Apply in UI:**
- Body contrast ≥ 4.5:1; large text ≥ 3:1. Test real foreground/background pairs.
- Support 200% zoom and 1.5× line-height without clipping or overlap.
- Don't convey state by color alone; add an icon, label, or weight.

**Violation smell:** Light-gray (#AAA) 13px text on white, "errors" shown only in red.

### Readability vs. legibility
**What:** Legibility = distinguishing characters; readability = ease of reading running text.
**Apply in UI:**
- Choose legible faces for data/labels; tune measure, leading, and contrast for readable prose.
- Avoid long passages in ALL CAPS — they slow reading by removing word shapes.
- Keep paragraphs short and well-spaced on screen.

**Violation smell:** A legible font set in an unreadable wall of justified all-caps.

### White space
**What:** Space groups, separates, and gives type room to breathe.
**Apply in UI:**
- Separate paragraphs by space *or* first-line indent — not both.
- Use a spacing scale (4/8px steps) for margins and gaps; tie rhythm to line-height.
- Give headings more space above than below to bind them to their content.

**Violation smell:** Sections with no breathing room, headings floating equidistant from both blocks.

## Default type scale

Base 16px, ratio ≈ 1.25. Sizes in `rem` (1rem = 16px).

| Role     | Size            | Weight | Line-height |
|----------|-----------------|--------|-------------|
| Display  | 3rem (48px)     | 700    | 1.1         |
| H1       | 2.25rem (36px)  | 700    | 1.15        |
| H2       | 1.75rem (28px)  | 600    | 1.2         |
| H3       | 1.375rem (22px) | 600    | 1.3         |
| Body     | 1rem (16px)     | 400    | 1.5         |
| Small    | 0.875rem (14px) | 400    | 1.45        |
| Caption  | 0.75rem (12px)  | 400/500| 1.4         |

## Micro-typography quick fixes

- [ ] Curly quotes “ ” ‘ ’ for text; straight `" '` only for inch/foot marks.
- [ ] Curly apostrophe ’ (don’t, it’s), never `'`.
- [ ] Hyphen `-` for compounds, en dash `–` for ranges (3–5), em dash `—` for breaks.
- [ ] Non-breaking spaces (`&nbsp;`) before units and after short orphans (10&nbsp;MB).
- [ ] Single space after periods — no double spaces.
- [ ] Ligatures on for prose: `font-feature-settings: "liga" 1;` (default in most browsers).
- [ ] Tabular numerals in tables/data: `font-variant-numeric: tabular-nums;`.
- [ ] Avoid widows/orphans in headings: `text-wrap: balance;` on titles.

## Quick review checklist

1. Body ≥ 16px, sized in `rem`, user zoom not disabled.
2. Body line-height ~1.5; headings 1.1–1.3.
3. Measure capped at ~65ch (45–75 chars).
4. One consistent type scale and ratio across the UI.
5. Flush-left by default; no web justification.
6. Hierarchy from few, consistent signals (size/weight/space).
7. Contrast ≥ 4.5:1 body, ≥ 3:1 large; not color-only.
8. 1–2 typefaces; real weights/italics, no faux styles.
9. Only needed font weights loaded (variable font preferred).
10. Smart quotes, correct dashes, tabular numerals, no double spaces.

## See also

- [./design-principles.md](./design-principles.md)
- [./usability-heuristics.md](./usability-heuristics.md)
