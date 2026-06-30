# Mash Design Studio

Official website for **Mash Design Studio** — Architecture | Interior | Design & Build.

A single-page, static marketing site for the studio: hero, vision/about, services, project portfolio (with a lightbox carousel), design process, and a contact section.

## Folder Structure

```
MashDesignStudio/
│
├── index.html              # Single-page site (all sections)
│
├── css/
│   ├── style.css            # Base styles, layout, and all components
│   ├── responsive.css        # Mobile / tablet breakpoint overrides
│   └── animations.css        # Keyframe animations (modal fade-in)
│
├── js/
│   ├── script.js             # Project data + carousel modal logic
│   ├── navigation.js         # Smooth-scroll nav link handling
│   └── animations.js         # Reserved hook for future scroll animations
│
├── images/
│   ├── logo/                 # Studio logo (nav, footer, hero badge)
│   ├── hero/                 # Hero banner image
│   ├── projects/             # Project portfolio images (incl. multi-image sets)
│   ├── icons/                 # Reserved for future iconography assets
│   └── backgrounds/           # Reserved for future background textures
│
├── favicon.ico
├── robots.txt
├── sitemap.xml
├── README.md
└── .gitignore
```

## Tech Stack

- **HTML5** — semantic markup, no framework
- **CSS3** — custom properties, CSS Grid/Flexbox, no preprocessor
- **Vanilla JavaScript** — no build step, no dependencies
- **Google Fonts** — Cormorant Garamond (display) + Inter (body)

No build tools, package manager, or bundler are required. This is a fully static site.

## Local Development

Because the site uses only static assets, you can open `index.html` directly in a browser, or serve it locally for accurate relative-path behavior:

```bash
# Python
python3 -m http.server 8000

# Node (if installed)
npx serve .
```

Then visit `http://localhost:8000`.

## Deployment

### Vercel

1. Push this folder to a GitHub repository.
2. Import the repository in [Vercel](https://vercel.com/new).
3. Framework preset: **Other** (static site).
4. Build command: *none*.
5. Output directory: `/` (root).
6. Deploy.

### GitHub Pages (alternative)

1. Push to a repository.
2. In repository **Settings → Pages**, set the source to the `main` branch, root folder.
3. Save — the site will publish at `https://<username>.github.io/<repo>/`.

## Updating Content

| To change...           | Edit...                                  |
|-------------------------|-------------------------------------------|
| Copy / text             | `index.html`                              |
| Colors, spacing, layout | `css/style.css`                           |
| Mobile layout            | `css/responsive.css`                      |
| Project portfolio items | `index.html` (`.project-card` markup) and `PROJECTS` object in `js/script.js` |
| Project images           | `images/projects/` (then update paths in `js/script.js` and `index.html`) |
| Contact details          | `index.html` (`.contact-details` block)   |

## Performance Notes

- All images are pre-optimized JPEGs/PNGs (no embedded Base64) for fast parallel loading and proper browser caching.
- Below-the-fold project images use `loading="lazy"`.
- Fonts are loaded via `<link rel="preconnect">` for faster Google Fonts handshake.
- No external JS dependencies — only three small, focused script files.

## License / Credits

© Mash Design Studio. All project imagery is proprietary to Mash Design Studio.
