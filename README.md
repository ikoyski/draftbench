# Draftbench

Draftbench is an interactive coding primer for beginners who want to learn web development by doing, not just reading. It turns each topic into a short, guided lesson with a live code bench, a clear explanation of the underlying ideas, and a final inspection challenge to check understanding.

The project follows a simple philosophy: "Build things. Understand why they work."

## Curriculum

Draftbench is organized into six short courses:

- HTML Foundations
- CSS Fundamentals
- Tailwind CSS
- JavaScript Essentials
- APIs & Async JavaScript
- To-Do List Capstone

Each course is meant to be approachable and hands-on, helping learners move from markup to styling to interaction and modern utility-based styling.

## Key Features

- Live sandboxing with an iframe-based preview
- Guided lessons that teach the why behind the code
- Final inspection-style quizzes
- Progress saved in localStorage so learners can continue where they left off
- Light/Dark theme support with a user override
- A simple client-side routing experience without a framework

## How it works

Draftbench is a static frontend app built with vanilla HTML, CSS, and JavaScript.

- Lesson content and quiz data live in a central `COURSES` structure inside `index.html`
- User interactions use event delegation through `data-action` handlers
- Application state is kept in simple global variables and synchronized with `localStorage`
- The sandbox renders code updates via `iframe` with `srcdoc`

## Run locally

There is no build step.

Open `index.html` directly in a browser, or serve the folder locally for the best experience:

```bash
npx serve .
# or
python3 -m http.server 8000
```

Then open the local URL shown by the server.

## Project structure

- `index.html`: The main app, lesson data, rendering logic, route handling, and sandbox system
- `README.md`: Project overview and run instructions
- `CLAUDE.md`: AI assistant guidance for contributing and maintaining the project

## For contributors

Keep the project lightweight and vanilla. Prefer small, readable JavaScript and CSS rather than introducing frameworks or build tooling unless the project explicitly needs them.

When adding content or sandbox examples:

- follow the existing `COURSES` schema
- keep IDs unique and descriptive
- ensure new sandbox starters work with the current `buildSrcdoc` logic
- maintain compatibility with the app's localStorage-based persistence model
