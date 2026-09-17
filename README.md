# Digital Clock — Real-Time JavaScript Clock

A minimal, real-time digital clock built with HTML5, CSS3, and vanilla JavaScript. This is a **Day 4** practice project focused on the JavaScript `Date` object, `setInterval`, and dynamic DOM text updates — no frameworks, no libraries.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![No Dependencies](https://img.shields.io/badge/Dependencies-None-success)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## 📸 Screenshot

![Digital Clock Screenshot](https://github.com/user-attachments/assets/3d277132-520f-4871-b5d3-0ffbba4f2a95)

## 📖 Overview

A live digital clock centered on the page, displaying hours, minutes, and seconds in `HH:MM:SS` format. The clock updates every second using `setInterval`, pulling the current time from JavaScript's built-in `Date` object. Styled with a diagonal gradient background and the `Orbitron` Google Font for a futuristic, LED-display look.

## ✨ Features

- 🕐 Live-updating clock (hours, minutes, seconds)
- 🎨 Diagonal gradient background (`linear-gradient`)
- 🔤 Custom typography using Google Fonts (`Orbitron`)
- 🧊 Frosted-glass style clock card (`rgba` background + `border-radius`)
- ⚡ Zero dependencies — pure HTML/CSS/JS, no build step

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Markup | HTML5 |
| Styling | CSS3 (Flexbox, `linear-gradient`) |
| Logic | Vanilla JavaScript (`Date` API, `setInterval`) |
| Fonts | Google Fonts — Orbitron, Poppins |
| Dependencies | None |

## 📁 Project Structure

```
digital-clock-day4/
├── index.html      # Clock markup — hrs/min/sec spans
├── style.css       # Centering, gradient background, clock styling
└── script.js       # updateClock() — reads Date, updates DOM every second
```

## 🔍 How It Works

### `index.html`
A single `.clock` container with three `<span>` elements (`#hrs`, `#min`, `#sec`) separated by colons. JavaScript fills in the actual time values on load and on each interval tick.

### `script.js`

```javascript
function updateClock() {
  let hrs = document.getElementById("hrs");
  let min = document.getElementById("min");
  let sec = document.getElementById("sec");

  const time = new Date();

  hrs.innerHTML =
    time.getHours() < 10 ? "0" + time.getHours() : time.getHours();
  min.innerHTML =
    time.getMinutes() < 10 ? "0" + time.getMinutes() : time.getMinutes();
  sec.innerHTML =
    time.getSeconds() < 10 ? "0" + time.getSeconds() : time.getSeconds();
}

updateClock();

setInterval(() => {
  updateClock();
}, 1000);
```

- `new Date()` grabs the current local time on each call
- `getHours()`, `getMinutes()`, `getSeconds()` extract each unit
- A ternary check pads single-digit values with a leading zero (`"0" + value`) so the display always shows two digits (e.g. `05` instead of `5`)
- `updateClock()` runs once immediately on page load, then every 1000ms (1 second) via `setInterval`, keeping the clock in sync with real time

### `style.css`
- `body` uses Flexbox to center the `.clock` both vertically and horizontally
- Background uses a 333° diagonal `linear-gradient` across pink → purple → dark blue
- `.clock` uses a semi-transparent `rgba(230, 230, 250, 0.2)` background with rounded corners for a frosted-glass effect
- `font-family: "Orbitron"` gives the digits a digital/LED aesthetic

## 🚀 Getting Started

No package manager, no build step — just open the file.

```bash
git clone https://github.com/your-username/digital-clock-day4.git
cd digital-clock-day4
```

Then open `index.html` directly in your browser.

## 🎯 What This Project Practices

- The JavaScript `Date` object and its getter methods
- `setInterval()` for repeating timed logic
- Conditional (ternary) logic for zero-padding numbers
- Updating the DOM via `innerHTML` on a timer
- CSS gradients and Flexbox centering

## 🐛 Known Issue

- `index.html` is missing the closing `>` on the opening `<body` tag — browsers are lenient and will still render it correctly, but it should be fixed to `<body>` for valid, standards-compliant HTML.

## 🧠 Possible Improvements

- Add a 12-hour/24-hour toggle with AM/PM display
- Add a date display alongside the time
- Add a dark/light theme toggle
- Animate digit transitions (e.g. flip-clock style) instead of instant text swaps
- Add timezone selection

## 🤝 Contributing

This is a beginner practice project, but suggestions and pull requests are welcome.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

**Topics:** `javascript` `html5` `css3` `digital-clock` `vanilla-javascript` `date-api` `frontend` `beginner-project` `web-development` `real-time`
