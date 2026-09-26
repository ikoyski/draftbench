# CLAUDE.md - Draftbench

## Project Overview
Draftbench is an interactive coding primer designed to teach the fundamentals of web development. It provides a structured learning path through four short courses: HTML, CSS, JavaScript, and Tailwind CSS. The core philosophy is "Build things. Understand why they work," combining conceptual explanations with an immediate, live coding "bench" (sandbox) and final "inspection" quizzes.

## Tech Stack
- **Frontend**: Vanilla HTML5, CSS3, and JavaScript (ES5/ES6).
- **Styling**: 
    - Custom CSS implementation with a comprehensive design system using CSS variables.
    - Theme support: Dynamic Light/Dark mode based on `prefers-color-scheme` and user override stored in `localStorage`.
    - Tailwind CSS integration for the Tailwind course via CDN.
- **Key Mechanisms**:
    - **Sandbox**: Uses `iframe` with the `srcdoc` attribute to render live code updates in isolation.
    - **Persistence**: `localStorage` is used to track user progress (`db_progress`), save sandbox code (`db_sandbox_{key}`), and remember theme preference (`db_theme`).
    - **Routing**: Simple client-side state-based routing managed via a `route` object and a `render()` dispatch function.

## Development Patterns
- **Data-Driven Content**: All courses, lessons, and quiz questions are defined in a central `COURSES` array within `index.html`. Adding new content requires adding objects to this array.
- **Event Delegation**: Most user interactions are handled by a single global click listener on `document` that checks for `data-action` attributes.
- **State Management**: Application state is held in global variables (`route`, `progress`, `quizState`) and synchronized with `localStorage`.
- **Rendering**: A functional rendering approach where `render()` clears the `#app` element and injects new HTML based on the current route.

## Build & Run Instructions
Draftbench is a purely static site with no build step.
- **Local Development**: Open `index.html` directly in any modern web browser.
- **Serving**: For a better experience (and to avoid some CORS/security restrictions with iframes in some environments), serve the directory using a static server:
  ```bash
  npx serve .
  # or
  python3 -m http.server 8000
  ```

## Guiding Principles for AI Assistants
- **Maintaining Simplicity**: The project avoids frameworks and build tools. Keep new features in vanilla JS/CSS unless specifically asked otherwise.
- **Content Updates**: When adding lessons or quiz questions, follow the schema in the `COURSES` array. Ensure IDs are unique and descriptive.
- **Sandbox Compatibility**: When creating new sandbox starters, ensure they are compatible with the `buildSrcdoc` logic (handling `html`, `css`, `js`, or `tailwind` types).
