# Morgenbooster Deck

Slide deck for *Designing with a vibe: When AI turns ideas into experiences* — Morgenbooster, 13 May 2026.

Speaker: Nils Smed, Partner at Heyra.

## What's here

```
morgenbooster/
├── morgenbooster-deck.html    The live deck
├── media/                     Build images and videos (13 tools)
│   └── linkedin-posts.md      Source posts the build slides pull from
└── design-system/             Visual system reference
    ├── DESIGN.md              Tokens, components, tone rules
    └── design-system.html     Visual showcase of every component
```

## Running the deck

Open `morgenbooster-deck.html` in any modern browser. No build step. No dependencies. Just the file and the `media/` folder next to it.

For full-screen presentation: press `F11` (or Cmd+Ctrl+F on macOS).

### Keyboard shortcuts

| Key | Action |
|---|---|
| `→` `Space` `PageDown` | Next slide |
| `←` `PageUp` | Previous slide |
| `Home` | Jump to first slide |
| `End` | Jump to last slide |
| `P` | Download PDF |

### Exporting to PDF

Click **Download PDF** (bottom center) or press `P`. In the browser print dialog:

- Destination: **Save as PDF**
- Layout: auto-detected from `@page` (16:9, 13.333in × 7.5in)
- Margins: None / Default
- **Background graphics: ON** *(critical — otherwise dark slides print white)*

## Deck structure

20 minutes. Roughly:

1. Cover · Confession · The 20+ tools
2. Act 1 — The gap (old way)
3. Act 2 — The shift (new way + the bottleneck moved)
4. Act 3 — The builds (13 tools available, 4–5 shown live)
5. The method (JEDUF · spec-driven flow · stack)
6. Proven at scale (Novo Nordisk Foundation)
7. Act 4 — Speed ≠ wisdom · The instinct is still yours
8. Close

Most builds in the deck are bonus/library — only 4–5 are shown during the talk. The rest are there for Q&A or future versions.

## Tools featured

| # | Tool | Status |
|---|---|---|
| /01 | Unsub™ | Live |
| /02 | Nobait™ | Soon to Chrome Web Store |
| /03 | Wiretap™ Guardian | Live |
| /04 | Acquired™ | Live (Danish companies) |
| /05 | Explain™ | POC with sundhed.dk |
| /06 | Mæla™ | Going live soon |
| /07 | Transcribe™ | Live (community-funded) |
| /08 | Holger™ | Internal |
| /09 | Subscriptions *(Unsub feature)* | Live |
| /10 | Flipper | Closed |
| /11 | Promos *(Unsub feature)* | Live |
| /12 | Notes *(Wiretap feature)* | Live |
| /13 | Wiretap™ | Live |

## Design system

The deck uses a personal design system documented in `design-system/`. Light, minimal, type-led. Inter font, monochrome with black accents, opinionated tone.

See `design-system/DESIGN.md` for tokens and rules. Open `design-system/design-system.html` for the visual showcase.
