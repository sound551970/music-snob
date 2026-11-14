# music-snob

**Status:** Phase 0 — setup complete.

Bite-sized music criticism for eclectic listeners.

**music-snob** is a mobile-first web app for short, opinionated reviews of records across every genre: free jazz next to footwork, drone next to K-pop, field recordings next to hyperpop. It takes its cues from the long-form seriousness of *Pitchfork* and *The Wire* and fits that voice into something you can read while waiting for a train.

## Why

Good music writing tends to be long, scattered, or tied to one genre. music-snob tries for the opposite:

- **Short.** Each review is a few paragraphs, a score, and a reason to listen.
- **Eclectic.** No genre is "beneath" a review, and none is "above" one.
- **Opinionated.** A clear point of view, written for curious listeners, not insiders.

## What it does (planned)

- A scrollable feed of short reviews, built for a phone first
- Review pages with artwork, a score, a pull quote and the review text
- Browsing by genre, scene, label and era
- "If you like this, try…" links between records that have nothing obvious in common
- A typographic, editorial look: strong type, plenty of space, little decoration

## A learning project

This is also a **design-engineering learning project**. It's built by a senior UX designer learning front-end development, so the codebase favors:

- **Design tokens as the single source of truth.** Every color, spacing value, type style, radius and motion value comes from tokens, just like variables and styles in a Figma library.
- **Components that map to design components.** Small, reusable pieces with clear props (variants), similar to a component set in Figma.
- **Mobile first.** Layouts start at phone width and get more complex as the screen grows.
- **Accessibility from the start.** Semantic HTML, readable contrast, keyboard support and respect for reduced-motion settings.
- **Clarity over cleverness.** Code that's easy to read and explain matters more than code that's short.

## Tech stack (planned)

- **Node.js** to run the tooling
- **React** for the interface
- **Design tokens** defined in one place and exposed as CSS custom properties

Nothing is installed yet. Tooling choices (build tool, styling approach, testing) will be made and written down here as the project grows.

## Getting started

Setup steps will be added once the project is scaffolded. They'll probably look like this:

```bash
npm install     # install dependencies
npm run dev     # start a local development server
```

## Project structure (planned)

```
music-snob/
├── src/
│   ├── tokens/       # design tokens: color, space, type, radius, motion
│   ├── components/   # reusable UI pieces (ReviewCard, Score, Tag…)
│   ├── pages/        # full screens (Feed, Review, Genre…)
│   └── content/      # review data
├── README.md
└── CLAUDE.md         # working rules for AI-assisted development
```

## Working with Claude Code

See [CLAUDE.md](./CLAUDE.md) for the rules Claude follows in this repo: plain-language explanations, tokens only, and no packages installed without asking first.
