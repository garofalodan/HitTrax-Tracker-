[README.md](https://github.com/user-attachments/files/31930600/README.md)
# Session Tracker — setup guide

A standalone batting-practice tracker: upload HitTrax screen photos, it reads
the stats off them automatically, and logs sessions, progress charts,
personal records, achievements, and goals. No build step — it's a single
HTML file plus one icon image.

## What's in this folder

- `index.html` — the entire app
- `icon-180.png` — your home screen icon (a baseball with flames)
- `README.md` — this file

## 1. Get an Anthropic API key

Photo-reading calls Claude directly from your phone, so you need your own key:

1. Go to https://console.anthropic.com and sign in (or create an account —
   this is separate from claude.ai).
2. Go to **Settings → Billing** and add a small amount of credit (a few
   dollars covers a very long time — each photo read costs a fraction of a cent).
3. Go to **Settings → API Keys → Create Key**. Give it a name like "Session
   Tracker."
4. **Copy the key immediately** (starts with `sk-ant-...`). It's only shown
   once — if you lose it, you'll need to make a new one, not recover the old
   one.

## 2. Put the app on GitHub Pages

1. On github.com, click the **+** icon → **New repository**.
2. Name it something like `session-tracker`. Keep it **Public** (required
   for free GitHub Pages). Don't add a README — you already have one.
3. Click **Create repository**.
4. On the empty repo page, click **uploading an existing file**, then drag
   in both `index.html` and `icon-180.png` from this folder.
5. Click **Commit changes**.
6. Go to **Settings → Pages** (left sidebar).
7. Under **Build and deployment → Source**, choose **Deploy from a branch**.
   Under **Branch**, choose `main` and `/ (root)`, then **Save**.
8. Wait about a minute, refresh the page, and you'll see your live URL —
   something like `https://yourusername.github.io/session-tracker/`.

## 3. Add it to your iPhone home screen

1. Open that URL in **Safari** on your iPhone (must be Safari, not Chrome).
2. Tap the **Share** button (square with an arrow up).
3. Tap **Add to Home Screen**, then **Add**.

You'll get a real icon — the flaming baseball — that opens full-screen, no
browser bar. Everything works the same as it did in testing.

## 4. Add your API key in the app

1. Open the app from the home screen icon.
2. Tap the **⚙** in the top right.
3. Paste your API key and tap **Save**.

That's it. Try Upload → choose a HitTrax photo, and it should read the
stats automatically.

## How data is stored

Everything — sessions, stats, goals, achievements, your API key — is saved
in that one browser's local storage, on that one device. It persists
between visits as long as you keep using the same URL in the same browser.
It does **not** sync across devices or browsers, and clearing Safari's
site data would wipe it. There's no cloud backup built in.

## Updating the app later

If you get an updated `index.html` (or icon) from me:

1. Go to your GitHub repo.
2. Click on the file you're replacing (e.g. `index.html`).
3. Click the pencil (edit) icon, or use **Add file → Upload files** and
   drag the new version in to overwrite it.
4. Commit the change.

GitHub Pages redeploys automatically within about a minute. Your saved
session data is untouched by this — it lives in your phone's browser, not
in the GitHub files.

## Troubleshooting quick reference

- **Blank page after opening the URL:** hard-refresh (pull down or
  Cmd/Ctrl+Shift+R). Check the browser console for red errors if it
  persists.
- **"Could not read this photo automatically":** usually a HEIC photo your
  browser can't decode — the app has a fallback decoder, but very new
  iPhone photos occasionally aren't supported yet. Re-saving the photo as
  JPEG (or switching your camera to Settings → Camera → Formats → Most
  Compatible) avoids this entirely.
- **Spray chart image looks cropped wrong:** use the "Adjust this photo"
  link that appears under each uploaded photo to fine-tune the crop box for
  that image, and optionally save it as the new default.
- **Duplicate photo warning:** the app fingerprints every photo — if you
  see this, it means that exact file was already saved (or picked twice in
  the same upload). You can skip it or upload anyway.
