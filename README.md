# CETPrep — Smart Practice Platform

> A lightweight, browser-based mock test platform designed for focused exam preparation, custom question sets, and performance tracking.

CETPrep is a frontend-first exam preparation application that allows users to create custom mock tests from JSON question data, attempt tests, review performance, and manage multiple practice sessions.

The project is intentionally built with standard web technologies to keep it lightweight, fast, and easy to run.

---

## Features

### Mock Test Creation

Create custom mock tests using structured JSON question data.

- Enter a custom test name
- Select a test category
- Paste question data directly as JSON
- Upload JSON question files
- Validate and load question sets
- Create reusable mock tests

### Custom JSON Question Format

Questions can contain:

- Questions
- Multiple-choice options
- Correct answers
- Explanations
- Paragraph-based data
- Embedded visual data

Supported embedded visual formats include:

```text
[BARGAPH]
[LINEGRAPH]
[PIEGRAPH]
[TABLE]
```

This allows question data to contain both standard questions and data-interpretation content.

---

### Practice Tests

Take previously created tests with an exam-style interface.

The platform is designed around:

- Multiple-choice questions
- Question navigation
- Test progress
- Independent attempts
- Result calculation
- Detailed explanations

---

### My Tests

Manage previously created mock tests from one place.

Each test can display information such as:

- Test name
- Category
- Best score
- Number of attempts
- Number of questions

Available actions include:

- Attempt
- View history
- Delete

---

### Performance Tracking

Track performance across test attempts.

The platform can display:

- Average score
- Best score
- Improvement
- Number of tests taken
- Attempt history

This provides a quick overview of preparation progress.

---

### Test Categories

Tests can be organized into different preparation categories, including:

- Verbal Ability
- Logical Reasoning
- Quants
- Miscellaneous

The category system is designed to make large collections of tests easier to manage.

---

### Multiple Attempts

A test can be attempted multiple times.

Each attempt can be treated as an independent practice session, allowing users to:

- Retake tests
- Compare previous performance
- Improve scores
- Review previous attempts

---

### Detailed History

Previous test attempts can be reviewed to understand performance over time.

The history system is intended to make it easier to identify:

- Previous scores
- Best performance
- Attempt frequency
- Areas requiring improvement

---

### Dark / Light Mode

CETPrep supports both dark and light themes.

The interface is designed around a modern dark-first visual system with:

- Deep navy backgrounds
- Purple accent colors
- Subtle borders
- Elevated cards
- Responsive layouts
- Accessible contrast

---

## Tech Stack

CETPrep is intentionally lightweight.

### Frontend

- HTML5
- CSS3
- Vanilla JavaScript

### Data

- JSON

### External Assets

The interface uses SVG-based icons where required.

No frontend framework is required.

There is no dependency on:

- React
- Next.js
- Vue
- Angular
- Tailwind CSS
- Node.js build tooling

The application can run directly in a modern browser.

---

## Project Structure

```text
cet-mock-test-platform/
│
├── favicon.ico
│
├── index.html
├── index.css
│
├── test.html
├── test.css
│
├── README.md
│
└── ...
```

### `index.html`

Contains the main application interface, including:

- Dashboard
- Test creation
- My Tests
- Navigation
- Theme controls
- Performance sections

### `index.css`

Contains the styling for the main application interface.

This includes:

- Layout
- Sidebar
- Dashboard
- Cards
- Buttons
- Forms
- Theme styling
- Responsive behavior

### `test.html`

Contains the mock-test/practice interface.

### `test.css`

Contains styling specific to the test-taking experience.

### `favicon.ico`

Application favicon used by the browser.

---

## Running the Project

CETPrep is a static frontend project, so no build process is required.

### Option 1 — Open Directly

Clone the repository:

```bash
git clone https://github.com/p3anv/cet-mock-app-v2.git
```

Enter the project directory:

```bash
cd cet-mock-app-v2
```

Then open:

```text
index.html
```

in a modern browser.

---

### Option 2 — Use VS Code Live Server

If you are using Visual Studio Code, install the **Live Server** extension.

Then:

