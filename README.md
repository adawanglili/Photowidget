# 🌸 Mae's Photo Watermarker

A lightweight, browser-based tool that automatically stamps your daughter's age onto photos — no app installs, no uploads to any server, no cost.

Drop in a photo taken when Mae was 3 months old and it comes out labelled **"Mae, 3 months old"** — automatically.

---

## Features

- **Auto age detection** — reads the EXIF date embedded in each photo to calculate Mae's exact age in months at the time it was taken
- **Fallback date** — if a photo has no EXIF data, the file's last-modified date is used (shown with a ⚠ badge so you know)
- **Batch processing** — upload and watermark many photos at once, then download them all in one click
- **Customizable watermark** — adjust the name, text position, font size, text color, and background style (drop shadow, dark box, or none)
- **Private by design** — everything runs in your browser; photos are never uploaded anywhere
- **Zero dependencies to install** — it's a single HTML file

---

## How to Use

1. Open the app (see hosting options below)
2. Adjust watermark settings if needed (name, position, color, etc.)
3. Drag and drop photos onto the upload area, or click to browse
4. Preview each watermarked photo in the gallery
5. Download individually or click **Download All**

---

## Hosting on GitHub Pages (free)

This app is a single `index.html` file that runs entirely in the browser — no backend needed. GitHub Pages hosts it for free.

### Step-by-step

1. [Create a GitHub account](https://github.com) if you don't have one
2. Click **New repository** and name it (e.g. `mae-watermarker`)
3. Set visibility to **Public** and click **Create repository**
4. Upload `index.html` by clicking **Add file → Upload files**
5. Go to **Settings → Pages**
6. Under *Source*, choose **Deploy from a branch**
7. Set branch to `main` and folder to `/ (root)`, then click **Save**
8. Wait about 1 minute — your app will be live at:

```
https://YOUR_USERNAME.github.io/mae-watermarker/
```

Bookmark that link and it's always there whenever you need it.

---

## Running Locally

No server required. Just open the file directly in any modern browser:

```
double-click index.html
```

Or via terminal:

```bash
open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux
```

---

## Watermark Settings

| Setting | Options | Default |
|---|---|---|
| Baby's name | Any text | Mae |
| Birthday | YYYY-MM-DD | 2025-05-24 |
| Position | Bottom right/left/center, Top right/left, Center | Bottom right |
| Text color | Color picker | White |
| Font size | 1–10% of image width | 4% |
| Background style | Drop shadow, Dark box, None | Drop shadow |

---

## How Age Is Calculated

Mae's birthday is **May 24, 2025**. When you upload a photo, the app reads the date it was taken and computes:

```
age in months = (photo year − birth year) × 12 + (photo month − birth month)
```

If the photo was taken before the day-of-month matches the birthday, one month is subtracted for accuracy. A photo taken on May 10, 2026 would read **11 months old**, not 12.

A photo taken before the birthday returns **"newborn"**.

---

## Privacy

Photos are processed entirely on your device using the browser's Canvas API. Nothing is sent to any server. Closing the tab discards everything.

---

## Tech Stack

- Vanilla HTML, CSS, JavaScript
- [exif-js](https://github.com/exif-js/exif-js) for reading photo metadata
- [Google Fonts](https://fonts.google.com) — Playfair Display + DM Sans
- Hosted via GitHub Pages

---

## Customizing for Another Baby

To adapt this for a different child, open `index.html` in a text editor and update the default values:

- **Name**: find `value="Mae"` and change it
- **Birthday**: find `value="2025-05-24"` and change it to `YYYY-MM-DD` format

Both can also be changed in the app UI without editing code.

---

*Made with love for Mae 🌸 — born May 24, 2025*
