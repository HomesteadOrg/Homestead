# Changelog

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [Unreleased]

### Added

- Jest testing framework with unit tests for `slugify`, `formatDate`, `extractPreview`, and `loadConfig`
- Babel config (`babel.config.js`) to allow Jest to transform ESM dependencies
- Test fixtures: sample `homestead.yaml` and markdown post for isolated test runs
- CI workflow (`.github/workflows/ci.yml`) — runs tests and build on every push and pull request to `main`

### Changed

- `config.js` validation errors now throw instead of calling `process.exit`, allowing tests to catch them
- `build.js` helper functions (`slugify`, `formatDate`, `extractPreview`, `fontVars`) are now exported for testing
- `build.js` build execution is now guarded with `require.main === module` so importing the file doesn't trigger a build

## [0.5.0] - 2026-04-07

### Added

- `gallery` section type — display images and YouTube videos in a grid. Images copy to `dist/gallery/` at build time and open in a full-screen lightbox. YouTube items show a thumbnail (no iframe/tracking) and open in a new tab on click.

## [0.4.0] - 2026-04-07

### Added

- `max_posts` option on blog and portfolio sections — limits how many posts appear on the index page, full post pages are still built for all posts
- `show_preview` option on blog sections — set to `false` to hide the excerpt snippet on cards, defaults to `true`
- Text labels in links sections — add `- text: "Label"` anywhere in a links list to group and separate buttons with a small heading
- Portfolio posts now open in a modal overlay instead of navigating to a separate page — close with the X button, clicking outside, or Escape

## [0.2.0] - 2026-03-26

### Added

- Three functional layouts, "links" for only links, "portfolio" for many small posts, "blog" for full sized posts to click into
- Updated documentation to show new changes and showcase avatar placement as well

## [0.3.0] - 2026-04-02

### Added

- Created modular rows you can add any number of sections to as you want
- Each row has a width modifier, and the sections in them can be a custom share of the width
    - Small + one links section is like the LinkTree setup

## [0.1.0] - 2026-03-19

### Added

- Initial build script, reads `homestead.yaml` and outputs static HTML to `dist/`
- Handlebars templates for the main page and individual post pages
- Markdown blog post support with YAML frontmatter (`title`, `date`, `excerpt`)
- Post preview cards on the index page with excerpt and date
- Theme customization via config: background, surface, accent, text, font, radius, border
- Google Fonts integration: load any font by name or fall back to system stack
- Bundled inline SVG icons: github, twitter, instagram, linkedin, youtube, twitch, discord, bluesky, email, globe, rss
- Avatar support: copies image to `dist/` for self-contained output
