# Transparent Intelligent Infrastructures and Systems (TIIS) Consortium Website

The TIIS Consortium website is a modular, data-driven static website. Its content follows the 13-slide **TIIS Consortium – Introduction** presentation. The visual system uses an academic-association portal layout inspired by the information architecture of IAPR: institutional utility bar, primary navigation, editorial homepage, conference highlights, news feed and structured institutional footer. The design is original to TIIS.

## Website sections

1. Home — consortium identity and Why TIIS.
2. About TIIS — Our Vision, Mission and Objectives.
3. Research — the five Research Pillars and their shared foundation.
4. Governance — governance structure, Working Groups, General Assembly, General Chair and Advisory Board.
5. How It Works — the five-step collaboration cycle.
6. Network — interactive map and profiles of connected universities.
7. Events & Roadmap — EIDT, SIMC, conference roles and the 2025–2029 roadmap.
8. Membership — four membership categories and six member benefits.
9. Join TIIS — the three-step membership process and Secretariat contact.

## Project structure

```text
.
├── index.html
├── README.md
└── assets/
    ├── css/site.css
    ├── data/
    │   ├── site.json
    │   ├── announcements.json
    │   ├── network.json
    │   └── stories.json
    ├── images/
    │   └── placeholders/
    │       └── tiis-event-placeholder.svg
    ├── js/
    │   ├── app.js
    │   └── tailwind.config.js
    └── pages/
        ├── home.html
        ├── about.html
        ├── research.html
        ├── governance.html
        ├── how-it-works.html
        ├── network.html
        ├── news.html
        ├── membership.html
        └── join.html
```

## Architecture

- `index.html`: application shell, shared navigation, footer, and page mount point.
- `assets/pages/`: eight page partials corresponding to the website sections above.
- `assets/css/site.css`: responsive styles, article layouts, network map, and page presentation.
- `assets/js/app.js`: page loading, navigation, story rendering, article routes, and interactive institution profiles.
- `assets/data/site.json`: site metadata and navigation configuration.
- `assets/data/network.json`: institution names, locations, profiles, official websites, and social links for the interactive map.
- `assets/data/stories.json`: news and event stories.
- Leaflet 1.9.4 and OpenStreetMap provide the interactive network map.

## Managing news and event stories

Edit `assets/data/stories.json` to publish or update stories. Each story has a unique `id`, title, category, date label, excerpt, cover image, and a `sections` array.

Supported article section types: `paragraph`, `heading`, `image`, and `quote`.

## Local preview

Page templates and JSON files are loaded with `fetch()`; use a local HTTP server:

```bash
python3 -m http.server 8000
```

Open `http://localhost:8000` in your browser.

## Deployment

Publish the repository root with `index.html` and the complete `assets/` directory. No build step or server-side runtime is required.

## Website forms

The Join TIIS page links to the Membership Expression of Interest and General Inquiry Google Forms. Responses are managed in Google Forms; the website does not use a custom server-side form handler or Apps Script bridge.
