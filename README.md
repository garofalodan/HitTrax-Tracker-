# Session Tracker — GitHub Pages setup

This folder is a complete, standalone web app. No build step — just host
`index.html` and open the page. (Home-screen icon setup, which needs a
manifest file and icons, can be added later — for now this is just the app.)

## 1. Get an Anthropic API key

Photo-reading calls Claude directly from your phone, so you need your own key:

1. Go to https://console.anthropic.com and sign in (or create an account).
2. Go to **Settings → API Keys → Create Key**.
3. Add a small amount of credit under **Billing** (each photo read costs a
   fraction of a cent — a few dollars will last a long time).
4. Copy the key (starts with `sk-ant-...`). You'll paste this into the app
   itself later, not into any file here.

## 2. Create the GitHub repo

1. On github.com, click **New repository**.
2. Name it something like `session-tracker`. Keep it **Public** (GitHub Pages
   needs this on a free account). Don't add a README — you already have one.
3. Click **Create repository**.
4. On the empty repo page, click **uploading an existing file**, then drag in
   `index.html` from this folder.
5. Commit the file (the green button at the bottom).

## 3. Turn on GitHub Pages

1. In your repo, go to **Settings → Pages** (left sidebar).
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Under **Branch**, choose `main` and `/ (root)`, then **Save**.
4. Wait about a minute, then refresh the page — you'll see a green box with
   your live URL, something like:
   `https://yourusername.github.io/session-tracker/`

## 4. Add it to your phone's home screen (iPhone)

1. Open that URL in **Safari** on your iPhone (must be Safari, not Chrome).
2. Tap the **Share** button (square with an arrow).
3. Tap **Add to Home Screen**.
4. Tap **Add**. You'll get a real icon on your home screen that opens full-screen, no browser bar.

## 5. Add your API key in the app

1. Open the app from the home screen icon.
2. Tap the **⚙** in the top right.
3. Paste your API key and tap **Save**.

That's it — everything else works exactly like the version we built in chat.
Your session data is saved on your phone (in the browser's local storage), so
it stays put between visits but won't sync across devices.

## Updating the app later

If we make changes, I'll give you an updated `index.html`. Just upload it to
the same GitHub repo (drag and drop again, or use **Add file → Upload
files**) to replace the old one — the live URL stays the same.
