<div align="center">
  <a href="https://shahadah-studs.github.io/quranpdf/">
    <img src="./assets/quranpdf-typing.svg" alt="QuranPDF — animated typing banner" width="900">
  </a>
</div>

<h1 align="center">QuranPDF — Madani Mushaf</h1>

<p align="center">
  A calm, browser-based reader for the Madani Mushaf PDF, built with plain HTML and hosted on GitHub Pages.
</p>

<p align="center">
  <a href="https://shahadah-studs.github.io/quranpdf/">Open the reader</a> ·
  <a href="https://shahadah-studs.github.io/quranpdf/wiki.html">Read the wiki</a> ·
  <a href="https://github.com/Shahadah-studs/quranpdf/issues">Report an issue</a>
</p>

> **Live update:** The current site includes a full-screen Arabic loading experience with a gold progress bar, a dark/gold reader header, an animated `QuranPDF - Madani Mushaf` title, the embedded Madani Mushaf PDF, and a link to the browser-friendly project wiki.

## What it is

QuranPDF is a lightweight static website for reading the Madani Mushaf in a distraction-free interface. There is no framework, backend, database, build step, or package installation: the project is made from HTML, CSS, and a small amount of JavaScript.

The PDF is embedded from the Internet Archive rather than stored in this repository:

```text
https://dn760104.eu.archive.org/0/items/MadinahQuran/ar_Mushaf_AlMadinah_N_G.pdf
```

## Features

- Full-page embedded Madani Mushaf PDF reader.
- Dark interface with gold accents and Arabic branding.
- Full-screen loading screen with an animated progress bar.
- Animated heading reveal after the PDF frame loads.
- Responsive layout for desktop and mobile browsers.
- Direct link to the project wiki from the live reader.
- Zero dependencies and simple GitHub Pages deployment.
- Respectful reduced-motion guidance in the project wiki.

## Project files

```text
quranpdf/
├── index.html                 # Reader, styles, loading behavior, and PDF iframe
├── wiki.html                  # Browser-friendly project guide
├── assets/
│   └── quranpdf-typing.svg   # Infinite animated typing banner used above
└── README.md                  # Project documentation
```

## Run locally

Clone the repository and start any static web server in the project directory. Python is a convenient option:

```bash
git clone https://github.com/Shahadah-studs/quranpdf.git
cd quranpdf
python3 -m http.server 8000
```

Then open <http://localhost:8000/>. The wiki is available at <http://localhost:8000/wiki.html>.

You can also open `index.html` directly, although an HTTP server is recommended because browsers handle embedded PDFs and local files differently.

## Deploy with GitHub Pages

1. Open **Settings → Pages** in the repository.
2. Select the `main` branch as the deployment source.
3. Select the repository root (`/`) as the folder.
4. Save and wait for the deployment to finish.
5. Visit <https://shahadah-studs.github.io/quranpdf/>.

## Customize it

### Change the PDF

Update the `src` of `#quran-iframe` in `index.html`:

```html
<iframe
  id="quran-iframe"
  src="YOUR_PDF_URL"
  title="Madani Mushaf PDF viewer">
</iframe>
```

Use a stable HTTPS URL and verify that the document host permits iframe embedding and that you have permission to link to or distribute the document.

### Change the title animation

The live reader types its heading with the `.start-typing h1` animation in `index.html`. The README banner is a self-contained SVG whose typing and cursor animations repeat infinitely.

## Troubleshooting

### The PDF area is blank

Open the PDF URL directly, check the browser console, and confirm that the external host is available and allows embedding. Some privacy tools and browsers may block third-party PDF frames.

### The loader never disappears

The reader hides the loader after the iframe fires its `load` event. If the remote PDF cannot be reached, add a fallback message or a direct “Open PDF” link to `index.html`.

### GitHub Pages shows an older version

Confirm that Pages deploys from `main`, wait for deployment to complete, and hard-refresh the page or open it in a private window.

## Contributing

1. Create a branch for your change.
2. Keep the change focused and dependency-free.
3. Test the reader on current desktop and mobile browsers.
4. Verify that the PDF, loader, animations, and wiki link still work.
5. Open a pull request with a clear description and screenshots for visual changes.

Please do not commit credentials, private documents, or large generated files.

## Content and licensing note

The PDF is hosted by a third party and is not included in this repository. Before replacing, downloading, or redistributing it, review the source's copyright, license, attribution, and hosting terms. This repository currently does not include a software license.

## Links

- **Live reader:** <https://shahadah-studs.github.io/quranpdf/>
- **Project wiki:** <https://shahadah-studs.github.io/quranpdf/wiki.html>
- **Repository:** <https://github.com/Shahadah-studs/quranpdf>
