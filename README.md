# A Life — GitHub Pages deployment

This is a fresh, ready-to-host static build of the game, rebuilt from your
latest `life-sim.jsx`. No build step needed — GitHub just serves these
files as-is.

## ⚠️ Before you upload: bring over your icons

This bundle was rebuilt from your game code only — **your 4 icon image
files aren't included here.** You already have working copies in your
existing repo. Copy these 4 files over into a new `icons/` folder here,
keeping the exact names:

- `icons/favicon-64.png`
- `icons/icon-192.png`
- `icons/icon-512.png`
- `icons/icon-512-maskable.png`

If you'd rather I double-check them, just re-upload the 4 image files and
I'll confirm they match what `manifest.json` and `sw.js` expect.

## Steps

1. **Create a new repository** on GitHub (public repos get free Pages
   hosting). Any name is fine.
2. **Upload every file in this folder**, plus your `icons/` folder from
   step above:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `storage-polyfill.js`
   - `life-sim.bundle.js`
   - `icons/` (4 files, see warning above)

   Easiest way: repo page → **Add file → Upload files**, drag in everything
   (including the `icons` folder), commit.
3. **Turn on Pages**: repo → **Settings → Pages** → under "Build and
   deployment", set **Source: Deploy from a branch**, branch **main**,
   folder **/ (root)** → **Save**.
4. GitHub will give you a URL after a minute or two:
   `https://<your-username>.github.io/<repo-name>/`
5. Open that link on your phone in **Chrome** → ⋮ menu → **"Install app"**.

## What's inside

- **`life-sim.bundle.js`** — your `life-sim.jsx`, bundled together with
  React into one self-contained file. Verified with a headless render test
  before packaging — it mounts and renders the character creation screen
  with no runtime errors.
- **`storage-polyfill.js`** — unchanged. Provides `window.storage` (an API
  that only exists inside Claude's own artifact runtime) backed by the
  browser's `localStorage`, so saves persist on-device.
- **`manifest.json`** / **`sw.js`** — clean, valid versions, matching the
  ones that got your last install working.

## Updating later

If you get a new `life-sim.jsx` again, just ask for the bundle to be
rebuilt and replace `life-sim.bundle.js` in the repo — everything else
stays the same.
