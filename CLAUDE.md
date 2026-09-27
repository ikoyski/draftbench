# CLAUDE.md - Draftbench

## Project overview

Draftbench is an interactive coding primer designed to teach the fundamentals of web development through active practice. The app emphasizes a learning loop of: explain, build, inspect, and repeat.

The project contains four short courses:

- HTML
- CSS
- JavaScript
- Tailwind CSS

The intended experience is to help beginners move from theory to working code quickly, with each lesson centered on a small, buildable example and a final inspection quiz.

## Tech stack

- Frontend: vanilla HTML5, CSS3, and JavaScript
- Styling: custom CSS design system with CSS variables and theme support
- Theme support: light/dark mode via `prefers-color-scheme` plus a saved user override in `localStorage`
- Tailwind: included for the Tailwind course via CDN
- Sandbox: `iframe` + `srcdoc` for isolated preview rendering
- Persistence: `localStorage` stores progress, sandbox code, and theme state
- Routing: simple client-side routing driven by a `route` object and `render()` dispatcher

## Development patterns

- Data-driven content: course, lesson, and quiz data are defined in the `COURSES` array in `index.html`
- Event delegation: most UI actions are handled via a single document-level click listener checking `data-action`
- State management: global variables like `route`, `progress`, and `quizState` are used and synced to storage
- Rendering: the app clears and re-renders the `#app` container using a functional render flow

## Build and run

Draftbench is a static site with no build process.

For local development:

- open `index.html` directly in a modern browser, or
- serve the directory with a static HTTP server for the best sandbox behavior

Example commands:

```bash
npx serve .
# or
python3 -m http.server 8000
```

## Repository conventions

- Keep changes simple and lightweight; avoid frameworks or build tooling unless truly necessary
- Prefer vanilla JavaScript and CSS for new features
- If adding course content, follow the existing `COURSES` schema and ensure IDs are unique
- If creating a sandbox starter, make sure it remains compatible with `buildSrcdoc` and the supported content types (`html`, `css`, `js`, `tailwind`)
- Preserve the project’s focus on teaching fundamentals through interactive examples rather than abstract complexity

## AI assistant guidelines

- Prefer minimal, focused edits that match the project’s existing structure
- Avoid introducing dependency-heavy patterns when a native HTML/CSS/JS solution is adequate
- When changing content, keep lesson flow and quiz structure consistent with the current app design
- Treat the localStorage-based persistence and sandbox behavior as part of the product’s expected behavior, not as incidental implementation details
- When modifying or adding content, verify that it still works within the `iframe`-based preview flow and route-driven render model