1. Open the project folder.
2. Open `index.html`.
3. Right-click the file.
4. Select **Open with Live Server**.

The application will then be available through a local development URL.

---

## JSON Question Format

A basic question can be represented using the following structure:

```json
[
  {
    "paragraph": "[BARGRAPH]\nSales in 2024\nProduct A: 120\nProduct B: 85\nProduct C: 200\nProduct D: 45",
    "question": "Which product had the highest sales?",
    "options": [
      "A",
      "B",
      "C",
      "D"
    ],
    "correct": 2,
    "explanation": "Product C had the highest sales at 200 units."
  }
]
```

### Question Fields

| Field | Description |
|---|---|
| `paragraph` | Optional supporting passage or data |
| `question` | Question text |
| `options` | Available answer choices |
| `correct` | Index of the correct option |
| `explanation` | Explanation shown during review |

The exact JSON structure should match the parser expected by the application.

---

## Supported Data Visualizations

Question paragraphs can contain visualization markers.

```text
[BARGAPH]
```

```text
[LINEGRAPH]
```

```text
[PIEGRAPH]
```

```text
[TABLE]
```

These markers allow the application to interpret structured data inside question content.

---

## Application Flow

```text
                    ┌─────────────────┐
                    │     Dashboard   │
                    └────────┬────────┘
                             │
              ┌──────────────┴──────────────┐
              │                             │
              ▼                             ▼
      ┌─────────────────┐          ┌─────────────────┐
      │   Create Test   │          │    My Tests     │
      └────────┬────────┘          └────────┬────────┘
               │                            │
               ▼                            ▼
      ┌─────────────────┐          ┌─────────────────┐
      │   JSON Questions│          │ Existing Tests  │
      └────────┬────────┘          └────────┬────────┘
               │                            │
               └──────────────┬─────────────┘
                              ▼
                    ┌─────────────────┐
                    │   Take Test     │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │     Results     │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │ History / Stats │
                    └─────────────────┘
```

---

## Design Philosophy

CETPrep follows a modern EdTech interface approach.

### Visual Principles

- Minimal visual clutter
- Strong information hierarchy
- Clear navigation
- Consistent spacing
- Rounded UI components
- Subtle borders
- Purple accent system
- Dark-first interface
- Responsive layouts

### UX Principles

The interface prioritizes:

1. Fast navigation
2. Clear actions
3. Minimal distractions during tests
4. Easy test creation
5. Quick performance feedback
6. Simple test management

---

## Browser Support

CETPrep is designed for modern browsers supporting standard HTML, CSS, and JavaScript features.

Recommended browsers:

- Google Chrome
- Mozilla Firefox
- Microsoft Edge
- Safari

---

## Development

Since CETPrep uses vanilla HTML, CSS, and JavaScript, development is intentionally straightforward.

There is no package installation or compilation step required for the current frontend.

Changes can be made directly to:

```text
index.html
index.css
test.html
test.css
```

and immediately tested in the browser.

---

## Future Improvements

Potential future improvements include:

- Persistent cloud storage
- User authentication
- Server-side test storage
- More advanced analytics
- Question bookmarking
- Weak-topic detection
- Timed mock tests
- Automatic performance recommendations
- Question search and filtering
- Import/export of test collections
- Progressive Web App support
- Offline test access
- More visualization types
- Mobile-specific optimizations

---

## Project Status

**Active Development**

The core frontend experience is being developed around a lightweight architecture with a focus on usability, performance, and maintainability.

---

## Contributing

Contributions are welcome.

### Suggested workflow

1. Fork the repository.
2. Create a feature branch.

```bash
git checkout -b feature/your-feature
```

3. Make your changes.
4. Test the application in a browser.
5. Commit your changes.

```bash
git commit -m "Add your feature"
```

6. Push the branch.

```bash
git push origin feature/your-feature
```

7. Open a Pull Request.

---

## License

This project is currently distributed under the license specified in the repository.

If a license has not yet been selected, add one before publishing the project for public use.

---

## Author

**Pranav Kamble**

Built as a lightweight exam-preparation and mock-test platform.


## CETPrep

**Practice smarter. Track progress. Improve consistently.**
