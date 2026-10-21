# 20/10 Interactive Letter Cards for Mother & Sister Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build and publish two dedicated, mobile-optimized interactive 20/10 letter websites for Mother (`/me/`) and Sister (`/chi/`) with 3D opening envelopes, custom wax seals, heartfelt letters, Polaroid photos, theme music, and interactive widgets.

**Architecture:** Static HTML5/CSS3/JavaScript pages leveraging Tailwind CSS (CDN), FontAwesome 6, Google Fonts, and Canvas particle systems. Subdirectory structure within the existing `danglio/tang-be-dau` GitHub repository automatically served by GitHub Pages.

**Tech Stack:** HTML5, Tailwind CSS, Canvas API, Web Audio API, ffmpeg/ImageMagick/Python for asset optimization, Git & GitHub Pages.

## Global Constraints

- Standalone URLs: `https://danglio.github.io/tang-be-dau/me/` and `https://danglio.github.io/tang-be-dau/chi/`.
- Mother's Photo: `assets/me_photo.jpg` derived from `/Users/admin/Downloads/LDT05840.JPEG`.
- Sister's Photo: `assets/chi_photo.jpg` derived from `/Users/admin/Downloads/LDT05373.JPEG`.
- Photo sizes must be web-optimized (under 400KB each).
- Clean, high-quality audio tracks with zero spam intros/watermarks.
- Full mobile responsiveness on iOS Safari and Android Chrome.
- Autoplay on first touch gesture/envelope click with cache-busting query strings.

---

### Task 1: Asset Preparation & Optimization

**Files:**
- Create: `assets/me_photo.jpg`
- Create: `assets/chi_photo.jpg`
- Create: `assets/music_me.mp3`
- Create: `assets/music_chi.mp3`

**Interfaces:**
- Consumes: `/Users/admin/Downloads/LDT05840.JPEG`, `/Users/admin/Downloads/LDT05373.JPEG`
- Produces: Web-optimized JPEG images in `assets/` and MP3 audio files in `assets/`

- [ ] **Step 1: Convert and optimize photos using ffmpeg/sips**

```bash
# Convert Mother's photo (max width 1200, high quality JPEG)
ffmpeg -i /Users/admin/Downloads/LDT05840.JPEG -vf "scale='min(1200,iw)':-1" -q:v 3 assets/me_photo.jpg -y

# Convert Sister's photo (max width 1200, high quality JPEG)
ffmpeg -i /Users/admin/Downloads/LDT05373.JPEG -vf "scale='min(1200,iw)':-1" -q:v 3 assets/chi_photo.jpg -y
```

- [ ] **Step 2: Verify photo dimensions and file sizes**

```bash
ls -lh assets/me_photo.jpg assets/chi_photo.jpg
file assets/me_photo.jpg assets/chi_photo.jpg
```
Expected: Files exist, under 500KB each, valid JPEG.

- [ ] **Step 3: Download clean audio for Mother and Sister**

```bash
# Mother track: "Ước Mơ Của Mẹ"
/Users/admin/.local/bin/yt-dlp "scsearch1:uoc mo cua me van mai huong acoustic" -x --audio-format mp3 -o "assets/music_me.mp3" --force-overwrites

# Sister track: "Bat Tinh Yeu Len" acoustic / chill
/Users/admin/.local/bin/yt-dlp "scsearch1:bat tinh yeu len tang duy tan acoustic" -x --audio-format mp3 -o "assets/music_chi.mp3" --force-overwrites
```

- [ ] **Step 4: Verify audio duration and transcribe sample to guarantee clean sound**

```bash
ffprobe -v error -show_entries format=duration assets/music_me.mp3 assets/music_chi.mp3
```

- [ ] **Step 5: Commit prepared assets to git**

```bash
git add assets/me_photo.jpg assets/chi_photo.jpg assets/music_me.mp3 assets/music_chi.mp3
git commit -m "feat(assets): add optimized photos and theme audio for mother and sister"
```

---

### Task 2: Build Mother's 20/10 Web Page (`me/index.html`)

**Files:**
- Create: `me/index.html`

**Interfaces:**
- Consumes: `assets/me_photo.jpg`, `assets/music_me.mp3`
- Produces: Full interactive web application at `/me/`

- [ ] **Step 1: Scaffold `me/index.html` structure and styling**
Create `me/index.html` with:
- Google Fonts: `Dancing Script`, `Playfair Display`, `Quicksand`.
- Tailwind CSS with Warm Rose Gold & Peach palette.
- Floating Rose Petal canvas animation.
- Realistic 3D Envelope with ruby wax seal stamped *"Gửi Mẹ Yêu ❤️"*.

- [ ] **Step 2: Implement Letter Content & Photo**
- Sincere letter: Gratitude for Mom's sacrifices, wishing Mom health, joy, and peace.
- Polaroid frame rendering `../assets/me_photo.jpg` with floral washi tape and warm caption.

