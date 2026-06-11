# UX Prototypes

Laurel UX prototype repo. Each prototype is a self-contained HTML file served via GitHub Pages.

**Live site:** https://josh-laurelai.github.io/ux-prototypes/

## Creating a new prototype

1. Create `{slug}/index.html` — lowercase, hyphenated slug (e.g., `timer-card`, `smart-filters`)
2. Add an entry to `index.html` (the landing page) under the right section. Mark new protos with `proto-tag new`
3. Commit and push — GitHub Pages deploys automatically
4. Share: `https://josh-laurelai.github.io/ux-prototypes/{slug}/`

## Design System & Template (READ BEFORE BUILDING)

Before writing any prototype HTML, **always read both of these files**:

1. **`_design-system.html`** — The complete Laurel component reference. Contains the Tailwind config (custom color palette, shadows, fonts), all component patterns (buttons, chips, entry rows, activity rows, stat cards, data tables, empty states, inputs, toolbars, suggested matters, app bar nav), and strict rules about when to use each. **Use only the components, colors, and patterns defined here.** Do not invent new variants or use arbitrary hex values.

2. **`_template/index.html`** — The product shell template. Three-panel layout: 80px black app bar, flexible entry sheet (center), 320px work activity panel (right). Contains realistic sample data for entry groups, status states, and activity rows.

### How to use them together
- Read `_design-system.html` first to understand available components and rules
- Copy the Tailwind config block (the `<script>tailwind.config = {...}</script>`) into every prototype — this is the canonical color palette and shadow system
- When the prototype needs product context (timesheet interactions, layout changes, modal work), fork `_template/index.html` and modify the relevant section
- When building isolated components or abstract explorations, use the design system components but skip the template shell
- If a component you need isn't in the design system, use the closest match — do not improvise new patterns

### Product Shell Template

Use the template when a prototype needs to feel like it lives inside the real product. Fork it and modify the relevant section. Don't force it onto every prototype — use judgment about whether the product shell adds value.

## Repo structure

```
index.html                    ← landing page listing all prototypes
_design-system.html           ← component reference and Tailwind config
_template/index.html          ← product shell template (fork for context-heavy protos)
_docs/                        ← specs and reference docs (not deployed)
.github/workflows/static.yml  ← GitHub Pages deployment (auto)
{slug}/index.html             ← one folder per prototype
```

## Conventions

- Prototypes are single self-contained HTML files (CSS + JS inline)
- If iterating on an existing prototype, update it in place
- Always offer several variants and document tradeoffs
- Prototypes should be interactive where possible (tabs, toggles, collapsible sections)
- Research best practices before building — look at how comparable products solve similar problems

### JTBD-First Thinking

Before jumping to UI patterns, start by asking **what job the user is hiring this feature/interaction to do**. Map the user goals first, then work backward to the design.

- Ask "why would someone do this?" before "how should this work?"
- Name the jobs explicitly so they can be evaluated and challenged
- Different jobs may need different solutions — don't force one pattern to serve all jobs

## Git config

```
git config user.email "josh@laurel.ai"
git config user.name "josh-laurelai"
```
