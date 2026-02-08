# replit.md

## Overview

This is a personal portfolio website for Abhishek Singh, based on the "vCard" personal portfolio template originally by codewithsadee. It's a static, single-page website built with plain HTML, CSS, and JavaScript — no frameworks, no build tools, no backend. The site features a sidebar with personal info, and sections for About, Resume, Portfolio, Blog, and Contact. It's fully responsive and designed to work across all device sizes.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Project Structure
The entire project lives inside `Singh_PortFolio/Singh-PortFolio/`. This is a purely static site with no build step or server-side logic.

```
Singh_PortFolio/Singh-PortFolio/
├── index.html          # Single-page entry point with all content
├── index.txt           # Text content reference/copy for the site
├── assets/
│   ├── css/
│   │   └── style.css   # All styles in one file, uses CSS custom properties
│   ├── js/
│   │   └── script.js   # Vanilla JS for interactivity (sidebar toggle, modals, etc.)
│   └── images/         # Static image assets (avatar, icons, favicon)
```

### Frontend Architecture
- **No framework**: Pure HTML, CSS, and JavaScript. No React, no Vue, no bundler.
- **Single HTML file**: All page sections (About, Resume, Portfolio, Blog, Contact) are in one `index.html` file. Navigation between sections is handled client-side via JavaScript toggling visibility.
- **CSS Custom Properties**: The stylesheet uses CSS variables (custom properties) extensively for theming — colors, gradients, borders. The color scheme appears to use a light theme with blue accent tones.
- **Google Fonts**: Uses the "Poppins" font family loaded from Google Fonts CDN.
- **Vanilla JavaScript**: Handles sidebar toggle on mobile, testimonials modal popups, and page navigation. Uses `data-*` attributes for DOM selection rather than classes or IDs.
- **Responsive Design**: Designed to be responsive across desktop and mobile viewports.

### Design Patterns
- **Data attribute selectors**: JavaScript interacts with the DOM using `data-*` attributes (e.g., `data-sidebar`, `data-sidebar-btn`, `data-modal-container`), keeping JS logic decoupled from CSS class names.
- **Toggle pattern**: A reusable `elementToggleFunc` adds/removes an "active" class to show/hide elements like the sidebar and modals.

### No Backend
There is no server, no API, no database. This is a static site that can be served from any web server or static hosting platform. To run it, simply serve the files or open `index.html` in a browser.

### How to Serve Locally
Since this is a static site, a simple HTTP server is sufficient:
```bash
cd Singh_PortFolio/Singh-PortFolio
python -m http.server 5000
```
Or use any static file server. The entry point is `index.html`.

## External Dependencies

- **Google Fonts (Poppins)**: Loaded via CDN link in the HTML head. No local font files.
- **No npm packages**: There is no `package.json` or dependency management. Everything is vanilla.
- **No database**: All content is hardcoded in HTML.
- **No third-party JavaScript libraries**: No jQuery, no animation libraries — just plain JS.
- **No APIs**: No external API calls. The contact form (if present) would need a backend or third-party form service to actually function.