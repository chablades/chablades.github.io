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
the order on the page: featured projects first, then newest to oldest by
start date.

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

## Checklist: things only Nicolas can add

Search `index.html` for `TODO` to find each spot in the code.

**Files to add to the repo root**

- [ ] `photo.jpg`: square profile photo, at least 400×400. Also used as the
      preview image when the site is shared.
- [ ] `resume.pdf`: both Resume links point here and return 404 until it exists.

**MapleDoro**

- [ ] Screenshot: save as `images/mapledoro.png` (1280×720) and set
      `image.src` to `"images/mapledoro.png"`.

**Chaebot**

- [ ] Merge the `desktop-app` and `ccr-3db4040f-1v8qlj` branches into `main`
      in the chaebot repo, so GitHub shows the desktop app and the features the
      page describes.
- [ ] Once cooldowns, timed messages and the YouTube listener are merged, move
      them out of the "in progress" bullet.
- [ ] Optional: a screenshot of the desktop app.

**Palcraft**

- [ ] Live site URL: fill in the empty `Live site` link.
- [ ] Confirm the start date (Jul 2026, taken from the first commit).
- [ ] Optional: a screenshot of the calculator or crafting tree.

**Multi-Agent AI Orchestrator**

- [ ] Start date: replace `"In progress"` with e.g. `"Sep 2026 – Present"`,
      then move the project to its place in the date order.
- [ ] Tech stack: fill in `stack`.
- [ ] GitHub URL: there's no repo for it yet. Either add one or leave the
      link empty (it stays hidden).

**ShiftSync**

- [ ] Confirm the GitHub link. It points to `chablades/shiftsync`; switch it if
      the team repo `TAndronaco/CS4800-Worker-Schedule-Project` is the one to show.

**Going live**

- [ ] Merge this branch into `main`. GitHub Pages only publishes `main`.
- [ ] Optional: the Contact line still says "Open to software engineering and
      IT roles". Update it if it should match the longer list in the intro.
