# SEO Peek (Manifest V3 Edition)

This is the actively maintained fork of SEO Peek, stewarded by **Titus Roby K**.
The original Manifest V2 extension by Sander Heilbron has been closed, so this
repository keeps the project alive, modernizes it for Manifest V3, and adds a
few refinements along the way.

## Overview

SEO Peek gives you a quick, focused look at the on-page SEO signals of whatever
tab you are viewing—without opening DevTools or digging through page source.
The extension inspects the live DOM, so it works with both server-rendered and
client-rendered (SPA) pages.

### Highlights

- Manifest V3 compliant background service worker and scripting pipeline.
- Snapshot of key content signals: page title, meta description, heading 1,
  canonical and pagination directives, robot directives, HTTP headers, and more.
- **New in this fork:** Open Graph (OG) tag coverage (title, description, image)
  presented alongside traditional meta tags.
- User-configurable display preferences (toggle keywords, pagination,
  mobile, and international sections) stored with `chrome.storage.sync`.

## Install Locally

1. Clone or download this repository.
2. In Chrome (or any Chromium browser), open `chrome://extensions`.
3. Enable *Developer mode* (toggle in the top-right corner).
4. Choose *Load unpacked* and select the project’s `src` directory.
5. Pin the “SEO Peek” action from the extensions toolbar if you want quick access.

The extension uses only static assets, so there is no build step—changes inside
`src/` are picked up immediately after a reload from the extensions page.

## Usage

1. Browse to any page you want to inspect.
2. Click the SEO Peek toolbar button to launch the popup.
3. Review the sections to spot missing or duplicate metadata, check
   canonicalization, review robot directives, and verify the newly added OG tags.

If the page exposes Open Graph data, you will see the extracted content and
links; otherwise the popup clearly marks the fields as **Not available**.

## Options

Open the extension’s options page to toggle visibility of:

- Meta Keywords
- Pagination directives
- Mobile directives (AMP, alternate media, vary header)
- International directives (rel-alternate-hreflang)

Your selections sync across Chrome profiles where the same Google account is
signed in.

## Development Notes

- Background logic now runs as a Manifest V3 service worker (`js/background.js`).
- Content script injection uses the MV3 `chrome.scripting` API.
- Open Graph data is parsed in `js/script.js` and surfaced in `js/popup.js`.
- Hot reload is as simple as running *Reload* on the extension card in
  `chrome://extensions` after editing files.

## Contributing

Bug reports and pull requests are welcome. Please open an issue first if you are
planning a larger enhancement, especially anything that touches the Manifest V3
architecture or the OG tag feature set.

## Credits

- Original concept and implementation: **Sander Heilbron** (archived project).
- Continued maintenance, Manifest V3 migration, and OG enhancements:
  **Titus Roby K**.

Licensed under the MIT License.