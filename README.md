# Communication Theory Primer (Jekyll + GitHub Pages)

This repository contains a Jekyll-powered website scaffold for introducing broad audiences to communication theory and modern communication problems involving AI.

## What is included

- Home page (`/`)
- Six required analysis pages:
  - `/transmission-view/`
  - `/meaning-culture/`
  - `/power-interpretation/`
  - `/intention-interpretation/`
  - `/reader-guidance/`
  - `/how-this-site-was-built/`
- Shared layout in `_layouts/default.html`
- Professional color palette and accessible styling in `assets/css/style.css`
- `assets/images/` folder for your images
- GitHub Actions workflow to build on every push to `main`

## Local development

1. Install Ruby (3.2+ recommended).
2. Install dependencies:
   ```bash
   bundle install
   ```
3. Serve locally:
   ```bash
   bundle exec jekyll serve
   ```
4. Open `http://127.0.0.1:4000/comm-primer-best-/`.

## Build configuration for GitHub Pages

The Jekyll config file already includes:

- `url: https://abbyduffer12.github.io`
- `baseurl: /comm-primer-best-`

If your username or repository name changes, update those values in `_config.yml`.

## How to add/edit content

- Edit each page file directly (`*.md`) and replace placeholder text with your own writing.
- Use Markdown headings (`##`, `###`) to keep each page readable.
- Add links with `[label](url)`.
- Add images to `assets/images/`, then reference them like:
  ```md
  ![Descriptive alt text]({{ '/assets/images/your-image-name.png' | relative_url }})
  ```

## Accessibility notes

The layout includes:

- A keyboard skip link
- ARIA labels on header/navigation/main/footer landmarks
- High-contrast, professional color choices
- Responsive navigation for smaller screens

When adding content, keep accessibility strong by using meaningful heading order and descriptive alt text for every image.

## CSS customization

Theme colors are centralized in CSS variables near the top of `assets/css/style.css`:

```css
:root {
  --bg: #f4f6fb;
  --surface: #ffffff;
  --text: #0f172a;
  --muted: #334155;
  --accent: #0a4a7a;
  --accent-hover: #083b62;
  --border: #cbd5e1;
}
```

Adjust these values to reskin the site while preserving readability and contrast.

## Automation

The workflow file `.github/workflows/jekyll-build.yml` builds the site on each commit to `main`:

1. Checks out the code
2. Sets up Ruby + Bundler cache
3. Runs `bundle exec jekyll build`
