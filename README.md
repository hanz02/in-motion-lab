# crap-portfolio

> Don't let the name fool you — the code is anything but.

A personal UI/web-design playground built with **vanilla HTML, CSS, and JavaScript** — no frameworks, no build step. What started as a hobby project for practicing layout and animation grew into a small collection of design experiments, the centerpiece being a fully hand-orchestrated animated hero section.

**Live site:** [hanz02.github.io/crap-portfolio](https://hanz02.github.io/crap-portfolio/)

## Highlight: The Hero Section

The most sophisticated piece of the project. Clicking the moon button triggers a multi-stage animation sequence, ending in a night scene where classical Japanese and Chinese literary quotes hang like vertical scrolls above a cat watching the moon.

<!-- TODO: add a GIF/screenshot of the hero section here, e.g. ./assets/git-screenshots/hero.gif -->

Everything is written from scratch in modular vanilla JS (ES modules) — no animation library. Under the hood:

- **Orchestrated animation timeline** — a chained sequence of seven timed stages (curtain reveal, star burst, moon shrink, floor drop, message rain) built with the Web Animations API and custom cubic-bezier easing.
- **Generative layout** — on every visit the quotes are shuffled, given randomized font sizes, opacities, paddings, and vertical offsets, then constrained so no quote ever overlaps the floor. Each render is unique.
- **Collision detection** — the script computes bounding-box offsets of each quote relative to the cat and moon; when a quote drifts or is hovered into that zone, the cat and floor blur to keep visual depth (`get_middle_messages.js`, `cat_offset.js`).
- **Responsive behavior** — on narrow screens the quote field becomes horizontally scrollable with edge-aware scroll buttons, and the collision logic re-evaluates the "middle" quotes as you scroll.
- **Typography as design** — vertical CJK text layout mixing Japanese, Chinese, and Arabic literary quotes, with hover states that surface each quote for reading.

## Other Sections

### Grid Design — V1

Responsive image grid, desktop and mobile:

![Grid V1 desktop view](./assets/git-screenshots/grid-v1.png)

![Grid V1 mobile view](<./assets/git-screenshots/grid-v1(Mobile).png>)

### Grid Design — V2 "Complexity"

A denser, asymmetric grid layout:

![Grid V2 desktop view](./assets/git-screenshots/grid-v2.png)

![Grid V2 mobile view](<./assets/git-screenshots/grid-v2(Mobile).png>)

### V3 "Insanity" (in progress)

Layered typography and slideshow experiments — under active development.

## Built With

- **HTML5 / CSS3** — mobile-first, with a custom utility-class system (`utility.css`) written before ever touching Tailwind
- **Vanilla JavaScript (ES modules)** — all animation and layout logic hand-rolled
- **jQuery** — used sparingly for legacy path animation (`jquery.path.js`)

## Project Structure

```
├── index.html
└── assets/
    ├── css/        # per-section stylesheets + utility classes
    ├── js/         # modular hero logic (animation, collision, scrolling)
    └── img/        # SVG/GIF assets (moon, stars, cats, floor)
```

## Roadmap

More sections and refinements are added as inspiration strikes — this is a living project. Planned: hero capture for this README, further V3 sections, and general polish.

## About Me

Hi, I'm **Hanz** — I build expressive, detail-obsessed front-end experiences for fun.

- GitHub: [@hanz02](https://github.com/hanz02)
- Email: [khawhanzhe@gmail.com](mailto:khawhanzhe@gmail.com)

All artwork in the grid sections is credited to its original creators via the "GO TO SOURCE" links on the site.
