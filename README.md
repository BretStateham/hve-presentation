# HVE Presentation

Presentation materials for "Hypervelocity Engineering" (HVE) upskilling, built with [Marp](https://marp.app/).

## Quick Start

```bash
# Install dependencies
npm install

# Start presentation server (browse all decks)
npm start
```

Then open [http://localhost:8080](http://localhost:8080) to browse all presentations.

## Available Presentations

| # | Topic | Path |
|---|-------|------|
| 1 | Introduction to HVE | `presentations/01-introduction/introduction.md` |

## Usage

### Presenting

```bash
# Launch Marp server mode (serves all presentations)
npm start
```

Navigate to any presentation in your browser. Use:
- **← →** arrow keys to navigate slides
- **F** for fullscreen
- **P** for presenter view with notes

### Authoring

1. Install the [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) extension
2. Open any `.md` file under `presentations/`
3. Use the VS Code Markdown preview to see slides live

### Building

```bash
# Build all presentations to HTML
npm run build

# Build all presentations to PDF
npm run build:pdf

# Watch mode (auto-rebuild on changes)
npm run watch
```

## Adding a New Presentation

1. Create a new directory under `presentations/`:
   ```
   presentations/02-your-topic/
   ├── your-topic.md      # Slide deck
   └── images/             # Presentation-specific images
   ```

2. Start your `.md` file with Marp front matter:
   ```markdown
   ---
   marp: true
   theme: default
   paginate: true
   ---

   # Your Title

   ---

   ## Slide 2
   ```

3. Update `presentations/index.md` to link to your new deck.

## Project Structure

```
hve-presentation/
├── package.json            # npm scripts and dependencies
├── marp.config.mjs         # Shared Marp configuration
├── themes/                 # Custom CSS themes
│   └── hve.css             # HVE-branded theme
├── images/                 # Shared images (logos, etc.)
├── presentations/          # All presentation decks
│   ├── index.md            # Landing page / table of contents
│   └── 01-introduction/    # First presentation
│       ├── introduction.md # Slide deck
│       └── images/         # Deck-specific images
└── .vscode/                # VS Code configuration
    ├── settings.json       # Marp theme paths
    └── extensions.json     # Recommended extensions
```

## Themes

Custom themes are in the `themes/` directory. Reference them in your slide front matter:

```markdown
---
marp: true
theme: hve
---
```

## Dependencies

- [Node.js](https://nodejs.org/) >= 18
- [@marp-team/marp-cli](https://github.com/marp-team/marp-cli)

