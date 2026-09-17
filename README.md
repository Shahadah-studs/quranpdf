# QuranPDF — Madani Mushaf

QuranPDF is a focused, browser-based Quran reader that presents the Madani Mushaf PDF in a clean, dark interface. The project is intentionally lightweight: the page is built with plain HTML, CSS, and JavaScript, while the Quran PDF is displayed through an embedded viewer.

**Live site:** https://shahadah-studs.github.io/quranpdf/

**Repository:** https://github.com/Shahadah-studs/quranpdf

## Features

- Full-page PDF reading experience for the Madani Mushaf.
- Dark interface designed to reduce visual distraction while reading.
- Gold accent color and subtle animations for a calm, polished presentation.
- Loading screen shown while the embedded PDF viewer initializes.
- Animated project title and PDF panel entrance after the viewer loads.
- Responsive layout that adapts to desktop and mobile browser sizes.
- No build step, package manager, framework, or server-side code required.

## How it works

The application currently consists of `index.html`. The page:

1. Displays a loading screen while the embedded document begins loading.
2. Loads the Quran PDF from the Internet Archive inside an `<iframe>`.
3. Waits for the iframe `load` event.
4. Hides the loading screen and starts the title animation.
5. Reveals the PDF container after the title animation begins.

The current PDF source is:

`https://dn760104.eu.archive.org/0/items/MadinahQuran/ar_Mushaf_AlMadinah_N_G.pdf`

Because the PDF is hosted externally, the reader depends on that service remaining available and allowing browser embedding. If the PDF host changes, update the iframe `src` in `index.html`.

## Repository structure

```text
quranpdf/
├── index.html   # Main reader page, inline styles, and loading behavior
├── README.md    # Project documentation
└── wiki.html    # Detailed, browser-accessible project wiki
```

## Running locally

No installation is required for a basic preview.

### Option 1: Open the file directly

Download or clone the repository and open `index.html` in a modern browser. Some browser PDF and iframe behaviors can differ when files are opened with the `file://` protocol, so a local server is recommended for reliable testing.

### Option 2: Use a local HTTP server

With Python installed:

```bash
python3 -m http.server 8000
```

Then visit:

http://localhost:8000/

You can also use any static server, such as the VS Code Live Server extension or another local development server.

## Deployment with GitHub Pages

The repository is configured as a static HTML project and can be published with GitHub Pages:

1. Open the repository **Settings** tab.
2. Select **Pages** in the sidebar.
3. Choose the `main` branch as the deployment source.
4. Select the repository root (`/`) as the folder.
5. Save the configuration and wait for the Pages deployment to finish.
6. Open the published URL shown by GitHub.

Every push to the configured source branch can trigger a new Pages deployment.

## Customizing the reader

### Change the title

Edit the heading in `index.html`:

```html
<h1>QuranPDF - Madani Mushaf</h1>
```

If the title length changes significantly, review the typing animation timing and `steps(...)` value in the CSS.

### Change the PDF

Replace the iframe source:

```html
<iframe
  id="quran-iframe"
  src="YOUR_PDF_URL"
  title="Madani Mushaf PDF viewer">
</iframe>
```

Use a stable HTTPS URL. Confirm that the host permits the PDF to be displayed in an iframe and that you have permission to link to or distribute the document.

### Adjust the visual style

The page styles are currently inside `index.html`. Common customization points include:

- `body` for the overall background and typography.
- `header` for the top navigation area.
- `.pdf-container` for reader size, spacing, and shadows.
- `.loader-spinner` and `.loader-text` for the loading state.
- `#d4af37` for the gold accent color.
- The media-query section you add for additional mobile refinements.

## Accessibility and usability notes

- Keep meaningful `title` text on the iframe so assistive technology can identify the embedded document.
- Maintain sufficient color contrast when changing the dark theme or gold accent.
- Respect users who prefer reduced motion by considering a `prefers-reduced-motion` media query for the animations.
- Keep a direct PDF link available if a browser or privacy extension blocks iframe embedding.
- Test keyboard navigation and zoom behavior on both desktop and mobile devices.

## Troubleshooting

### The PDF does not appear

Check your network connection, confirm that the external PDF URL is still valid, and inspect the browser developer console for iframe or content-security errors. Try opening the PDF URL directly in a new tab.

### The loading screen never disappears

The loading screen is removed when the iframe emits its `load` event. If the external host blocks embedding or fails to respond, the event may not behave as expected. Consider adding a fallback link or a timeout message for production use.

### The layout is too tall or too short

The reader height is calculated from the viewport. Adjust the `height` value on `.pdf-container` and test with browser toolbars, small screens, and device rotation.

### GitHub Pages shows an old version

Confirm that the latest commit reached the branch configured in **Settings → Pages**, then wait for the deployment to complete. Hard-refresh the browser or open the site in a private window to bypass cached assets.

## Contributing

1. Fork the repository or create a working branch.
2. Make a focused change.
3. Test the page in a current desktop and mobile browser.
4. Verify that the PDF still loads and that the loading state behaves sensibly.
5. Open a pull request with a clear description and screenshots when the visual design changes.

Please avoid committing large generated files, private documents, credentials, or unrelated changes.

## Content and hosting note

This project embeds a document hosted by a third party. The repository does not currently contain a local copy of the PDF. Review the source's licensing, attribution, availability, and redistribution terms before changing the document source or adding downloaded files to the repository.

## License

No license file is currently included in this repository. Until a license is added, assume that the code is not granted for reuse beyond the permissions provided by applicable law. Add a license file if you want to define terms for copying, modification, and distribution.

## Project wiki

For a visual, browser-friendly guide to the project, open [`wiki.html`](./wiki.html) or visit:

https://shahadah-studs.github.io/quranpdf/wiki.html