- [ ] **Step 3: Implement Mother-themed Interactive Widgets**
- Widget 1: *"💖 Gửi 10,000 lời chúc sức khỏe đến Mẹ"* (interactive heart counter).
- Widget 2: *"🎁 Phiếu đặc quyền của Mẹ"* (interactive flip voucher: Mom rests, I do everything).

- [ ] **Step 4: Implement Music Player & Autoplay Unlock**
- Audio player loading `../assets/music_me.mp3?v=20261021_me`.
- Gesture unlock listeners (`touchstart`, `click`, envelope trigger).

- [ ] **Step 5: Validate JavaScript Syntax**

```bash
node -e "
const fs = require('fs');
const html = fs.readFileSync('me/index.html', 'utf8');
const scriptRegex = /<script\b[^>]*>([\s\S]*?)<\/script>/gi;
let match;
while ((match = scriptRegex.exec(html)) !== null) {
  if (match[1].trim()) new Function(match[1]);
}
console.log('me/index.html syntax valid');
"
```
Expected: `me/index.html syntax valid`.

- [ ] **Step 6: Commit `me/index.html`**

```bash
git add me/index.html
git commit -m "feat: implement 20/10 web card for mother"
```

---

### Task 3: Build Sister's 20/10 Web Page (`chi/index.html`)

**Files:**
- Create: `chi/index.html`

**Interfaces:**
- Consumes: `assets/chi_photo.jpg`, `assets/music_chi.mp3`
- Produces: Full interactive web application at `/chi/`

- [ ] **Step 1: Scaffold `chi/index.html` with Lavender & Baby Pink Pastel Theme**
- Google Fonts & Tailwind CSS configuration.
- Floating sparkles & cute pastel hearts canvas animation.
- 3D Envelope with Lavender wax seal stamped *"Gửi Chị Hai 💌"*.

- [ ] **Step 2: Implement Sibling Letter & Polaroid Photo**
- Witty, affectionate letter celebrating Sister's beauty, kindness, and wishing her wealth & success.
- Polaroid frame rendering `../assets/chi_photo.jpg` with pastel washi tape and cute caption.

- [ ] **Step 3: Implement Sister-themed Interactive Widgets**
- Widget 1: *"🧋 Ting ting 1 ly trà sữa full topping cho Chị Hai"* (boba cup animation + confetti).
- Widget 2: *"🎫 Voucher sai vặt em trai 1 ngày"* (interactive redemption coupon).
- Widget 3: *"🍀 Rút quẻ may mắn cho Chị"* (random career/wealth/love blessings).

- [ ] **Step 4: Implement Music Player & Autoplay Unlock**
- Audio player loading `../assets/music_chi.mp3?v=20261021_chi`.
- Immediate playback on first touch/interaction.

- [ ] **Step 5: Validate JavaScript Syntax**

```bash
node -e "
const fs = require('fs');
const html = fs.readFileSync('chi/index.html', 'utf8');
const scriptRegex = /<script\b[^>]*>([\s\S]*?)<\/script>/gi;
let match;
while ((match = scriptRegex.exec(html)) !== null) {
  if (match[1].trim()) new Function(match[1]);
}
console.log('chi/index.html syntax valid');
"
```
Expected: `chi/index.html syntax valid`.

- [ ] **Step 6: Commit `chi/index.html`**

```bash
git add chi/index.html
git commit -m "feat: implement 20/10 web card for sister"
```

---

### Task 4: Local Verification & Integration

**Files:**
- Modify: `index.html` (optional subtle switcher/footer links)
- Test: Local HTTP server on port 3838

- [ ] **Step 1: Verify all 3 pages locally via curl / HTTP**

```bash
curl -I http://127.0.0.1:3838/me/
curl -I http://127.0.0.1:3838/chi/
curl -I http://127.0.0.1:3838/assets/me_photo.jpg
curl -I http://127.0.0.1:3838/assets/chi_photo.jpg
curl -I http://127.0.0.1:3838/assets/music_me.mp3
curl -I http://127.0.0.1:3838/assets/music_chi.mp3
```
Expected: All return HTTP 200 OK.

---

### Task 5: Push to GitHub & Verify GitHub Pages Deployment

**Files:**
- All repositories files

- [ ] **Step 1: Push changes to GitHub main branch**

```bash
git push origin main
```

- [ ] **Step 2: Monitor GitHub Pages build until `built`**

```bash
gh api repos/danglio/tang-be-dau/pages/builds/latest
```

- [ ] **Step 3: Verify live endpoints**

```bash
curl -sI https://danglio.github.io/tang-be-dau/me/ | grep "HTTP"
curl -sI https://danglio.github.io/tang-be-dau/chi/ | grep "HTTP"
```
Expected: HTTP/2 200 for both.
