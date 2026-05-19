# Living Life — Setup

The app is **already deployed** and your data repo is initialized. You just need to grant the app access to your data repo, which takes ~3 minutes.

## ✅ Status — what's already done

| Thing | Status | URL |
|---|---|---|
| **App hosted** | ✅ Live | https://vedantpatel699.github.io/living-life-app/ |
| **Data repo** | ✅ Created (private) | https://github.com/vedantpatel699/living-life-data |
| **GitHub Pages** | ✅ Enabled | served from `main` branch |
| **Code repo** | ✅ Created (public) | https://github.com/vedantpatel699/living-life-app |

---

## Step 1 — Open the app

On your **Pixel 8 Pro** (or any device):

1. Open Chrome and go to https://vedantpatel699.github.io/living-life-app/
2. You'll see the welcome screen.
3. **Add to home screen**: Chrome → ⋮ menu → **Add to Home Screen** → name it "Living Life" → Add. Now it opens like a real app.

(On a PC: just bookmark the URL.)

## Step 2 — Connect the app to your data repo

The app uses a **fine-grained Personal Access Token (PAT)** with permission to read/write only your `living-life-data` private repo. You already have one — it's the token you generated. Here's how to enter it:

1. Tap **Open Settings** on the welcome screen
2. Fill in:
   - **GitHub username:** `vedantpatel699`
   - **Repo name:** `living-life-data`
   - **Branch:** `main`
   - **Token:** paste your `github_pat_...` token
3. Tap **Test connection** → should show "✓ Connected to vedantpatel699/living-life-data"
4. Tap **Save**

That's it. The app remembers everything in localStorage on this device.

> 🔒 Security note: the token you generated has Contents Read+Write scoped to **only** the `living-life-data` repo. That's the right scope — it's tight and your data repo stays private. The public `living-life-app` code repo doesn't need the token since the code is open.

## Step 3 — Log your first entry

Once connected, tap **Today**:
1. Enter your weight (or skip until you have a scale)
2. Tap **Take photo** → camera opens → snap your physique photo
3. Tap an activity chip
4. Type a quick line about meals
5. Pick an energy emoji
6. **Save & sync**

You'll see a "Saved ✓" toast and the data writes to your private GitHub repo. Done. Tomorrow, repeat.

---

## Updating the app code later

Because the token you generated only has access to `living-life-data` (the secure choice), pushing updates to the public `living-life-app` code repo requires either:

**Option A — Generate a wider-scope PAT for code updates** (recommended for iteration):
1. https://github.com/settings/personal-access-tokens/new
2. Token name: `living-life-code-deploy`
3. Repository access: **Selected repositories** → include `living-life-app` AND `living-life-data`
4. Permissions: **Contents — Read and write**
5. Save the token, and we can deploy code updates with it.

**Option B — Push manually** (one-off updates):
1. Clone `living-life-app` to your PC
2. Replace `index.html` with the latest from your Living Life folder's `app/index.html`
3. `git commit -am "Update app" && git push`
4. GitHub Pages auto-redeploys in ~1 minute

Either works. Option A is what we'd want if I'm pushing code for you.

---

## Privacy

- Your token is stored only in your browser's localStorage on each device you install on. It never leaves to anywhere except GitHub's API.
- Your photos and data live in YOUR private `living-life-data` GitHub repo. Only you and the app (acting as you) can read them.
- If you ever want to wipe a device, just clear that browser's data or use the "Clear local cache" button in the app's Settings.

---

## Using on phone AND PC

The app deployment is a single URL. On both devices:
1. Open https://vedantpatel699.github.io/living-life-app/
2. Open Settings → enter token (one-time per device)
3. Both devices read/write the same data repo

When you log on your phone, the PC version pulls the latest on next sync. Tap the **Sync** button in the header on either to manually refresh.

---

## Troubleshooting

**"Sync error: GitHub 401"** — token is wrong or expired. Generate a new one.

**"Sync error: GitHub 403"** — token doesn't have Contents Read+Write on the data repo. Re-check the token's "Repository access" includes `living-life-data` and "Permissions" includes Contents R/W.

**"Sync error: GitHub 404"** — repo name or username typo. Verify in Settings.

**Photos slow to upload on cellular** — large originals take time even after compression. Works fine over WiFi.

**Can't install to home screen on Chrome** — make sure Chrome is updated. The "Add to Home Screen" option is in the three-dot menu.

**Want a backup of your data?** It's already on GitHub — that IS your backup. For an extra local copy: Settings → **Export JSON**.

---

## Coming soon

The web app is a fine starting point. The native Android wrap is documented in `android-build/BUILD_ANDROID.md` — that gives you:

- Health Connect integration (Garmin steps, HR, sleep, workouts auto-sync)
- Native camera (better than the web file picker)
- Local notifications (daily reminder, weekly reflection alert, rest-timer chimes)
- App icon on home screen with splash screen

When you're ready for that, that's the next step.
