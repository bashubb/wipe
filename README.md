# Wipe website

Static site for `https://bashubb.com/wipe/` (privacy policy and support for App Store Connect, plus a placeholder home page). Publish the `docs/` folder of the GitHub repository `bashubb/wipe` with GitHub Pages (Settings → Pages → main, /docs); the account's custom domain serves it under `/wipe/`.

```sh
python3 -m http.server 8766 --bind 127.0.0.1 --directory docs
```

App source: `../../utility factory/Wipe - remove metaData from photos/`.

Next: once the App Store listing exists, run the `app-store-seo-landing-page` skill for keyword research, a full landing page and guides; add the App Store link and `apple-itunes-app` meta.
