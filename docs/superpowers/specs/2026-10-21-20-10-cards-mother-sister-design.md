# Design Document: 20/10 Interactive Letter Websites for Mother & Sister

**Date:** 2026-10-21  
**Author:** Antigravity AI  
**Status:** Approved by User  
**Target Deployment:** GitHub Pages (`https://danglio.github.io/tang-be-dau/me/` and `https://danglio.github.io/tang-be-dau/chi/`)

---

## 1. Overview & Objectives

In celebration of Vietnamese Women's Day (20/10), this project extends the existing romantic 20/10 web application with two new dedicated interactive web cards:
1. **Web for Mother (`/me/`):** A warm, deeply affectionate, respectful and emotional gratitude letter with dedicated Mom-themed music, elegant visual aesthetic, and Mother-themed interactive widgets.
2. **Web for Sister (`/chi/`):** A youthful, cute, witty and loving letter with trendy Gen Z/acoustic music, aesthetic pastel styling, and humorous sister-sibling interactive perks.

Both web cards feature:
* Realistic 3D opening envelope with a custom-stamped ruby/pastel wax seal.
* Heartfelt, beautifully typeset letters with Polaroid photos optimized from camera raw assets (`LDT05840.JPEG` for Mother, `LDT05373.JPEG` for Sister).
* Seamless background music player with instant unlock on entry/tap.
* Responsive layouts tailored for mobile viewports (iPhone, Android) and desktop.
* Direct standalone URLs hosted via GitHub Pages.

---

## 2. Information Architecture & URL Routing

The project resides in the existing repository `danglio/tang-be-dau` with the following directory structure:

```
4.20:10/
├── index.html                 # Existing card for Bé Đậu
├── assets/                    # Shared and existing assets
│   ├── ky1.jpg, ky2.jpg
│   ├── music.mp3, music2.mp3, music3.mp3
│   ├── me_photo.jpg           # Compressed & web-optimized from /Users/admin/Downloads/LDT05840.JPEG
│   ├── chi_photo.jpg          # Compressed & web-optimized from /Users/admin/Downloads/LDT05373.JPEG
│   ├── music_me.mp3           # "Ước Mơ Của Mẹ" / "Mẹ Yêu" acoustic
│   └── music_chi.mp3          # "Bật Tình Yêu Lên" / "Một Ngày Hay Trăm Năm" acoustic
├── me/
│   └── index.html             # Dedicated card for Mother
└── chi/
    └── index.html             # Dedicated card for Sister
```

---

## 3. Detailed Specifications

### 3.1 Web for Mother (`me/index.html`)
* **Color Palette:** Warm Rose Gold (`#E8927C`), Soft Amber/Peach (`#FDF6F0`, `#F5D0C5`), Ruby Red Wax Seal (`#B33951`).
* **Particle Effects:** Floating pink rose petals and subtle golden starlight particles on HTML5 canvas.
* **Wax Seal:** Ruby wax medallion stamped with *"Gửi Mẹ Yêu ❤️"*.
* **Letter Content:**
  * Sincere, emotional gratitude honoring Mom's sacrifices and unconditional love.
  * Wishes for Mom's health, enduring happiness, youthfulness, and inner peace.
  * High-res Polaroid photo (`assets/me_photo.jpg`) with an elegant floral washi tape and cursive caption: *"Mẹ là người phụ nữ tuyệt vời nhất trần đời"*
* **Interactive Widgets:**
  * **"💖 Nạp 10,000 lời chúc sức khỏe":** Animated particle counter bursting golden hearts.
  * **"🎁 Phiếu đặc quyền của Mẹ":** Interactive voucher unfolding a special promise: *"Hôm nay Mẹ chỉ việc nghỉ ngơi và thư giãn, mọi việc cứ để con lo!"*
* **Music:**
  * Track: Acoustic ballad *"Ước Mơ Của Mẹ"* / *"Mẹ Yêu"*.
  * Mini disc player with spinning vinyl and auto-trigger on first user interaction.

### 3.2 Web for Sister (`chi/index.html`)
* **Color Palette:** Lavender Lilac (`#9D8DF1`, `#E6E1FA`), Baby Pink (`#FF92A5`), Soft Pastel Mint (`#BEE3DB`).
* **Particle Effects:** Floating sparkles, cute pastel hearts, and twinkling stars.
* **Wax Seal:** Lavender pastel wax seal stamped with *"Gửi Chị Hai 💌"*.
* **Letter Content:**
  * Warm, humorous, sibling-love tone praising Sister's charm, beauty, and kindness.
  * Wishing Sister skyrocketing success, wealth, glowing skin, happiness, and shopping sprees.
  * Cute Polaroid photo (`assets/chi_photo.jpg`) with colorful washi tape and caption: *"Chị hai xinh đẹp, tài năng số 1"*
* **Interactive Widgets:**
  * **"🧋 Ting ting 1 ly trà sữa full topping":** Interactive boba cup animation with joyful sound and sparkles.
  * **"🎫 Voucher sai vặt em 1 ngày":** Playful coupon granting Sister 1 day of bossing the younger sibling around.
  * **"🍀 Rút quẻ may mắn cho Chị":** Random positive fortune draw (*"Tăng lương x2", "Thăng chức vù vù", "Sớm có người yêu tâm lý giàu có", "Da luôn căng bóng"*).
* **Music:**
  * Track: Cheerful acoustic pop *"Bật Tình Yêu Lên"* / *"Một Ngày Hay Trăm Năm"*.
  * Floating vinyl player with auto-play on first touch.

---

## 4. Technical Implementation & Asset Processing

1. **Asset Processing:**
   * Downscale and optimize `LDT05840.JPEG` (11.8MB) to `assets/me_photo.jpg` (~200KB, max width 1200px, high JPEG quality) for instantaneous loading on mobile.
   * Downscale and optimize `LDT05373.JPEG` (10.6MB) to `assets/chi_photo.jpg` (~200KB, max width 1200px, high JPEG quality).
   * Obtain clean acoustic audio tracks:
     * `assets/music_me.mp3`: Official acoustic version of "Ước Mơ Của Mẹ".
     * `assets/music_chi.mp3`: Official acoustic/chill version of "Bật Tình Yêu Lên".
2. **Performance & Mobile First:**
   * Viewport meta tags configured for notch and dynamic island (iOS Safari).
   * Zero render-blocking scripts, Google Fonts preloaded, Tailwind CSS via CDN.
   * Audio unlocked upon first user interaction without intrusive popups.
3. **Deployment:**
   * Git commit & push to GitHub repository `danglio/tang-be-dau`.
   * Live URLs available under standard GitHub Pages tree.

---

## 5. Verification & Testing Criteria

* [ ] Both `LDT05840.JPEG` and `LDT05373.JPEG` correctly converted and displayed without distortion.
* [ ] Audio plays cleanly on iOS Safari and Android Chrome upon opening the envelope or tapping anywhere.
* [ ] 3D envelope fold and wax seal animations render at 60 FPS.
* [ ] All interactive buttons (wishes, vouchers, boba tea) give instant visual feedback with confetti bursts.
* [ ] GitHub Pages build passes with HTTP 200 on both `/me/` and `/chi/`.
