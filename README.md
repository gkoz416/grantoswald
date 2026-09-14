# Portfolio site

Plain HTML/CSS/JS — no build step, no framework. Open any `.html` file
in a browser to preview it locally, no server needed.

## File map

```
index.html                     Homepage
projects/fsae.html             FSAE wing design project page
projects/class-projects.html   Class projects placeholder page
css/style.css                  All styling (one file, organized in sections)
js/main.js                     Site JS (currently minimal — grows as you learn)
```

## Things to fill in first

- `index.html` — the "Academic snapshot" section has placeholder text
  in *italics* (school, program, year, GPA, coursework). Search for
  `placeholder` in that file to find each one.
- `projects/fsae.html` — the "Gallery" section has three placeholder
  boxes for CAD renders/photos. Replace a `<div class="placeholder-media">`
  block with a real `<img src="..." alt="...">` once you have images
  to add (see below).
- Footer GitHub link on the homepage — point it at your actual profile.

## Adding real images

1. Drop image files into the `images/` folder.
2. Replace a placeholder block like this:
   ```html
   <div class="placeholder-media"><span><strong>CAD render</strong>Front wing assembly</span></div>
   ```
   with:
   ```html
   <img src="../images/front-wing.png" alt="Front wing CAD render">
   ```
   (use `images/...` instead of `../images/...` on the homepage, since
   it's one folder closer to the images folder).

## Adding a new project page

1. Copy `projects/fsae.html` to `projects/your-project.html` as a
   starting template, and edit its content.
2. Add a new row to the "parts list" on the homepage (`index.html`,
   under `<div class="parts-list">`), copying one of the existing
   `<a class="part">` blocks and pointing its `href` at your new page.
3. Add a link to the new page in the `<nav class="site-nav">` block
   at the top of every page (there's one copy per HTML file).

## Embedding the aero map / cross-section viewer later

In `projects/fsae.html`, look for the two sections with
`<!-- AERO MAP EMBED PLACEHOLDER -->` and
`<!-- CROSS-SECTION SLIDESHOW PLACEHOLDER -->` in the HTML comments.
Replace the `placeholder-media` div inside each with your embed
(an `<iframe>`, a `<canvas>`-based viewer, or a small JS widget in
`js/main.js`) when those pieces are ready.

## Deploying with GitHub Pages

1. Create a new GitHub repository (e.g. `yourname.github.io` for a
   root-level site, or any name for a project site).
2. Push this folder's contents to that repo:
   ```
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
   git push -u origin main
   ```
3. In the repo on GitHub: **Settings → Pages → Source → Deploy from a
   branch**, pick `main` and `/ (root)`, save.
4. Your site will be live at `https://YOUR-USERNAME.github.io/YOUR-REPO/`
   (or `https://YOUR-USERNAME.github.io/` if you used the root-level
   repo name) within a minute or two.

No build step is needed — GitHub Pages serves the HTML/CSS/JS as-is.
