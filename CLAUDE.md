# Project notes

Single-page static site (`index.html`) served by GitHub Pages from `main` at
html-player.5moreminutes.games. Cloudflare redirects several alternate names to it.

## Standing feature: tap-the-version update check

Every project that shows a version number should have this behavior:

- The version number is visible somewhere on the page (here: bottom right).
- Clicking or tapping it checks whether a newer version is live:
  - Newest version already: flash the version label white and green.
  - Newer version available: reload the page.
- Keep it simple. No service workers or background polling. A plain `fetch` of the
  page itself with `cache: 'no-store'`, comparing the version text, is enough.
  If a real check isn't practical for a project, tapping the version can just
  refresh the page.

**When starting work on any project that has no version number or no update check,
ask the user whether they want this feature added.** Don't add it without asking.

## Conventions

- Bump the version number (the `#ver` span in `index.html`) with every user-visible change.
- Push to `main` to publish; Pages republishes within a minute or two.
