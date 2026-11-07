# SmartDesk demo app

**Your smart assistant for the day-to-day.** Book, block, plan and post, in one chat.

An installable web app (PWA) demo with two modes, chosen on first launch and switchable anytime:

- **Business mode** (sample: Bloom Hair Studio): customer bookings, booking page, supplier and content events, business posts.
- **Personal mode** (sample: Tolu): events, focus time, personal tasks and personal posts. No booking page or customer fields.

Each mode keeps its own calendar, tasks and posts on the device.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole app (screens, styles and logic) |
| `manifest.json` | App name, colours and icons, so phones can install it |
| `sw.js` | Service worker: lets the app open offline after the first visit |
| `favicon.svg`, `favicon-32.png`, `icon-*.png` | SmartDesk logo (white desk and coral spark on teal) as browser and home-screen icons |

## Put it online (choose one)

The app must be served over **HTTPS** for installing and offline use to work.

### Option A: Netlify Drop (easiest, about 2 minutes)
1. Unzip `smartdesk-app.zip`.
2. Go to https://app.netlify.com/drop and sign in (free).
3. Drag the **`smartdesk-pwa` folder** onto the page.
4. Netlify gives you a link like `https://random-name.netlify.app`. Rename it in Site settings if you like.

### Option B: GitHub Pages
1. Unzip the file and open a terminal in the `smartdesk-pwa` folder.
2. Run:
   ```
   git init
   git add .
   git commit -m "SmartDesk demo app"
   git branch -M main
   git remote add origin https://github.com/Omolaso-charis/SmartDesk.git
   git pull --rebase origin main   # only if the repo already has files
   git push -u origin main
   ```
3. On GitHub: Settings → Pages → Source: "Deploy from a branch" → Branch `main`, folder `/ (root)` → Save.
4. After a minute, open `https://omolaso-charis.github.io/SmartDesk/`.

## Install on a phone

**iPhone (Safari)**
1. Open the link in Safari (not Chrome).
2. Tap the Share button, then **Add to Home Screen**, then **Add**.
3. Open SmartDesk from the home screen. It opens full screen with no browser bars.

**Android (Chrome)**
1. Open the link in Chrome.
2. Tap the ⋮ menu, then **Install app** (or **Add to Home screen**).
3. Open SmartDesk from the home screen or app drawer.

**Laptop (Chrome or Edge)**
1. Open the link.
2. Click the install icon at the right of the address bar, then **Install**.

## Good to know
- **Switching modes.** Tap the mode pill on the home card, or go to Settings → Mode.
- **Data stays on the device.** Each phone keeps its own sample data for each mode. Use Settings → Reset demo data before presenting.
- **Assistant.** Live AI only works when the app is opened through the Claude artifact link. The installed app uses the built-in offline assistant, which handles the suggestion buttons in the chat:
  - Business: "Block Friday morning for admin", "Book a silk press for Funmi on Wednesday at 2pm", "Draft an Instagram post about our new colour treatment", "Remind me to reorder shampoo".
  - Personal: "Block 2pm tomorrow for focus time", "Add lunch with Bisi on Friday at 1pm", "Draft an Instagram post about my weekend", "Remind me to call my mum".
- **First screen again.** To see the mode picker again on a device, clear the site data in the browser settings.
- **Previews.** Calendar sync and social posting are simulated and do not connect to real accounts.
- **Updating.** Replace the files on your host. Users get the update the next time they open the app online.
- **App stores.** Publishing to the App Store or Google Play needs developer accounts and a wrapper such as PWABuilder or Capacitor.
