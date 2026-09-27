# Spotter — Car ID App

Identifies a car's **make, model, and colour** from a photo, using Google's **Gemini API free tier** (no billing needed). It's a Progressive Web App (PWA) — installs to a home screen like a real app, with no app store involved.

## What's in this folder
- `index.html` — the app
- `manifest.json`, `sw.js`, `icons/` — what makes it installable

## Step 1 — Put it on GitHub Pages (free, gives it a real link)
Installing needs an `https://` link — a `file://` link won't offer an "Install" prompt.

1. Create a new GitHub repo (public is fine — there are no secrets in this code; each person enters their own API key locally on their own device).
2. Upload all the files in this folder, keeping the folder structure (`icons/` stays a subfolder).
3. In the repo: **Settings → Pages → Source → Deploy from branch → main → / (root) → Save**.
4. After a minute, GitHub gives you a link like `https://yourusername.github.io/your-repo/`. That's the app.

Anyone with that link can install it — they don't need write access to the repo, just the URL (or repo access if you'd rather keep it private and have them clone + host it themselves — see the note below).

## Step 2 — Install it on a device

**Android (Chrome):**
1. Open the GitHub Pages link.
2. Tap the **⋮** menu → **Add to Home screen** / **Install app**.
3. It now opens full-screen from the home screen like a normal app.

**iPhone (Safari):**
1. Open the link in **Safari** (must be Safari, not Chrome, for this to work on iOS).
2. Tap the **Share** icon → **Add to Home Screen**.
3. It appears as an app icon and opens without browser bars.

That's it — no App Store, no Play Store, no review process.

## Optional — a literal installable file (Android `.apk`)
If you want an actual file to hand someone to "install," not just a link:
1. Host the app on GitHub Pages first (step 1 above).
2. Go to **pwabuilder.com**, paste your GitHub Pages URL.
3. It packages your PWA into a downloadable `.apk`.
4. On the Android device: enable **Install unknown apps** for the browser/file manager you're using, then open the `.apk` to install.

This only works for Android — iPhones don't allow installing apps outside the App Store or a home-screen web app, so the Safari method above is the closest equivalent on iOS.

## Keeping it private
If you don't want the app public at all:
- Use a **private repo** and have each person `git clone` it, then open `index.html` directly (camera access may be blocked on `file://` in some browsers — "Choose photo" always works).
- Or keep the repo private and run GitHub Pages anyway — note that GitHub Pages sites are public by default even from a private repo, unless you're on a paid GitHub plan that supports private Pages.

## Using the app
1. Paste your **Gemini API key** — free at aistudio.google.com/app/apikey, no billing required.
2. Take or choose a photo of a car.
3. Tap **Identify this car** — make, model, colour and a confidence level appear.

Everything runs in the browser. Your key and photo go straight to Google's API, never through any other server.
