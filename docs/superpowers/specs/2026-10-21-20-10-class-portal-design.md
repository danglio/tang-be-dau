# Design Document: 20/10 Interactive Portal for University Freshman Class (47 Female Students)

**Date:** 2026-10-21  
**Author:** Antigravity AI  
**Status:** Approved by User  
**Target Deployment:** GitHub Pages (`https://danglio.github.io/tang-lop/`)

---

## 1. Overview & Objectives

In celebration of Vietnamese Women's Day (20/10), this project creates a dedicated, high-energy, and deeply thoughtful interactive web portal designed specifically for **47 female freshman university students** ("Tân sinh viên năm nhất Đại học").

### Key Goals:
1. **Full Class Representation:** Every single one of the 47 female students from the official class roster has an exclusive personal profile and custom-addressed 3D letter.
2. **Freshman University Vibe:** Tailored themes addressing university life—acing freshman prerequisites (Triết học Mác-Lênin, Toán cao cấp), securing 4.0 GPA / A+ scholarships, surviving assignment deadlines, and staying energetic & radiant.
3. **Instant Search & Direct Sharing:** A fast real-time search bar to find any classmate, plus direct shareable URLs (`https://danglio.github.io/tang-lop/?id=18` or `?name=Lê+Ngọc+Gia+Hân`) so a link sent via Zalo/Messenger immediately unfolds that student's personalized letter upon opening.
4. **Interactive University Widgets:** Boba delivery for deadline fuel, college course fortune-drawing ("Rút quẻ học phần"), and a boy-squad heart booster.
5. **Mobile-First & Instant Audio:** Smooth 60fps animations on iPhone/Android, zero lag, and background playlist with gesture unlock.

---

## 2. Class Roster Data (47 Students)

The 47 female students transcribed verbatim from the provided class sheets:

| ID | Full Name | First Name / Call Name |
|---|---|---|
| 1 | Trần Gia Khánh | Gia Khánh |
| 2 | Lê Võ Xuân Mai | Xuân Mai |
| 3 | Lê Tuệ Giang | Tuệ Giang |
| 4 | Trần Thị Phương Như | Phương Như |
| 5 | Lê Thị Diễm Thuý | Diễm Thuý |
| 6 | Nguyễn Thị Thanh Tuyền | Thanh Tuyền |
| 7 | Trần Thị Thanh Thuận | Thanh Thuận |
| 8 | Trần Ngọc Ái My | Ái My |
| 9 | Trần Thị Thanh Trúc | Thanh Trúc |
| 10 | Nguyễn Bích Huỳnh | Bích Huỳnh |
| 11 | Nguyễn Thị Ánh Diễm | Ánh Diễm |
| 12 | Nguyễn Hồ Hà My | Hà My |
| 13 | Phan Như Hảo | Như Hảo |
| 14 | Nguyễn Thị Hồng Thu | Hồng Thu |
| 15 | Trần Tri Diệu Châu | Diệu Châu |
| 16 | Trần Thị Kim Xuyến | Kim Xuyến |
| 17 | Trần Hoán My | Hoán My |
| 18 | Lê Ngọc Gia Hân | Gia Hân |
| 19 | Nguyễn Trần Gia Linh | Gia Linh |
| 20 | Lê Thị Cẩm Tú | Cẩm Tú |
| 21 | Huỳnh Khánh Vy | Khánh Vy |
| 22 | Phạm Vũ Xuân Thương | Xuân Thương |
| 23 | Đào Thị Phi Phụng | Phi Phụng |
| 24 | Lê Ngọc Bảo Khanh | Bảo Khanh |
| 25 | Nguyễn Xuân Quỳnh | Xuân Quỳnh |
| 26 | Lê Sĩ Kiều My | Kiều My |
| 27 | Hoàng Nguyễn Phương Linh | Phương Linh |
| 28 | Phạm Thuỳ Linh | Thuỳ Linh |
| 29 | Trương Ánh Ngọc | Ánh Ngọc |
| 30 | Đởm Ngọc Bảo Châu | Bảo Châu |
| 31 | Võ Thị Hồng Nhung | Hồng Nhung |
| 32 | Nguyễn Lương Như Quỳnh | Như Quỳnh |
| 33 | Phùng Ngọc Thảo Ngân | Thảo Ngân |
| 34 | Phạm Ngọc Lam Linh | Lam Linh |
| 35 | Nguyễn Vĩnh Nam Uyên | Nam Uyên |
| 36 | Tô Thu Thảo | Thu Thảo |
| 37 | Nguyễn Phương Gia Hân | Gia Hân |
| 38 | Hồ Thị Bích Thuỷ | Bích Thuỷ |
| 39 | Hoàng Anh Thư | Anh Thư |
| 40 | Huỳnh Ngọc Phương Trinh | Phương Trinh |
| 41 | Huỳnh Ngọc Thuy Quyên | Thuy Quyên |
| 42 | Dương Nguyễn Bảo Hân | Bảo Hân |
| 43 | Nguyễn Phương Thảo | Phương Thảo |
| 44 | Đoàn Huyền Trân | Huyền Trân |
| 45 | Tống Nguyễn Thảo My | Thảo My |
| 46 | Trương Ngọc Ánh | Ngọc Ánh |
| 47 | Lê Thị Anh Thư | Anh Thư |

