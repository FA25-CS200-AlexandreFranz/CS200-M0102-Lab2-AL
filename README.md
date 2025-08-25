# CS 200 — Module 01–02 Lab 2: Structured Webpage

A simple, valid HTML5 page (`index.html`) that introduces the author with **About Me**, **My Interests**, a skills **Aside**, a short **Fun Fact** **Article**, a **Favorite Quote**, and a **Figure** with caption. The page uses an **animated drift GIF** background with a dark overlay for readability. No external libraries or frameworks.

---

## Files

```
structured_webpage/
├─ index.html   # single-page site with inline CSS
└─ README.md    # this file
```
> (Optional) If you serve a local GIF, create an `assets/` folder and place the file there, e.g., `assets/drift.gif`.

---

## What’s Inside `index.html`

- **Head metadata**
  - `<!DOCTYPE html>` and a single `<html lang="en">`
  - `<meta charset="UTF-8">`, `<meta name="viewport" content="width=device-width, initial-scale=1">`
  - Exactly one `<title>`: **ME**
- **Semantic structure**
  - `<main>` containing:
    - **Welcome (Section)**: one top-level `<h1>` and two links  
      - Internal: `#about-me`  
      - External: `https://www.vividracing.com` (`target="_blank"` + `rel="noopener noreferrer"`)
    - **About Me (Section)**: short bio focused on cars, anime, and gaming
    - **My Interests (Section)**: list of interests
    - **Skills (Aside)**: labeled with `aria-labelledby`
    - **Fun Fact (Article)**: short personal story
    - **Favorite Quote (Aside)**: quote in a `<blockquote>`
    - **Figure**: animated image with descriptive `alt` + `<figcaption>`
  - **Footer**: contact line with `mailto:alexandre@example.com`

---

## Animated Background (Inline CSS)

Defined in the `<head>` inside a `<style>` block. Current GIF is an AE86 drift:

```css
body{
  margin:0;
  min-height:100vh;
  background-image:
    linear-gradient(rgba(0,0,0,.55), rgba(0,0,0,.55)),
    url("https://media1.tenor.com/m/V5h6bDx7qJIAAAAd/ae86-trueno.gif");
  background-size: cover, cover;
  background-position: center, center;
  background-repeat: no-repeat, no-repeat;
  background-attachment: fixed, fixed;
  color:#f1f1f1;
  font-family: system-ui, Arial, sans-serif;
}

/* Translucent “cards” for content */
main{ max-width:900px; margin:0 auto; padding:1rem; }
section, article, aside, figure, footer{
  background: rgba(0,0,0,.30);
  backdrop-filter: blur(2px);
  border-radius: 12px;
  padding: 1rem;
  margin: 1rem 0;
}

/* Accessibility: reduced motion fallback */
@media (prefers-reduced-motion: reduce){
  body{
    background-image: linear-gradient(#111, #111);
    background-attachment: scroll;
  }
}
```

**Change the GIF:** replace the URL above. For a local file, save to `assets/drift.gif` and use:
```css
url("assets/drift.gif")
```

**Mobile tip:** if scrolling stutters on some devices, change:
```css
background-attachment: fixed, fixed;
```
to:
```css
background-attachment: scroll, scroll;
```

---

## How to Run

- Just open `index.html` in any modern browser.
- *(Optional)* Serve locally:
  - **Python 3:** `python -m http.server 8000` → visit `http://localhost:8000`

---

## Accessibility & Validation Checklist

- [x] One `<html lang="en">` (no duplicates)
- [x] `<head>` has **exactly one** `<title>`
- [x] Properly nested/closed elements (`section`, `article`, `aside`, `figure`, `footer`)
- [x] Only one top-level `<h1>`
- [x] Descriptive `alt` on images
- [x] External links opened in a new tab include `rel="noopener noreferrer"`
- [x] Provides a reduced-motion fallback for animated background

---

## Notes

- The content is intentionally simple and self-contained for the lab.
- Optional copy edits you can apply later: change `Im` → `I’m`, `Imm` → `I’m`, and “Hands on” → “Hands-on”.

---

## Author

**Alexandre Franz Pries Junior** (listed in the header comment of `index.html`).
