# Fernbrook Coffee — Landing Page (Bootstrap 5)

A single-file landing page for **Fernbrook Coffee**, a fictional small-batch café. Built with **Bootstrap 5** and plain custom CSS — no Tailwind, no Sass, no build step. Open the HTML file in a browser and it just works.

## Live demo

Open `fernbrook-coffee.html` directly in any modern browser. Bootstrap's CSS and JS bundle are loaded from a CDN (`jsdelivr`), so there's nothing to install.

## What's inside

- **Sticky nav** with a mobile hamburger menu (Bootstrap's built-in `navbar-collapse` component)
- **Hero section** — headline, copy, two CTA buttons, and a real photo (via `<img>`, sourced from Unsplash)
- **Stats strip** — hours, sourcing, and founding year in a 3-column row
- **Menu grid** — three items (espresso, pour over, bakery) using Bootstrap's card component
- **Pull-quote block** — a founder quote on a dark background
- **Hours & location** — a simple list layout
- **Contact form** — name, email, and message fields with a working submit-confirmation state (front-end only, no backend)
- **Footer**

## Why Bootstrap here

This build uses **Bootstrap 5 alone** — no other CSS framework mixed in — restyled with custom CSS variables so it doesn't read as a default Bootstrap template:

| Bootstrap feature | Used for |
|---|---|
| Grid system (`row` / `col-*`) | Hero layout, stats strip, menu cards, hours/contact two-column layout |
| `navbar` + `navbar-collapse` | Responsive nav that collapses into a hamburger menu on mobile |
| `card` | Menu item layout |
| Utility classes (`d-flex`, `gap-*`, `justify-content-*`, etc.) | Spacing and alignment throughout |
| `alert` | The contact form's success confirmation message |
| Bootstrap Bundle JS | Powers the mobile nav toggle (via `data-bs-toggle="collapse"`) |

On top of Bootstrap's defaults, a custom CSS block at the top of the `<style>` tag overrides colors, fonts, and component styling — buttons, cards, and form inputs are all reskinned with a warm cream/rust/bark palette rather than Bootstrap's default blue.

## Interactivity

A small vanilla JavaScript snippet handles:
- Preventing the default form submission
- Hiding the form and revealing a confirmation message on submit

Bootstrap's own JS bundle (loaded via CDN) handles:
- The mobile nav hamburger toggle

## Customizing

### Colors and fonts
Defined as CSS custom properties near the top of the `<style>` block:

```css
:root {
  --cream: #FBF4E9;
  --bark: #3E2C23;
  --bark-soft: #6B5648;
  --rust: #C1622D;
  --sage: #7C8B6F;
  --line: #E7DCC9;
}
```

Change these to re-theme the whole page. Headings use `Fraunces` (serif); body text uses `Nunito Sans`.

### Menu items
Each menu card lives inside `<section id="menu">` — duplicate a `.col-md-4` block and edit the badge label, title, description, size, and price to add or change items.

### Hero image
The hero photo is a standard `<img>` tag inside `.hero-photo`. Swap the `src` attribute for a different image — the container uses `object-fit: cover` inside a fixed 4:5 aspect ratio, so most images will crop cleanly regardless of their original dimensions.

### Hours
Edit the `<ul>` list inside the "Hours & location" column under `<section id="visit">`.

## File structure

```
fernbrook-coffee.html   → markup, styles, and script all in one file
README.md               → this file
```

## Known limitations

- The contact form is front-end only — it doesn't send anywhere. Wire the `<form id="contactForm">` up to a real backend or form service (e.g. Formspree, Netlify Forms) for production use.
- No page routing — this is a single scrolling page with anchor links (`#menu`, `#about`, `#visit`), not a multi-page site.
- The hero image is a real photo pulled from Unsplash; swap it for a licensed image of your own café before using this commercially.
