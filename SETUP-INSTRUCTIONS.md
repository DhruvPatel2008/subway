# 🥖 Subway Fresh Tracker — Setup Guide

This is a **one-time setup** that takes about 10 minutes.
After that, both employees just open the website every day.

---

## WHAT YOU NEED
- A free Google account (Gmail)
- A free GitHub account (github.com)
- The `index.html` file

---

## PART 1 — Set up your FREE database (Firebase)

Firebase is Google's free database. It's what keeps both phones in sync.

### Step 1 — Go to Firebase
1. Open your browser and go to: **https://console.firebase.google.com**
2. Sign in with your Google account

### Step 2 — Create a project
1. Click the big **"Add project"** button
2. Name it: `subway-tracker` (or anything you like)
3. It will ask about Google Analytics — click **"Disable"** then **"Create project"**
4. Wait a few seconds, then click **"Continue"**

### Step 3 — Create the database
1. On the left sidebar, click **"Build"** → then **"Realtime Database"**
2. Click **"Create Database"**
3. Choose a location (pick whichever is closest to you — Canada if you're in Canada)
4. It asks about security rules — choose **"Start in test mode"**
5. Click **"Enable"**

> ✅ Your database is now created!

### Step 4 — Get your config keys
1. Click the **gear icon** ⚙ near the top left → **"Project settings"**
2. Scroll down to **"Your apps"** section
3. Click the **`</>`** (web) icon
4. App nickname: type `tracker` → click **"Register app"**
5. You will see a block of code that looks like this:

```
const firebaseConfig = {
  apiKey: "AIzaSyXXXXXXXXXXXXXXXXXXXXX",
  authDomain: "subway-tracker-XXXX.firebaseapp.com",
  databaseURL: "https://subway-tracker-XXXX-default-rtdb.firebaseio.com",
  projectId: "subway-tracker-XXXX",
  storageBucket: "subway-tracker-XXXX.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:XXXXXXXXX"
};
```

6. **Copy all these values** — you need them in the next step

---

## PART 2 — Put your config into index.html

### Step 5 — Edit index.html
1. Open `index.html` in **Notepad** (Windows) or **TextEdit** (Mac)
   - Windows: right-click the file → "Open with" → Notepad
   - Mac: right-click → "Open With" → TextEdit

2. Near the very top of the file, find this section:

```javascript
const FIREBASE_CONFIG = {
  apiKey:            "PASTE_YOUR_apiKey_HERE",
  authDomain:        "PASTE_YOUR_authDomain_HERE",
  databaseURL:       "PASTE_YOUR_databaseURL_HERE",
  ...
```

3. Replace each `"PASTE_YOUR_xxxxx_HERE"` with the matching value from Firebase.
   For example:
   ```
   apiKey: "AIzaSyXXXXXXXXXXXXXXXXXXXXX",
   ```

4. **Save the file** (Ctrl+S on Windows, Cmd+S on Mac)

---

## PART 3 — Put it on GitHub (free hosting)

### Step 6 — Create GitHub account
1. Go to **https://github.com** and sign up for a free account (if you don't have one)

### Step 7 — Create a new repository
1. Click the **"+"** button at the top right → **"New repository"**
2. Repository name: `subway-tracker`
3. Make sure it is set to **Public**
4. Check the box: **"Add a README file"**
5. Click **"Create repository"**

### Step 8 — Upload index.html
1. On your new repository page, click **"Add file"** → **"Upload files"**
2. Drag your `index.html` file into the upload area
3. Scroll down and click **"Commit changes"**

### Step 9 — Enable GitHub Pages (free hosting)
1. Click **"Settings"** (tab at the top of the repository)
2. On the left sidebar, click **"Pages"**
3. Under "Source" → click the dropdown and select **"main"**
4. Click **"Save"**
5. Wait 1-2 minutes, then GitHub will show you a green banner with your URL like:
   ```
   https://YOUR-USERNAME.github.io/subway-tracker/
   ```

### Step 10 — Open and test it!
1. Open that URL in your phone browser
2. You should see the Fresh Tracker with a green "SYNCED — LIVE" indicator at the top
3. Send the same URL to your coworker
4. Both of you can now log items and they'll sync instantly!

---

## DAILY USE

**Every time you open/prep something:**
1. Tap **"+ Log Item"**
2. Find the item (or use the search bar)
3. Tap the item → select its current state (Opened, Prepped, etc.)
4. Done! It appears on the Dashboard with a countdown

**Dashboard colours:**
- 🟢 Green = still good (shows time remaining)
- 🟡 Yellow = expiring in under 6 hours
- 🟠 Orange = critical — expiring in under 2 hours!
- 🔴 Red flashing = **DISCARD NOW**

Items are automatically sorted — most urgent always shows at the top.

**When you discard something:** tap the **✕** button on that item.

---

## BOOKMARK IT ON YOUR PHONE

**iPhone:** Open the URL in Safari → tap the Share button → "Add to Home Screen"

**Android:** Open in Chrome → tap the three dots menu → "Add to Home screen"

Now it works like an app on your phone! 📱

---

## COST: $0.00

- Firebase free tier: up to 100 simultaneous users, 1GB storage, 10GB/month transfer
- GitHub Pages: completely free forever
- For a 2-person store this will NEVER hit the free limits

---

## NEED HELP?

If anything goes wrong, the most common issues are:

| Problem | Fix |
|---|---|
| Orange banner saying "not configured" | You haven't replaced the Firebase config values yet |
| "SYNC ERROR" at the top | Double-check your `databaseURL` value is correct |
| Items not showing on other phone | Both phones need internet connection |
| Page not loading | Wait 2-3 minutes after enabling GitHub Pages |
