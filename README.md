# 📁 My Portfolio & File Sharing Website

A premium WhatsApp-inspired personal portfolio and file sharing website.  
**No backend. No server. Just GitHub + Render.**

---

## 🗂️ File Structure

```
your-repo/
├── index.html        ← Main website (single file)
├── data.json         ← All your content (files, links, notice, profile)
├── files/            ← Upload PDFs, APKs, ZIPs here
│   ├── sample.pdf
│   ├── modapp.apk
│   └── ...
├── media/            ← Upload images, videos, audio here
│   ├── photo1.jpg
│   ├── tutorial.mp4
│   └── ...
└── README.md
```

---

## ⚡ Quick Setup (5 Steps)

### Step 1 — Fork / Create GitHub Repo
- Go to [github.com](https://github.com) → New Repository
- Name it anything (e.g. `my-portfolio`)
- Set to **Public** (required for free Render hosting)

### Step 2 — Upload Files
- Upload `index.html`, `data.json`, `README.md`
- Create `files/` folder → upload your PDFs, APKs, ZIPs
- Create `media/` folder → upload images, videos, audio

### Step 3 — Connect data.json to index.html
Open `index.html` and find this line (around line 5):
```javascript
const DATA_URL = null;
```
Replace `null` with your raw GitHub URL:
```javascript
const DATA_URL = "https://raw.githubusercontent.com/YOURUSERNAME/YOURREPO/main/data.json";
```

### Step 4 — Deploy on Render
1. Go to [render.com](https://render.com) → Sign in with GitHub
2. Click **New** → **Static Site**
3. Connect your GitHub repo
4. Settings:
   - **Build Command:** *(leave empty)*
   - **Publish Directory:** `.`  (just a dot)
5. Click **Deploy** ✅

### Step 5 — Done! 🎉
Your site is live at `https://your-site-name.onrender.com`

---

## ✏️ How to Update Content (Admin Guide)

### 📝 Update Notice Board
Edit `data.json` → find the `"notice"` section:
```json
"notice": {
  "text": "Your new notice message here 🎉",
  "postedAt": "2025-06-01T10:00:00.000Z",
  "expiry": "never"
}
```
**Expiry options:**
| Value | Meaning |
|-------|---------|
| `"never"` | Notice stays forever |
| `"24h"` | Auto-hides after 24 hours |
| `"7d"` | Auto-hides after 1 week |

> **postedAt** — Set to current time in ISO format.  
> You can get it at: https://www.timestamp.online

---

### 📚 Add a PDF / Study Material
Edit `data.json` → find `"study"` → `"pdfs"` array, add:
```json
{
  "name": "Physics Notes Chapter 3",
  "size": "1.8 MB",
  "url": "https://raw.githubusercontent.com/YOURUSERNAME/YOURREPO/main/files/physics3.pdf",
  "icon": "📗"
}
```
Then upload `physics3.pdf` to your `files/` folder on GitHub.

---

### 📱 Add an App / APK
Edit `data.json` → find `"apps"` → `"apps"` array, add:
```json
{
  "name": "My App v2.0",
  "size": "25 MB",
  "url": "https://raw.githubusercontent.com/YOURUSERNAME/YOURREPO/main/files/myapp.apk",
  "icon": "📲",
  "version": "v2.0"
}
```

---

### 🖼️ Add a Picture to Gallery
Edit `data.json` → find `"gallery"` → `"picture"` array, add:
```json
{
  "name": "My Photo.jpg",
  "url": "https://raw.githubusercontent.com/YOURUSERNAME/YOURREPO/main/media/myphoto.jpg",
  "thumb": ""
}
```
Upload `myphoto.jpg` to `media/` folder.

> **thumb** — Leave empty `""` to use main URL as thumbnail,  
> or provide a separate smaller thumbnail URL for faster loading.

---

### 🔗 Add a Useful Link
Edit `data.json` → find `"folder"` → `"links"` array, add:
```json
{
  "name": "Cool Website",
  "url": "https://example.com",
  "desc": "Short description here"
}
```

---

### 👤 Update Profile Info
Edit `data.json` → find `"profile"`:
```json
"profile": {
  "name": "Your Real Name",
  "bio": "Your bio goes here",
  "avatarUrl": "https://link-to-your-photo.jpg",
  "siteTitle": "My Hub",
  "tagline": "Sharing Made Easy"
}
```

---

### 🌐 Update Social Media Links
Edit `data.json` → find `"social"` array → replace `#` with your real URLs:
```json
{ "label": "Instagram", "icon": "fab fa-instagram", "cls": "ig", "url": "https://instagram.com/yourhandle" }
```

---

## 🔐 Change Admin PIN
Open `index.html` → find this line:
```javascript
const ADMIN_PIN = "1234";
```
Change `"1234"` to your secret PIN.

---

## 🚀 How to Update Site After Changes

1. Edit `data.json` on GitHub (click pencil ✏️ icon)
2. Scroll down → click **Commit changes**
3. Render auto-deploys in ~1 minute ✅

No need to touch `index.html` for content updates — only `data.json`!

---

## 📦 Getting Raw GitHub File URLs

For any file you upload to GitHub, the raw URL format is:
```
https://raw.githubusercontent.com/YOURUSERNAME/YOURREPO/main/FOLDER/FILENAME
```

Example:
```
https://raw.githubusercontent.com/john/my-portfolio/main/files/notes.pdf
```

---

## 💡 Tips

- **File size limit:** GitHub free = 100MB per file. Use Google Drive / Telegram for bigger files and paste the direct link in `data.json`.
- **Images:** Use [imgbb.com](https://imgbb.com) or [postimages.org](https://postimages.org) for free image hosting and paste the direct URL.
- **Videos:** Host on Google Drive → get shareable link, or use direct links.
- **Notice expires locally** — The 24h/7d timer runs in the visitor's browser based on `postedAt` time.

---

## 🛠️ Tech Stack

| Part | Technology |
|------|-----------|
| Frontend | HTML + CSS + Vanilla JS |
| Icons | Font Awesome 6.6 |
| Fonts | Plus Jakarta Sans + Syne (Google Fonts) |
| Hosting | Render (Static Site) |
| Content | GitHub raw files + data.json |
| Admin | PIN-protected localStorage overlay |

---

*Made with ❤️ — No backend, no database, no cost.*
