# Claude Slides

An agent skill that turns a short brief into a presentation you can run from any browser.

Project page: https://marcogalluccio.com/claude-slides/

## What it is

Claude Slides is a skill for [Claude Code](https://claude.com/claude-code) that generates HTML slide decks: a fixed 1920×1080 canvas, keyboard navigation (arrow keys, space), progress bar, fullscreen, print-to-PDF. Every deck is a single self-contained HTML file, with an opt-in animation system for in-slide step reveals (cards appearing one by one, SVG arrows drawing themselves, popup payoffs).

It was born from Marco Galluccio's real workflow for workshops, talks and pitches, then stripped of branding so anyone can use it as a starting point.

## Install

Personal install (available in every project):

```bash
git clone https://github.com/marcogalluccio/claude-slides.git ~/.claude/skills/claude-slides
```

Or clone it into a single project's `.claude/skills/` folder if you want it scoped to that repo.

## Usage

Open Claude Code and ask for slides, in any language:

- "Crea le slide per un workshop di 2 ore su AI agents per un team non tecnico"
- "5 minute pitch on our product, palette #0F766E #134E4A, font Space Grotesk"
- "Deck per un talk di 20 minuti sul Q3: i dati stanno in docs/q3.md"

The skill runs a quick brief (topic, audience, type, duration), proposes a narrative arc and an ASCII wireframe, waits for your approval, then generates the deck and opens it in the browser. From there you iterate slide by slide in plain conversation.

## How it works

Three files do the heavy lifting: `template.html` is the boilerplate (design tokens, viewer chrome, step controller), `components.md` is a catalog of ready layout patterns (cards, grids, terminals, mockups, diagrams), `animations.md` holds the animation recipes and their hard-earned gotchas. The workflow is wireframe-first: you approve the structure of every slide before a single line of HTML is written.

## Try the demo

Open `examples/demo-deck.html` in your browser. Navigate with the left and right arrow keys (some slides reveal their content step by step), press R to reset, and use the button in the top right corner for fullscreen.

## Customization

The whole look lives in a handful of CSS variables at the top of each deck: `--cs-primary`, `--cs-secondary`, `--cs-cream`, plus the body `font-family`. Override them (or just tell the agent "palette #abc #def, font X") for instant rebranding. Everything else in the CSS is parametric.

## License

MIT
