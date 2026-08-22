# Just View the SVG, Please

A minimal, offline SVG viewer contained in a single HTML file. Paste SVG source, open or drop an `.svg` file, inspect the result in a sandboxed preview, pan and zoom, tidy the source, and export the image again as SVG, PNG, or WebP. [Run the app in your browser.](https://inventwithpython.com/justviewthesvgplease/just-view-the-svg-please.html)

Generated and human-reviewed by [Al Sweigart](https://inventwithpython.com/). This app works offline and you own it forever. No ads. No registration. No subscriptions. No trackers. Just right-click and save the `.html` page.

![Just View the SVG, Please](just-the-svg-please-og-preview.png)

Current version: **v0.3.2**

## Features

- Runs entirely from a single `just-view-the-svg-please.html` file.
- Works offline with no third-party JavaScript packages or runtime dependencies.
- Automatically renders SVG text as you edit it.
- Opens SVG files with the file picker.
- Accepts drag-and-drop SVG files.
- Displays source line numbers.
- Tidies/pretty-prints SVG markup.
- Uses a sandboxed preview without script permission.
- Supports click-and-drag panning.
- Supports zoom buttons, editable zoom percentage, mouse-wheel zoom, and Fit.
- Uses an always-visible checkerboard preview background for transparency.
- Exports SVG, PNG, and WebP locally in the browser.
- Follows the browser/OS light or dark color scheme.
- Includes an About dialog and clipboard Share button.
- Stores no document data in `localStorage` or IndexedDB.
- Starts with the Ghostscript Tiger SVG as a sample image.
- Includes 40 UI translations and automatically selects a matching browser language when available.
- Supports RTL layout for Arabic, Persian, Hebrew, and Urdu.
- Includes embedded favicon, metadata, Open Graph tags, and offline-safe assets.

## Use

No installation or build step is required.

1. Download `just-view-the-svg-please.html`.
2. Open it in a modern browser.
3. Paste SVG markup into the source editor, click **Open SVG**, or drag an SVG file onto the page.
4. Pan or zoom the preview as needed.
5. Use the SVG, PNG, or WebP download buttons to export the image.

You can also host the HTML file on any static web server. The application does not require a backend.

## Security model

SVG can contain active content, so the preview is deliberately isolated.

The rendered SVG is displayed in a sandboxed iframe that is not granted script execution permission. The app also applies a restrictive Content Security Policy to the preview document as defense in depth. The surrounding application makes no network requests during normal operation.

The viewer is intended for inspecting SVG files more safely than inserting arbitrary SVG markup directly into the main page. As with any browser-based file viewer, keep your browser up to date when opening untrusted files.

## Localization

The app currently includes these languages:

English, Simplified Chinese, Spanish, Arabic, Indonesian, Portuguese, French, Japanese, Russian, German, Hindi, Bengali, Urdu, Korean, Vietnamese, Turkish, Italian, Dutch, Polish, Thai, Persian, Ukrainian, Czech, Malay, Romanian, Greek, Hebrew, Swedish, Filipino, Tamil, Hungarian, Danish, Finnish, Norwegian Bokmål, Slovak, Bulgarian, Serbian, Croatian, Slovenian, and Catalan.

The language selector is generated from the keys present in the `TRANSLATIONS` object. To make a smaller custom build, delete unwanted language entries from that object; the dropdown will automatically contain only the remaining languages.

The source marks the editable translation section with:

```js
/**************************************************************************
 * TO REDUCE FILE SIZE, DELETE ALL THE LANGUAGES YOU DON'T WANT SUPPORTED.
 **************************************************************************/
const TRANSLATIONS = {
  // ...
};

// DO NOT DELETE CODE BELOW THIS LINE.
```

English is the fallback locale when the browser language is unavailable or unsupported.

## Project files

```text
just-view-the-svg-please.html       Complete offline application
just-the-svg-please-og-preview.png  Open Graph / repository preview image
README.md                           Project documentation
```

## Development

There is no compilation, bundling, package installation, or dependency-management step. Edit the HTML file directly and reload it in a browser.

The application intentionally keeps HTML, CSS, JavaScript, translations, icons, and the default SVG sample together so the finished app remains easy to copy, download, archive, and share.

When changing the version, update the single `APP_VERSION` constant in the HTML source. The displayed version is derived from that value.

## Browser compatibility

The app is designed for current desktop and mobile browsers with standard support for:

- SVG
- `iframe` sandboxing
- Canvas image export
- Blob/Object URLs
- File APIs
- Clipboard API, with browser-dependent availability
- Pointer and wheel events

No browser extension or server-side component is required.

## Default sample attribution

The bundled starting image is the **Ghostscript Tiger SVG**, derived from the Ghostscript examples.

Source: <https://commons.wikimedia.org/wiki/File:Ghostscript_Tiger.svg>

The embedded sample is identified in the application source as licensed under the **GNU Affero General Public License v3.0 or later**.

