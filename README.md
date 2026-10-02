# Pixar Animation Studios: Responsive Web Page (Debug Battle)

> A responsive clone of the Pixar Animation Studios landing page, built with plain HTML and CSS.

This project came from **Debug Battle**, a challenge by Not Your College (Sheryians Coding School, Beyond Sigma batch). I did not build the page from scratch. I was handed a complete codebase with hidden bugs and an expected-output recording. My job was to find each bug, fix it in the right place, and make the page work properly from desktop down to small mobile screens.

🔗 **Live demo:** [Click here to view the live project](https://jidanwaresi.github.io/debugbattle1/)

---

## 📌 The Challenge

- Start from an existing HTML and CSS codebase that contains deliberate and accidental bugs.
- Match the page to a screen recording of the expected output at multiple screen widths.
- Keep the existing code intact. Fix problems at their source and write only what the responsive layout needs.
- Deploy the final page before the deadline.

<br>

## 🏗️ What the Page Contains

- **Fixed header** with blur effect, navigation and a mobile menu icon.
- **Hero section** with a full-width background image.
- **About section** (image and text side by side).
- **"Coming Soon" carousel** with a hover-expand effect.
- **Careers section** with a sticky reveal on scroll.
- **Gallery** in a custom grid layout.
- **News card grid**.
- **Multi-column footer** with a newsletter field.

<br>

## 📱 Responsive Behaviour

| Screen width | What changes |
| :--- | :--- |
| **Above 1024px** | Full desktop layout, 3-column gallery grid, 4-column news grid. |
| **Up to 1024px** | Tighter header spacing, careers content in one column, gallery becomes a single column. |
| **Up to 900px** | Navigation collapses into the menu icon, About section stacks, careers header centres, news moves to 2 columns, footer reflows. |
| **Up to 640px** | Carousel shows one film at a time, gallery becomes a swipeable horizontal strip with scroll snapping, news in 1 column, footer centred. |
| **Up to 400px** | Smaller buttons and tighter letter spacing for narrow phones. |

<br>

## 🐞 Bugs Found and Fixed

| Problem | Cause | Fix |
| :--- | :--- | :--- |
| **Gallery responsive rule had no effect** | Selector written as `#gallery-item`, but the HTML uses `class="gallery-item"`. | Changed to a class selector (`.gallery-item`). |
| **Careers title not centring on tablet** | Selector written as `.careers-title`, but the element has `id="careers-title"`. | Changed to an ID selector (`#careers-title`). |
| **Desktop layout changed unexpectedly** | A "tablet" media query was written with `min-width` instead of `max-width`. | Changed to `max-width: 1024px`. |
| **Navigation and carousel rules never applied** | Responsive rules were sitting inside a CSS comment block. | Moved them out of the comment into the right breakpoint. |
| **Gallery images were squeezed on smaller screens** | Fixed `height: 750px` on the grid, with `overflow: hidden`. | Reset to `height: auto` inside the media query. |
| **Rule not winning over base styles** | Lower specificity than the earlier `nth-child` rules. | Scoped it as `#gallery-grid .gallery-item:nth-child(n)`. |

<br>

## 🧠 What I Learned

- **Debugging is mostly reading:** I lost time at the start by changing things in the wrong direction. Reading both files line by line, in order, found more bugs than guessing did.
- **A property that does nothing usually has a reason:** Either the selector never matched, another rule overrides it, or a different property is interfering.
- **Specificity matters more than order:** An ID selector beats a class selector, and a long selector beats a short one.
- **Check against expected result at every breakpoint:** Not just at the widths where the page already looks right.
- **New to me in practice:** `position: sticky` with `z-index` for layered scroll effects, `aspect-ratio`, and `scroll-snap-type` for swipeable galleries.

<br>

## 💻 Tech Stack

- **HTML5**
- **CSS3** (Flexbox, CSS Grid, media queries, `clamp()`, pseudo-elements, transitions)
- **Typography:** Montserrat (via Google Fonts)
- **Tools:** Chrome DevTools (device mode, Styles and Computed panels) for debugging
- **References:** MDN Web Docs and W3Schools

<br>

## 📂 Project Structure

```text
.
├── index.html
├── styles.css
└── README.md
```

<br>

## 🚀 Run Locally

```bash
git clone https://github.com/Jidanwaresi/debugbattle1.git
cd debugbattle1
```

Open `index.html` in a browser, or serve it with the Live Server extension in VS Code. To test the layout, open DevTools, switch to device mode, and resize between desktop and mobile widths.

<br>

## ⚠️ Scope and Limitations

- The project is HTML and CSS only. The menu icon and carousel arrows are visual elements and are not wired to JavaScript.
- Images are loaded from external URLs, so they depend on those sources staying available.

<br>

## 🏆 Credits

- Challenge by **Not Your College** and **Sheryians Coding School** (Beyond Sigma)
- Design reference: Pixar Animation Studios
- This is an educational project and is not affiliated with Pixar, Disney or any of their partners. All film artwork and trademarks belong to their respective owners.

<br>

## 👨‍💻 Author

**Jidan Waresi**

Computer Science student, focusing on Full Stack development.

LinkedIn: [Jidan Waresi](https://www.linkedin.com/in/jidan-waresi-a63298430)
