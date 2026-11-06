# Pocket — Personal Money Tracker

A mobile-first, offline-capable expense tracker built with plain HTML, CSS and JavaScript.

## What's included

- `index.html` — Pocket V4 app.
- `manifest.webmanifest` — installable Progressive Web App metadata.
- `sw.js` — service worker for offline app-shell caching.
- `assets/icons/` — icon assets generated from the icon supplied by you.
- `.github/workflows/deploy.yml` — deploys the site to GitHub Pages when you push to `main`.

The supplied wallet artwork is used for the app brand mark, browser favicon, Android/PWA launcher icons and Apple touch icon. All launcher/icon variants are derived from that same artwork.

## Publish on GitHub Pages

1. Unzip this project.
2. Create a new GitHub repository.
3. Upload **the contents inside** the unzipped `Pocket_GitHub_Project` folder to the repository root (so `index.html` is at the root, not inside another nested folder).
4. Commit and push to the `main` branch.
5. In GitHub, open **Settings → Pages**. Under Build and deployment, choose **GitHub Actions** if it is not already selected.
6. Open the **Actions** tab and wait for “Deploy Pocket to GitHub Pages” to complete.
7. Open the Pages URL shown by the workflow. Use HTTPS.

## Install on Android

1. Open the published HTTPS URL in Chrome on Android.
2. Open Chrome's menu (⋮).
3. Choose **Install app** or **Add to Home screen** (the wording depends on Chrome version).
4. Confirm. Pocket will appear on the home screen using your supplied wallet icon.

The app shell can open offline after its first successful online load. Transaction data is stored in browser local storage on that device. Export a backup from Settings before clearing browser data or changing devices.

## Important notes

- This is a PWA/web app package, not a signed APK/AAB. It can be installed from Chrome without a Play Store release.
- A standalone Android APK/AAB requires an additional Android packaging step (for example, Capacitor or a Trusted Web Activity), plus Android build/signing configuration.
- The browser may restrict a webpage from force-closing itself. Pocket's in-app back flow returns to Home and then displays an exit confirmation.
- The balance is calculated from the transactions entered into Pocket; it is not connected to a bank account.

## Local testing

Service workers require HTTPS or `localhost`. For a quick local preview, use a local static server, for example:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`.
