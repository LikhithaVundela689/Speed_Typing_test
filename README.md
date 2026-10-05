# ⌨️ Speed Typing Test

**A lightweight, browser-based typing challenge that fetches a fresh random quote on every round and measures how fast you can type it.**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Bootstrap](https://img.shields.io/badge/Bootstrap_4-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)
![REST API](https://img.shields.io/badge/REST_API-Fetch-690cb0?style=for-the-badge)

[🚀 Live Demo](#-live-demo) · [✨ Features](#-features) · [🛠 Tech Stack](#-tech-stack) · [⚙️ Getting Started](#️-getting-started) · [🗺 Roadmap](#-roadmap)

</div>

---

## 📖 Overview

Speed Typing Test is a front-end web application built with vanilla JavaScript. On each round, the app requests a random quote from a REST API, starts a timer, and asks the user to reproduce the quote exactly. On a correct submission, the elapsed time is displayed. A reset button loads a new quote and restarts the timer.

The project was built to practise the core fundamentals of front-end development: **DOM manipulation, asynchronous programming with the Fetch API, event handling, timers, and responsive styling** without relying on a JavaScript framework.

## 🚀 Live Demo

> 🔗 **Live link:** _add your GitHub Pages / Netlify / Vercel URL here_

<!-- Add a screenshot or GIF after deployment:
![Speed Typing Test Screenshot](./assets/screenshot.png)
-->

## ✨ Features

- 🎲 **Dynamic content:** a new random quote is fetched from a REST API each round
- ⏱️ **Live timer:** a running seconds counter displayed above the typing area
- ✅ **Instant validation:** an exact-match check on submission with clear success and error messages
- 🔄 **One-click reset:** clears the input, restarts the timer, and loads a fresh quote
- ⏳ **Loading indicator:** a Bootstrap spinner is shown while a new quote is being fetched on reset
- 🎨 **Clean purple-themed UI:** gradient background, card layout, and Google Fonts typography

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| Markup | HTML5 |
| Styling | CSS3 (custom styles, gradients), Bootstrap 4.5 (utility classes, spinner) |
| Logic | Vanilla JavaScript (ES6) |
| Data | Fetch API with a remote random-quote REST endpoint |
| Fonts | Google Fonts |

## 🧠 How It Works

```
Page load ──► fetch() random quote ──► render quote ──► timer starts
                                                          │
              ┌───────────────────────────────────────────┘
              ▼
        User types in textarea
              │
        ┌─────┴──────┐
     Submit         Reset
        │             │
  Input === quote?    └─► stop timer ► show spinner ► fetch new quote
   ├─ Yes → stop timer, show time taken               ► restart timer
   └─ No  → show "incorrect sentence" message
```

## 📂 Project Structure

```
speed-typing-test/
├── index.html     # Page structure and Bootstrap includes
├── script.js      # Quote fetching, timer, submit and reset logic
├── style.css      # Theme, layout, and component styling
└── README.md
```

> **Note:** rename the source files to the names above (or update the paths in your HTML) so that the stylesheet and script are linked correctly.

## ⚙️ Getting Started

### Prerequisites

- Any modern web browser
- An active internet connection (for the quote API, Bootstrap CDN, and Google Fonts)

### Run locally

```bash
# 1. Clone the repository
git clone https://github.com/vishnusai2005/<your-repo-name>.git

# 2. Move into the project folder
cd <your-repo-name>

# 3. Open the app
#    Option A: double-click index.html
#    Option B: serve it locally
npx serve .
```

## 🎯 What I Learned

- Consuming a REST API with `fetch()` and handling the Promise chain
- Updating the DOM dynamically with `textContent` and `classList`
- Managing timers with `setInterval` / `clearInterval` and keeping UI state in sync
- Structuring event-driven logic for form submission and reset flows
- Combining Bootstrap utilities with custom CSS for a consistent design

## 🔍 Known Limitations

In the interest of transparency, the following limitations have been identified in the current version. They form the basis of the roadmap below.

| # | Area | Observation |
|---|---|---|
| 1 | Timer | The timer starts at page load rather than on the first keystroke, so reading time is included in the result. |
| 2 | Timer | Submitting before the first tick can display `null` instead of a number of seconds. |
| 3 | Reset | Rapid repeated clicks on Reset can create overlapping fetch calls and multiple intervals. |
| 4 | Error handling | There is no `.catch()` on the fetch calls. If the API is unreachable, the spinner and timer stay in an inconsistent state. |
| 5 | Loading state | The spinner is hidden by default, so it appears only after Reset and not during the initial quote load. |
| 6 | HTML | The `id="timer"` is declared twice (a `<span>` and a hidden `<p>`), which is invalid HTML. |
| 7 | Dependencies | jQuery, Popper, and Bootstrap JS are loaded but not used. Only Bootstrap CSS is required. |
| 8 | Validation | Matching is an exact string comparison with no live character feedback or accuracy score. |
| 9 | Responsiveness | The layout uses fixed `140vh` height and `vh`-based widths, which may not adapt well on small screens. |
| 10 | Availability | The app depends on a third-party quote API and image asset; if either goes offline, the app degrades. |

## 🗺 Roadmap

- [ ] Start the timer on the first keystroke
- [ ] Add `try/catch` or `.catch()` error handling with a retry message
- [ ] Debounce / disable the Reset button while a request is in flight
- [ ] Display **WPM** and **accuracy** alongside elapsed time
- [ ] Highlight correct and incorrect characters in real time
- [ ] Store a personal best in `localStorage`
- [ ] Remove unused JavaScript dependencies and fix duplicate IDs
- [ ] Improve mobile responsiveness
- [ ] Add a local fallback list of quotes for offline use

## 🤝 Contributing

Suggestions and pull requests are welcome. Please open an issue first to discuss any major change.


⭐ If you found this project useful, consider giving it a star.

</div>
