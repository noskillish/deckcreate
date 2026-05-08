# Design System
*A personal system by Nils Smed*

A visual system for one-pagers, slide decks, and presentation pages. Light, minimal, type-led. Inspired by editorial layouts (NYT, mockups.directory) and product overview pages (Palantir).

The principle: most pages are a headline, two columns, and breathing room. Anything more should earn its place.

Note: examples below reference Heyra Arc, Heyra Code, and Heyra Core because those were the projects this system was built around. The system itself is general-purpose.

---

## Colors

```
Background          #f5f5f3   warm off-white
Surface (subtle)    #fafaf8   slightly lighter than background, for cards
Surface (white)     #ffffff   for cards that should pop more
Hero / dark slide   #1a1a1a   inverted callouts, dark slides

Border (soft)       #e0e0db
Border (medium)     #d5d5d0
Pill background     #eeeee9

Text primary        #1a1a1a
Text dim            #a0a09a   subtitles, body that recedes
Text very dim       #b5b5b0   meta info, decorative
Text faint          #c5c5c0   labels next to pills

On-dark text        #f5f5f3
On-dark dim         #ccc
On-dark very dim    #888
```

**Use color for hierarchy, not decoration.** Two grays do most of the work.

---

## Typography

**Font:** Inter (Google Fonts). Weights 300, 400, 500, 600.

```
H1 (display)       clamp(2rem, 4.5vw, 3.2rem)  weight 500  letter-spacing -0.03em  line-height 1.2
H1 (slide cover)   clamp(2.5rem, 6vw, 5rem)    weight 500  letter-spacing -0.035em line-height 1.1
H2                 clamp(1.75rem, 3.5vw, 2.6rem) weight 500  letter-spacing -0.025em
H3 (section)       9.5pt–1rem                  weight 500  letter-spacing -0.01em
Body / subtitle    0.78–0.88rem                weight 400  line-height 1.5–1.6
Eyebrow / label    0.65–0.75rem  uppercase  weight 500  letter-spacing 0.08em  color #a0a09a
Big number         clamp(2.4rem, 4.5vw, 3.5rem) weight 600 letter-spacing -0.035em
```

**Print (A4 one-pagers):** use `pt` units, not `rem`. Headlines around 26–28pt, body 8–10pt, eyebrows 7pt.

---

## The headline pattern

Headlines use a bold-then-dim split. The first phrase carries weight (500). The continuation fades to gray (300, color `#b5b5b0`). This gives every headline a built-in narrative — anchor + extension.

```html
<h1>Spec-driven development <span class="dim">at scale.</span></h1>
<h1>Heyra Arc. <span class="dim">Spec-driven AI development at scale.</span></h1>
<h1>One spec. <span class="dim">Full transparency.</span></h1>
```

```css
h1 span.dim {
  color: #b5b5b0;
  font-weight: 300;
}
```

This is the most consistent visual identity in the system. Use it.

---

## Spacing & rhythm

- **A4 one-pagers:** 18mm top/bottom, 20mm left/right. Sections separated by 16–22pt margin-top. Use `justify-content: space-evenly` to distribute on the page.
- **Slides:** 6vh top/bottom, 8vw sides. Max content width 1100px.
- **Cards/callouts:** 1rem–1.5rem padding internal.
- **Border radius:** 6–10pt for cards, 4pt for small buttons/steps.

---

## Components

### Eyebrow + Headline + Subtitle
The default opening of any section. Eyebrow tags context. Headline carries the message. Subtitle gives one line of nuance.

### Two-column (problem / fix)
Equal columns, gap 30–40pt. Each column has H3 + paragraph. Use for contrast: before/after, problem/solution, today/with-us.

### Three-column (why / how / what)
Three equal columns. Used for structural breakdowns. Each column gets a 1-word title and a 1–2 sentence body.

### Capability list (Q&A)
Rows separated by thin borders. Left column = question (medium weight). Right column = answer (regular, dim color). Used for "what it solves" sections.

### Callout (dark block)
Black background `#1a1a1a`, white text, rounded 6pt. For "Why now" or other emphasized sections. One per page max.

### Dot flow
Five (or N) horizontal steps connected by a thin line. Each step: 9px black dot, H4 label, dim caption below. Used for process flows.

### Stack grid
Four-column grid of category cards. Each card has uppercase label + list of tools with small monochrome SVG marks. Used to show "the stack" or "what we use."

### Spec block + context + outputs
A vertical flow: dark spec block at top → context pills with "draws from" prefix → "AI orchestrates" divider line → three output cards. Used for showing how a system processes input.

### Product slide (Palantir style)
Big product name on the right (clamp 4–8rem, weight 500, letter-spacing -0.045em). Description on the left with /01–/0n number, tag, headline, body, stat line. Used for product overviews and storytelling about builds.

### JEDUF three-column
Three columns showing extremes vs middle path. Outer columns (waterfall, vibe coding) on light cards. Center column on dark `#1a1a1a` background as the hero. Steps stacked vertically inside each column.

---

## Tone & voice rules

- **Bold the keyword. Dim the rest.** That's the rhythm of every headline.
- **No em-dashes in body copy.** Use periods or split into shorter sentences. (Em-dashes are fine in author bylines.)
- **No fluff.** If a sentence doesn't add information, delete it.
- **Use the names.** Heyra Arc, Heyra Code, Heyra Core. Not "the framework," "the IDE," "the system."
- **Spec-driven AI development.** That's the term. Don't shorten or paraphrase.
- **Numbers should be specific.** "7×" beats "huge gains." "35 use cases / week / engineer" beats "much faster."
- **Headlines are statements, not questions.** Q&A rows are an exception — the question is the format.

---

## Page formats

### Slide deck (full-screen presentation)
- One HTML file, one slide per `<section class="slide">`.
- Arrow keys to navigate. Space and arrow-right also advance.
- Progress bar at top, slide counter bottom-right.
- Light slides default. Dark slides (`.slide.dark`) for emphasis moments.

### A4 one-pager (print)
- Fixed `210mm × 297mm` page.
- `@page { size: A4; margin: 0; }` for clean print.
- Sections distributed with `justify-content: space-evenly`.
- All sizing in `pt` so it renders consistently.

### Product overview (web page)
- Long-form layout, max-width 1100–1200px.
- Hero headline, then rows of products with massive name on the right.

---

## What this isn't

- It's not a framework. There's no NPM package, no CSS variables file, no build step. Each page is a single self-contained HTML file with inline styles.
- It's not designed for a real product UI. This is for content pages — decks, one-pagers, overviews. If you build an app, use a real component library.
- It's not pretending to be neutral. The voice is opinionated. Lean into it.

---

## File examples

| Use case | Reference file |
|---|---|
| A4 one-pager | `spec-driven-full-story.html`, `heyra-code-onepager.html` |
| Slide deck | `morgenbooster-deck.html` |
| Visual product overview | `heyra-products.html` |
| Three-column comparison | `spec-driven-jeduf.html` |
| Diagram-heavy slide | `spec-driven-transparency.html` |
| Agenda / invitation | `danske-bank-agenda.html` |
