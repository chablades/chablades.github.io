# chablades.github.io

Personal portfolio site for Nicolas Tran, served by GitHub Pages at
**https://chablades.github.io/**.

It's a single static page with no build step, framework or dependencies.
All markup, styles and scripts live in [`index.html`](index.html).

## Structure

| Section    | Where it's defined                                            |
| ---------- | ------------------------------------------------------------- |
| Intro      | `<section class="hero">` in `index.html`                      |
| Projects   | The `PROJECTS` array in the `<script>` at the bottom of the file |
| Experience | `<ol class="timeline">`, one `<li class="job">` per role       |
| Skills     | `<dl class="skills">`, one `<div class="skill-group">` per group |
| Contact    | `<footer class="site-footer">`                                |

Colors, fonts and spacing are CSS custom properties on `:root` at the top of
the `<style>` block.

## Editing projects

Projects are rendered from the `PROJECTS` array. Their order in the array is
the order on the page.

```js
{
  title: "Project name",            // required
  subtitle: "Short tagline",        // optional, shown in gray after the title
  when: "Jan 2026 – Present",       // optional: dates, status or course code
  featured: true,                   // optional, adds a "Featured" label
  stack: ["TypeScript", "Next.js"], // optional tech tags
  image: { src: "images/app.png", alt: "Describe the screenshot" }, // optional, shown at 16:9
  points: ["What it does", "..."],  // required, 1–3 short lines
  links: [{ label: "GitHub", url: "https://github.com/..." }] // optional
}
```

A link with an empty `url`, or an image with an empty `src` or a missing file,
is hidden, so placeholders are safe to leave in
until the real file or URL is ready. Put screenshots in an `images/` folder;
1280×720 PNG or JPG works well.

## Images

| File          | Used for                                                    |
| ------------- | ----------------------------------------------------------- |
| `photo.jpg`   | Profile photo in the intro, and the preview image when the site is shared on LinkedIn, Slack, etc. Square, at least 400×400. Until it exists, an "NT" monogram shows instead. |
| `images/*.png`| Optional project screenshots (see `image` above).           |

## Previewing locally

Open `index.html` directly in a browser, or serve the folder:

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploying

Push to the branch GitHub Pages publishes from (normally `main`). The site
updates within a minute or two.

## To do

- [ ] Add `resume.pdf` to the repo root. The Resume links already point to it
      and return 404 until it exists.
- [ ] Fill in the empty project links (the `// TODO` entries in `PROJECTS`).
- [ ] Add the tech stack for Multi-Agent AI Orchestrator.
- [ ] Add `photo.jpg` (square profile photo) to the repo root.
- [ ] Add a MapleDoro screenshot and set its `image.src`.
