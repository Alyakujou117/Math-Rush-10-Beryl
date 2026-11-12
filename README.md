# Radical Rush — Remove Download Button + Mobile Landscape Fix

This package preserves the latest separated Radical Rush source (HTML + CSS + 35 JS files).

## Exactly what changed
- Home screen: no `rr-download-app` element. Your Download Android App button is removed.
- New `assets/css/07-mobile-landscape-only.css` is loaded at the end of `index.html`.
- The new stylesheet applies ONLY to touch-screen landscape gameplay at widths 761–1100px and heights up to 600px. It fixes the collapsed zero-height game area, gives the board usable square tiles, and lets the map and sidebar scroll independently.
- Existing desktop and mobile portrait rules and ALL JavaScript were left unchanged.

## Update your existing GitHub Pages repository (minimal method)
1. In your GitHub repository `Math-rush`, open `index.html` and delete the single download-button `<a class="rr-download-app"> ... </a>` element and its optional `<!-- DOWNLOAD ANDROID APP -->` comment.
2. Add this line AFTER your other CSS stylesheet links (near `</body>` works):

   `<link rel="stylesheet" href="assets/css/07-mobile-landscape-only.css">`

3. Upload ONLY `assets/css/07-mobile-landscape-only.css` to the matching folder in GitHub.
4. Commit and refresh your GitHub Pages website. Test mobile landscape and portrait.

## Alternative: overwrite with supplied files
Upload the files from the *Changed Files Only* ZIP, keeping their folder paths. This replaces `index.html` with the latest packaged version (without the download button), and includes CSS files `06-setup-and-turn.css` and `07-mobile-landscape-only.css`. If you manually edited `index.html` further after receiving our last source ZIP, first compare those edits before overwriting.

The **Complete Game ZIP** can be used for a full replacement if you prefer.

## Checks
- Browser rendering: Chrome emulation at 844x390 and 932x430 landscape now shows 100 board tiles, full-height game and independent board/sidebar scrolling.
- Rotation: 844x390 -> 390x844 -> 844x390 restores portrait and landscape dimensions.
- CSS patch match: NOT applied at 390x844 portrait or 1365x768 desktop.
- All 35 JavaScript files: `node --check` passed.
- Browser runtime: no reported JS exceptions in tested start/game flows.
- This is browser emulation, not a physical-phone or APK test.

Your APK is not changed; a standalone APK with bundled files must be rebuilt to include future website updates.
