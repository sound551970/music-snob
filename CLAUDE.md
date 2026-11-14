# CLAUDE.md

Working rules for Claude in the **music-snob** repo. See [README.md](./README.md) for what the project is.

## Who you're working with

I'm a senior UX designer with professional HTML/CSS experience from before 2018 and some vanilla JS. I'm new to modern JS, TypeScript and React — explain those in depth, and flag any outdated CSS habits. I know design deeply (systems, components, tokens, layout, typography, prototyping, and accessibility at the design level). Treat me as an expert collaborator catching up on the modern front-end stack; explain code-level accessibility (semantics, ARIA, focus) as we go.

## 1. Explain every change in plain terms

- **Before** making a change, say briefly what you're about to do and why.
- **After** making a change, explain what changed, in which files, and what it does, in plain language.
- Define any jargon the first time it comes up (e.g. "props", "state", "hook", "build step", "dependency").
- Where it helps, **relate concepts to design tools** like Figma. For example:
  - Design tokens → Figma variables and styles
  - React components → Figma components; props → variants and component properties
  - Component state → interactive component states (hover, pressed, selected)
  - CSS Flexbox → Auto layout; `gap` → item spacing; `padding` → auto layout padding
  - CSS Grid → layout grids
  - Media queries / breakpoints → frames for different devices
  - Git commits → version history; branches → Figma branches
  - `package.json` dependencies → libraries enabled in a file
- Keep explanations short and concrete. Show the relevant lines of code rather than describing them abstractly.
- If there are several reasonable approaches, name the tradeoff in a sentence or two and recommend one.

## 2. Never hard-code design values. Always use tokens.

All visual values come from design tokens. This includes:

- **Color**: text, backgrounds, borders, shadows, focus rings
- **Spacing**: padding, margin, gap, positioning offsets
- **Typography**: font family, size, weight, line height, letter spacing
- **Also**: border radius, border width, shadows, z-index, motion duration and easing, breakpoints

Rules:

- ❌ `color: #ff3b30;` `padding: 16px;` `font-size: 1.125rem;`
- ✅ `color: var(--color-accent);` `padding: var(--space-4);` `font: var(--type-body);`
- If a token you need doesn't exist, **stop and propose one** (name, value, and where it'll be used) instead of inventing an inline value. Treat it like adding a new variable to the library.
- Keep tokens in one place (planned: `src/tokens/`). Components consume tokens and never define raw values.
- Name tokens by **purpose** (e.g. `--color-text-muted`), not by appearance (e.g. `--grey-500`), except in the base palette layer that semantic tokens point to.
- The only exceptions are values that aren't design decisions, such as `0`, `100%`, `1fr`, or `auto`. When unsure, ask.

## 3. Ask before installing any package

- **Never** run `npm install <pkg>`, `npx create-…`, or anything else that adds a dependency without asking first.
- When proposing a package, explain: what it does, why we need it, whether there's a simpler option without it, and roughly how big or widely used it is.
- This also covers dev tools (linters, formatters, test runners, build tools) and global installs.
- Running `npm install` to restore dependencies already listed in `package.json` is fine. Mention that you're doing it.

## General working style

- Make small, focused changes I can follow, one concept at a time.
- Prefer clear, readable code over clever or very short code.
- Build **mobile first**: style for small screens by default, then add larger breakpoints.
- Use semantic HTML and accessible patterns (labels, contrast, focus states, `prefers-reduced-motion`).
- Don't commit or push unless I ask. When I do, write clear commit messages.
- If something I ask for conflicts with these rules, point it out instead of quietly working around it.
