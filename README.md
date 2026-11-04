# Wipe website

Static site for `https://bashubb.com/wipe/`: the landing page (3D scroll story, two ways to clean, Share Sheet, hand-over to the app, presets, pricing, FAQ), the privacy policy and support for App Store Connect. Publish the `docs/` folder of the GitHub repository `bashubb/wipe` with GitHub Pages (Settings → Pages → main, /docs); the account's custom domain serves it under `/wipe/`.

```sh
python3 -m http.server 8766 --bind 127.0.0.1 --directory docs
```

Look: the app's own Ink & Marker palette (paper `#f3f1ec`, ink `#141413`, marker `#e4ff3a` behind dark text, signal `#c2361b`), in `docs/assets/wipe.css`. The shared system is `landing.css` / `landing.js` (copies of the `bashubb-app-sites` skill, do not edit here).

App source: `../../utility factory/Wipe - remove metaData from photos/`.

## Refreshing the screens, the film and the card
- **Phones** (`docs/assets/media/iphone-*.webp`): capture the screens with `Design/v2/capture.sh` (en, light) in the app repo, and the Photos Share Sheet with `WipeUITests/ShareSheetScreenshotTests` (`TEST_RUNNER_WIPE_SHARE_SHOT=<dir>`); flatten each into the iPhone bezel with the skill's `scripts/fronts.py` (bezel: `AppStore/Screenshots/bezels/`). Never publish the bezel alone.
- **Film** (`wipe-motion.mp4`, `wipe-motion-tall.mp4` and posters): rendered by `AppStore/Motion/motion.py` in the app repo, formats `search` (3:2) and `reel` (9:16), `WIPE_MOTION_READY=<fresh Ready screenshot>`; then `ffmpeg` to 1440 × 960 and 720 × 1280, 30 fps, no audio.
- **Link card** (`social-preview.jpg`, 1200 × 630): composed from the Quick Clean phone and the headline.
- **Icons**: `scripts/favicons.py` from `Wipe/Resources/Assets.xcassets/AppIcon.appiconset/WipeAppIcon-1024.png`.
- **Audits** (skill scripts, `NODE_PATH` with `playwright`): `fit-audit.js wipe` → "ALL SCENES FIT", `phone-audit.js wipe` → "ALL PHONE LAYOUTS FIT".
