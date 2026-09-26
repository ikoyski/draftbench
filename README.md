# Draftbench

**Draftbench** is an interactive coding primer designed to help beginners build things and understand why they work. It replaces passive reading with active doing through a structured "Plan & Bench" approach.

## 📚 The Curriculum

Draftbench offers four focused courses that take you from zero to a functioning layout:

- **HTML Foundations**: Structure every page with the tags that hold the web together.
- **CSS Fundamentals**: Give your HTML a look with spacing, color, and layout.
- **JavaScript Essentials**: Make pages react with variables, logic, and the DOM.
- **Tailwind CSS**: Style directly in your markup with utility classes.

## ✨ Key Features

- **Live Sandboxes**: Every lesson includes a "Bench"—an integrated live editor where you can tweak code and see the results instantly.
- **Inspection Quizzes**: Each course ends with a final inspection quiz to verify your understanding and sign off on the material.
- **Progress Tracking**: Your progress and your custom sandbox code are saved locally in your browser, so you can pick up right where you left off.
- **Adaptive Design**: A clean, focused interface with full support for Light and Dark themes.

## 🚀 Getting Started

Draftbench is a static site and requires no installation or build steps.

### Running Locally
1. Clone or download the repository.
2. Open `index.html` in any modern web browser.

### Recommended: Serving via Static Server
For the best experience, serve the project using a simple static server:

```bash
# Using npx
npx serve .

# Using Python
python3 -m http.server 8000
```

## 📁 Project Structure

- `index.html`: The heart of the application. Contains the entire UI, the course data, the routing logic, and the sandbox engine.
- `README.md`: Project documentation.
- `LICENSE`: Licensing information.

## 🛠️ For Contributors

Draftbench is built using vanilla HTML, CSS, and JavaScript to keep it accessible and fast. All course content is data-driven; to add new lessons or courses, simply update the `COURSES` array in `index.html`.
