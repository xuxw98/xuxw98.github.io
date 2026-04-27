# Repository Notes for Codex

This is Xiuwei Xu's personal homepage, served as a static GitHub Pages site from the repository root. There is no build step or package manager; edit HTML/CSS/assets directly.

## Main Pages

- `index.html`: main landing page. It contains the profile intro, news, selected preprints, and selected publications.
- `pubs.html`: full publications page. Its profile header and paper-entry markup largely mirror `index.html`, but it includes a longer publication list.
- `projects.html`: research projects page. It uses embedded local videos from `videos/` plus small inline JavaScript carousels.

The visible navigation bar is duplicated inline in the three main pages. If changing nav labels, links, or styling, update all three files consistently.

## Asset Layout

- `images/`: thumbnails, GIFs, profile photo, and favicon used by the main pages.
- `videos/`: MP4/MOV videos used by `projects.html`.
- `files/`: PDFs such as CV, papers, supplementary material, and posters.
- `DSPDet3D/`, `Online3D/`, `ESAM/`: standalone project pages with their own `index.html`, local CSS, and `img/` assets.
- `stylesheet.css`: shared stylesheet for the three main pages.
- `google15c5e277c915f8f8.html` and `BingSiteAuth.xml`: search engine verification files; do not remove casually.

## Editing Conventions

- Keep the site static and dependency-free unless explicitly asked to modernize it.
- Preserve the existing table-based layout and inline style pattern for small content updates.
- Use relative paths for local assets, for example `images/Foo.png`, `videos/Foo.mp4`, and `files/Foo.pdf`.
- Paper entries are hand-written HTML blocks. When adding a paper, copy an existing `<table>...</table>` paper block and update title, authors, venue, links, thumbnail, and description.
- Author markers currently use `*` for equal contribution and `<sup>†</sup>` for project leader.
- Several pages duplicate profile text and footer metadata. If updating biography, contact links, or "Last updated", check all three main pages.

## Typical Updates

When adding a new publication:

1. Add the thumbnail/GIF to `images/`.
2. Add any local PDFs to `files/`.
3. Add or update the publication block in `pubs.html`.
4. If it should be highlighted on the homepage, add or update the corresponding block in `index.html`.
5. Update `index.html` news if there is an acceptance or release announcement.
6. Update the footer `Last updated` date on touched pages.

When adding a new research project:

1. Add local demo videos to `videos/` if the project page uses local media.
2. Add or update the project section in `projects.html`.
3. Use unique carousel IDs and function names if copying an existing video carousel.
4. Add a standalone project folder only when the project needs its own detailed page.

## Local Preview

Most pages can be opened directly in a browser. For a local HTTP preview from the repository root:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000/`.

## Deployment

The remote is expected to be `https://github.com/xuxw98/xuxw98.github.io`. GitHub Pages serves the committed root files after pushing to the default branch.
