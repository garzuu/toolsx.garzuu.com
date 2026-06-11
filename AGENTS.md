# Repository Guidelines

## Project Structure & Module Organization

This repository is a static marketing/support site for ToolsX. Pages live at the repository root:

- `index.html` is the landing page.
- `assistenza.html` and `privacy.html` are support and privacy pages.
- `style.css` contains shared visual styling for all pages.
- `i18n.js` contains Italian and English translation strings plus locale switching.
- `icon.png`, `favicon.png`, and `apple-touch-icon.png` are site assets.
- `.github/ISSUE_TEMPLATE/` contains GitHub issue template configuration.

Keep new pages at the root unless the site grows enough to justify folders. Reuse the shared navigation, footer, and `data-i18n` translation pattern.

## Build, Test, and Development Commands

There is no package manager or build step. Work directly with the static files.

- `python3 -m http.server 8000` starts a local static server from the repo root.
- `open http://localhost:8000` opens the local site in a browser.
- `git status --short` checks pending changes before committing.

Avoid adding tooling unless it solves a concrete maintenance problem.

## Coding Style & Naming Conventions

Use two-space indentation in HTML, CSS, and JavaScript, matching the existing files. Prefer semantic HTML, shared CSS classes, and concise vanilla JavaScript. Keep filenames lowercase and descriptive, for example `privacy.html`.

For localized text, add a `data-i18n` key in the HTML and matching entries under both `it` and `en` in `i18n.js`. Keep translation keys grouped by page or feature, such as `support.faq.q1`.

## Testing Guidelines

No automated test suite exists. Before opening a pull request, manually verify pages through a local server. Check:

- Navigation links between `index.html`, `assistenza.html`, and `privacy.html`.
- Language toggle behavior and persistence.
- Mobile and desktop responsive layout.
- Asset loading for icons and favicons.

## Commit & Pull Request Guidelines

Recent commits use Conventional Commit style, for example `feat(site): landing, assistenza e privacy policy per ToolsX`. Use the pattern `type(scope): summary`, with types such as `feat`, `fix`, `docs`, or `chore`.

Pull requests should include a short description, list of changed pages/assets, manual test notes, and screenshots for visible UI changes. Link related GitHub issues when applicable.

## Security & Configuration Tips

Do not add analytics, trackers, or third-party scripts without updating the privacy page. Keep `CNAME` unchanged unless the deployment domain changes.
