# 🚀 Full Website Tutorial: Login + Google Maps + YouTube on GitHub Pages

## What You'll Build
A polished 2-page website:
- **`login.html`** — a working login screen with validation
- **`dashboard.html`** — a dashboard with Google Maps + an embedded YouTube video

Hosted **100% free** on GitHub Pages.

---

## File Structure

```
my-website/
├── login.html       ← Login page (start here)
├── dashboard.html   ← Dashboard with Maps + YouTube
└── README.md        ← (optional, GitHub will show this)
```

---

## STEP 1 — Create a GitHub Account & Repository

1. Go to **https://github.com** and sign up (free).
2. Click **"New"** (the green button) to create a repository.
3. Name it **`my-website`** (or anything you like).
4. ✅ Check **"Add a README file"**
5. Set visibility to **Public**.
6. Click **"Create repository"**.

---

## STEP 2 — Upload Your Files

1. Open your repository on GitHub.
2. Click **"Add file" → "Upload files"**.
3. Drag and drop `login.html` and `dashboard.html` into the upload area.
4. Scroll down and click **"Commit changes"**.

---

## STEP 3 — Enable GitHub Pages

1. In your repository, go to **Settings** (top tab).
2. In the left sidebar, click **"Pages"**.
3. Under **"Branch"**, select `main` and click **Save**.
4. Wait ~60 seconds, then refresh the page.
5. You'll see a banner: **"Your site is live at https://YOUR-USERNAME.github.io/my-website/"**

✅ Your login page is now live at:
```
https://YOUR-USERNAME.github.io/my-website/login.html
```

---

## STEP 4 — Get a Google Maps API Key (Free)

The map on your dashboard needs an API key. Here's how:

1. Go to **https://console.cloud.google.com**
2. Create a new project (call it anything).
3. In the search bar, search for **"Maps JavaScript API"** and enable it.
4. Go to **Credentials → Create Credentials → API Key**.
5. Copy your key (looks like: `AIzaSyAbc123...`)

### Add the key to dashboard.html

Open `dashboard.html` and find this line near the top:

```javascript
const GOOGLE_MAPS_API_KEY = "YOUR_GOOGLE_MAPS_API_KEY";
```

Replace `YOUR_GOOGLE_MAPS_API_KEY` with your real key:

```javascript
const GOOGLE_MAPS_API_KEY = "AIzaSyAbc123YourRealKeyHere";
```

### Restrict your key (recommended for security)

In Google Cloud Console → Credentials → click your key:
- Under **"Application restrictions"** → select **"HTTP referrers"**
- Add: `https://YOUR-USERNAME.github.io/*`

This prevents others from using your key.

---

## STEP 5 — Change the Map Location

In `dashboard.html`, find the `locations` object and edit the coordinates:

```javascript
const locations = {
  headquarters: { lat: -7.7956, lng: 110.3695, label: 'HQ – Yogyakarta' },
  office2:      { lat: -7.8014, lng: 110.3644, label: 'Office 2'         },
  warehouse:    { lat: -7.7900, lng: 110.3800, label: 'Warehouse'        },
};
```

To find coordinates of any location:
1. Open **https://maps.google.com**
2. Right-click any point → click the coordinates at the top to copy them
3. Paste `lat` and `lng` into your code

---

## STEP 6 — Change the YouTube Video

In `dashboard.html`, find the `<iframe>` tag:

```html
<iframe
  src="https://www.youtube.com/embed/dQw4w9WgXcQ?rel=0&modestbranding=1"
  ...
```

Replace `dQw4w9WgXcQ` with any YouTube video ID:

1. Go to any YouTube video
2. The URL looks like: `https://www.youtube.com/watch?v=VIDEO_ID_HERE`
3. Copy the part after `v=`
4. Paste it into the iframe `src`

Also update the title and channel text below the video:

```html
<div class="video-title">Your featured video title here</div>
<div class="video-channel">Channel Name · YouTube</div>
```

---

## STEP 7 — Re-upload Updated Files to GitHub

After making any changes locally:

1. Go to your GitHub repository
2. Click on `dashboard.html`
3. Click the **pencil icon** (Edit) — or drag and drop the updated file
4. Scroll down → **"Commit changes"**
5. Wait ~30 seconds, then refresh your live site

---

## STEP 8 — Test Everything

Visit your live site:

| Page | URL |
|------|-----|
| Login | `https://YOUR-USERNAME.github.io/my-website/login.html` |
| Dashboard | `https://YOUR-USERNAME.github.io/my-website/dashboard.html` |

### Checklist:
- [ ] Login form shows validation errors for blank/invalid input
- [ ] Successful login redirects to `dashboard.html`
- [ ] Google Maps loads and shows your pins
- [ ] Map buttons (HQ / Office 2 / Warehouse) pan the map
- [ ] YouTube video plays inside the dashboard
- [ ] Sidebar navigation works

---

## How the Login Works

The login uses **client-side JavaScript validation** (no backend needed):

```javascript
function handleLogin() {
  // Validates email format and password length
  // On success: shows a success overlay and links to dashboard.html
}
```

> **Note:** This is a frontend-only demo. For real authentication (actual user accounts, passwords stored securely), you'd need a backend service like **Firebase Auth**, **Supabase**, or **Auth0** — all have free tiers.

---

## Customization Quick Reference

| What to change | Where to find it |
|---|---|
| Site name / logo | Search for `MyApp` in both files |
| Colors | `:root { --accent: ...; }` CSS block |
| Font | `@import` URL at the top |
| Map location pins | `const locations = { ... }` in dashboard.html |
| YouTube video | Replace the video ID in the `<iframe src>` |
| User name in sidebar | Find `Jane Doe` in dashboard.html |
| Navigation links | The `<a class="nav-item">` elements in sidebar |

---

## Optional Next Steps

| Feature | Tool |
|---|---|
| Real login / user accounts | Firebase Auth (free) |
| Store data (posts, locations) | Firebase Firestore or Supabase |
| Custom domain (yourname.com) | GitHub Pages → Custom domain settings |
| Contact form | Formspree.io (free) |
| Analytics | Google Analytics (free) |

---

*Built with plain HTML, CSS, and JavaScript — no frameworks required.*
