1| <div align="center">
2|   <a href="https://shahadah-studs.github.io/quranpdf/">
3|     <img src="./assets/quranpdf-typing.svg" alt="QuranPDF — animated typing banner" width="900">
4|   </a>
5| </div>
6| 
7| <h1 align="center">QuranPDF — Madani Mushaf</h1>
8| 
9| <p align="center">
10|   A calm, browser-based reader for the Madani Mushaf PDF, built with plain HTML and hosted on GitHub Pages.
11| </p>
12| 
13| <p align="center">
14|   <a href="https://shahadah-studs.github.io/quranpdf/">Open the reader</a> ·
15|   <a href="https://shahadah-studs.github.io/quranpdf/wiki.html">Read the wiki</a> ·
16|   <a href="https://github.com/Shahadah-studs/quranpdf/issues">Report an issue</a>
17| </p>
18| 
19| > **Live update:** The current site includes a full-screen Arabic loading experience with a gold progress bar, a dark/gold reader header, an animated `QuranPDF - Madani Mushaf` title, the embedded PDF, and a quiet, distraction-free reading layout.
20| 
21| ## What it is
22| 
23| QuranPDF is a lightweight static website for reading the Madani Mushaf in a distraction-free interface. There is no framework, backend, database, build step, or package installation: the project is designed to stay simple and easy to host on GitHub Pages.
24| 
25| The PDF is embedded from the Internet Archive rather than stored in this repository:
26| 
27| ```text
28| https://dn760104.eu.archive.org/0/items/MadinahQuran/ar_Mushaf_AlMadinah_N_G.pdf
29| ```
30| 
31| ## Features
32| 
33| - Full-page embedded Madani Mushaf PDF reader.
34| - Dark interface with gold accents and Arabic branding.
| 35| - Full-screen loading screen with an animated progress bar.
| 36| - Animated heading reveal after the PDF frame loads.
| 37| - Responsive layout for desktop and mobile browsers.
| 38| - Direct link to the project wiki from the live reader.
| 39| - Zero dependencies and simple GitHub Pages deployment.
| 40| - Respectful reduced-motion guidance in the project wiki.
| 41| 
| 42| ## Project files
| 43| 
| 44| ```text
| 45| quranpdf/
| 46| ├── index.html                 # Reader, styles, loading behavior, and PDF iframe
| 47| ├── wiki.html                  # Browser-friendly project guide
| 48| ├── assets/
| 49| │   └── quranpdf-typing.svg   # Infinite animated typing banner used above
| 50| └── README.md                  # Project documentation
| 51| ```
| 52| 
| 53| ## Run locally
| 54| 
| 55| Clone the repository and start any static web server in the project directory. Python is a convenient option:
| 56| 
| 57| ```bash
| 58| git clone https://github.com/Shahadah-studs/quranpdf.git
| 59| cd quranpdf
| 60| python3 -m http.server 8000
| 61| ```
| 62| 
| 63| Then open <http://localhost:8000/>. The wiki is available at <http://localhost:8000/wiki.html>.
| 64| 
| 65| You can also open `index.html` directly, although an HTTP server is recommended because browsers handle embedded PDFs and local files differently.
| 66| 
| 67| ## Deploy with GitHub Pages
| 68| 
| 69| 1. Open **Settings → Pages** in the repository.
| 70| 2. Select the `main` branch as the deployment source.
| 71| 3. Select the repository root (`/`) as the folder.
| 72| 4. Save and wait for the deployment to finish.
| 73| 5. Visit <https://shahadah-studs.github.io/quranpdf/>.
| 74| 
| 75| ## Customize it
| 76| 
| 77| ### Change the PDF
| 78| 
| 79| Update the `src` of `#quran-iframe` in `index.html`:
| 80| 
| 81| ```html
| 82| <iframe
| 83|   id="quran-iframe"
| 84|   src="YOUR_PDF_URL"
| 85|   title="Madani Mushaf PDF viewer">
| 86| </iframe>
| 87| ```
| 88| 
| 89| Use a stable HTTPS URL and verify that the document host permits iframe embedding and that you have permission to link to or distribute the document.
| 90| 
| 91| ### Change the title animation
| 92| 
| 93| The live reader types its heading with the `.start-typing h1` animation in `index.html`. The README banner uses the `assets/quranpdf-typing.svg` SVG file, where the `QuranPDF` name types in place with a looping cursor animation.
| 94| 
| 95| ## Troubleshooting
| 96| 
| 97| ### The PDF area is blank
| 98| 
| 99| Open the PDF URL directly, check the browser console, and confirm that the external host is available and allows embedding. Some privacy tools and browsers may block third-party PDF frames.
| 100| 
| 101| ### The loader never disappears
| 102| 
| 103| The reader hides the loader after the iframe fires its `load` event. If the remote PDF cannot be reached, add a fallback message or a direct “Open PDF” link to `index.html`.
| 104| 
| 105| ### GitHub Pages shows an older version
| 106| 
| 107| Confirm that Pages deploys from `main`, wait for deployment to complete, and hard-refresh the page or open it in a private window.
| 108| 
| 109| ## Contributing
| 110| 
| 111| 1. Create a branch for your change.
| 112| 2. Keep the change focused and dependency-free.
| 113| 3. Test the reader on current desktop and mobile browsers.
| 114| 4. Verify that the PDF, loader, animations, and wiki link still work.
| 115| 5. Open a pull request with a clear description and screenshots for visual changes.
| 116| 
| 117| Please do not commit credentials, private documents, or large generated files.
| 118| 
| 119| ## Content and licensing note
| 120| 
| 121| The PDF is hosted by a third party and is not included in this repository. Before replacing, downloading, or redistributing it, review the source's copyright, license, attribution, and hosting terms.
| 122| 
| 123| ## Links
| 124| 
| 125| - **Live reader:** <https://shahadah-studs.github.io/quranpdf/>
| 126| - **Project wiki:** <https://shahadah-studs.github.io/quranpdf/wiki.html>
| 127| - **Repository:** <https://github.com/Shahadah-studs/quranpdf>
| 128| 