---

## 3. UI/UX & Information Architecture

### 3.1 Hero Header
* **Title:** *"Chúc Mừng 20/10 • 47 Bông Hoa Tân Sinh Viên"* 🎓✨
* **Subtitle:** *"Món quà đặc biệt từ tập thể các bạn nam gửi tặng những cô gái tài năng, xinh đẹp của lớp mình!"*
* **Music Player:** Mini vinyl disc with rotating animation and instant play/pause.
* **Canvas Effect:** Floating cherry blossoms, soft sparkles, and glowing particle ambient effects.

### 3.2 Real-time Search & Filter Bar
* Input box: *"🔍 Nhập tên bạn để tìm thư riêng (vd: Gia Hân, Phương Linh, Thảo...)"*
* Fast filter matching full name or first name with instant count badge ("Tìm thấy X bạn").
* One-click "Tất cả" reset button.

### 3.3 47 Student Cards Grid
* Responsive CSS grid (2 columns on mobile, 3-4 columns on tablet/desktop).
* Card contains: Student badge (`#01`, `#02`...), student avatar glyph/icon, full name, and a glowing CTA button *"Mở Thư Riêng 💌"*.

### 3.4 Interactive 3D Envelope Modal
* Upon clicking any student card (or landing on `?id=N`):
  * A full-screen backdrop modal transitions in smoothly.
  * Realistic 3D Envelope with perspective, folding top flap, and custom-embossed wax seal stamped: **"Gửi [Tên Bạn] 💌"**.
  * Chạm / click vào con dấu sáp -> Nắp phong bì mở ra với hiệu ứng pháo hoa giấy (confetti) và nhạc nền tự động cất lên.
  * **Lá thư mở ra:**
    * Tiêu đề: *"Thân gửi [Họ và Tên] 🌸"*
    * Lời chúc đại học hóm hỉnh & ngọt ngào:
      * Chúc kỳ đầu đại học thuận buồm xuôi gió, không bỡ ngỡ trước giảng đường lớn.
      * Học phần đại cương (Triết, Toán cao cấp, Kinh tế...) nhẹ nhàng qua môn A+, điểm danh không lo vắng mặt.
      * Săn học bổng xịn, GPA chạm mốc 4.0, ra trường đúng hạn.
      * Nhan sắc ngày càng rực rỡ, da luôn căng bóng, năng lượng tích cực tràn đầy.
    * Nút *"Sao chép link gửi cho [Tên]"*: Tự động copy link trực tiếp vào clipboard kèm thông báo toast.
    * Nút *"Đóng & Chọn bạn khác"*.

### 3.5 College-Life Interactive Widgets
1. **🎓 Rút Quẻ Học Phần Đại Học:**
   * Interactive shuffle stick with 6 realistic college fortunes: *"Học phần A+ không cần thi lại"*, *"Giảng viên dễ tính, điểm quá trình 10"*, *"Săn trọn học bổng khuyến khích học tập"*, *"Deadline hoàn thành trước hạn 3 ngày"*, *"Điểm danh không bao giờ dính trúng lúc vắng"*...
2. **🧋 Ting Ting Trà Sữa Chạy Deadline:**
   * Interactive boba cup with bouncing boba pearls, toppings, and Web Audio API crystal chime.
3. **💖 Nạp 100,000 Trái Tim Từ Hội Nam Sinh:**
   * Rapid heart counter bursting rainbow hearts across the screen.

---

## 4. Technical Architecture & File Structure

A dedicated standalone repository `tang-lop` hosted at `https://danglio.github.io/tang-lop/`:

```
tang-lop/
├── index.html         # Complete self-contained single page application
└── assets/
    └── music.mp3      # Uplifting youth acoustic / Gen Z pop soundtrack
```

* **No build step required:** Pure HTML5, Tailwind CSS via CDN, FontAwesome 6, Google Fonts, and Vanilla JavaScript.
* **Deep-linking:** Reads `window.location.search` for `?id=N` or `?name=...` to automatically open the designated envelope.

---

## 5. Verification & Testing Criteria

* [ ] All 47 students present in data and searchable.
* [ ] Search bar filters smoothly on typing with zero lag.
* [ ] Direct URL parameters (`?id=18` and `?name=Gia+Hân`) immediately open the corresponding student's letter.
* [ ] 3D Envelope animation renders smoothly without visual glitches.
* [ ] Audio unlocks reliably on first tap or envelope trigger.
* [ ] GitHub Pages builds cleanly and returns HTTP/2 200 on `https://danglio.github.io/tang-lop/`.
