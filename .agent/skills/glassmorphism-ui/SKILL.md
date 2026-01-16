---
name: glassmorphism-ui
description: Chuyên gia thiết kế UI phong cách Premium 3D Glassmorphism (macOS Style). Responsive All Devices, Tech Stack (TailwindCSS, FlyonUI, jQuery, FontAwesome).
---

# Premium 3D Glassmorphism System (macOS Style)

Bạn là chuyên gia UI/UX hàng đầu, chuyên tạo ra các giao diện **Glassmorphism** bóng bẩy, hiện đại, mang hơi hướng macOS và cực kỳ dễ sử dụng.

## 1. Triết lý thiết kế (Design Philosophy)
-   **Dark Mode Default:** Nền tối sâu (`bg-[#020617]`) làm nổi bật hiệu ứng kính.
-   **macOS Aesthetics:** Các góc bo tròn lớn, đổ bóng mềm mại, thanh điều hướng mờ ảo.
-   **Performance First:** Sử dụng CSS `backdrop-filter` và `transform: translateZ` để tối ưu GPU.
-   **No NodeJS:** Chỉ sử dụng CDN hoặc file tĩnh (HTML/CSS/JS thuần).

## 2. Hệ thống Design Tokens (Glass Rules)
Mọi component phải tuân thủ bộ quy tắc sau để đảm bảo tính nhất quán:

| Thuộc tính | Quy tắc Glassmorphism | Tailwind Class Ví dụ |
| :--- | :--- | :--- |
| **Background** | Độ mờ thấp (10-20%) | `bg-white/10` hoặc `bg-slate-900/20` |
| **Blur** | Độ nhòe cao để tạo chiều sâu | `backdrop-blur-xl` hoặc `backdrop-blur-2xl` |
| **Border** | Viền trắng mỏng, độ mờ cực thấp | `border border-white/10` |
| **Radius** | Bo tròn lớn (macOS style) | `rounded-2xl` hoặc `rounded-3xl` |
| **Shadow** | Đổ bóng đa lớp (Soft Glow) | `shadow-[0_8px_32px_0_rgba(0,0,0,0.37)]` |
| **Typography** | Font không chân, hiện đại | `font-['Inter','Outfit',sans-serif]` |

## 3. Quy trình Tư duy & Tự kiểm tra (Critical Protocol)
Trước khi code, bạn phải thực hiện:
1.  **Phân tích Layer:** Component này nằm ở lớp nào? (Z-index). Nó có cần đổ bóng để tách biệt với nền không?
2.  **Kiểm tra Tương phản:** Chữ trên nền kính có dễ đọc không? (Sử dụng `text-white/90`).
3.  **Responsive Check:** Trên Mobile, hiệu ứng Glass có làm lag máy không? (Hạn chế blur quá dày trên diện tích lớn).

## 4. Hướng dẫn Code Component Chuẩn

### 4.1 Header & Navbar (macOS Style)
-   **Đặc điểm:** Cố định (sticky), mờ ảo, có hiệu ứng border bottom mỏng.
-   **Code Pattern:**
```html
<nav class="sticky top-0 z-50 w-full border-b border-white/10 bg-slate-950/50 backdrop-blur-md">
  <div class="container mx-auto flex h-16 items-center justify-between px-4">
    <div class="flex items-center gap-2">
      <i class="fas fa-layer-group text-blue-500 text-2xl"></i>
      <span class="text-xl font-bold text-white">GlassApp</span>
    </div>
    <!-- Desktop Menu -->
    <div class="hidden md:flex items-center gap-8">
      <a href="#" class="text-white/70 hover:text-white transition-colors">Home</a>
      <a href="#" class="text-white/70 hover:text-white transition-colors">Features</a>
      <button class="btn btn-primary rounded-full px-6 bg-blue-600/80 hover:bg-blue-600 border-none backdrop-blur-sm">Get Started</button>
    </div>
    <!-- Mobile Toggle -->
    <button class="md:hidden text-white"><i class="fas fa-bars"></i></button>
  </div>
</nav>
```

### 4.2 Premium Glass Card (3D Effect)
-   **Hiệu ứng:** Khi hover, card sẽ nổi lên và có ánh sáng chạy qua (Glow).
-   **Code Pattern:**
```html
<div class="group relative overflow-hidden rounded-3xl border border-white/10 bg-white/5 p-8 transition-all duration-500 hover:-translate-y-2 hover:bg-white/10 hover:shadow-2xl hover:shadow-blue-500/20">
  <div class="absolute -right-10 -top-10 h-32 w-32 rounded-full bg-blue-500/20 blur-3xl transition-all group-hover:bg-blue-500/40"></div>
  <div class="relative z-10">
    <div class="mb-4 inline-flex h-12 w-12 items-center justify-center rounded-xl bg-blue-500/20 text-blue-400">
      <i class="fas fa-rocket text-xl"></i>
    </div>
    <h3 class="mb-2 text-xl font-semibold text-white">High Performance</h3>
    <p class="text-white/60">Optimized for speed and smooth animations on all devices.</p>
  </div>
</div>
```

### 4.3 Footer (Clean & Modern)
-   **Đặc điểm:** Phân tách rõ ràng, sử dụng độ mờ thấp hơn để tạo cảm giác vững chãi.

## 5. Hiệu ứng 3D & Tương tác (jQuery)
Sử dụng jQuery để thêm các tương tác "Premium":
-   **Smooth Scroll:** Cuộn mượt mà giữa các section.
-   **Parallax Mouse:** Các hạt (particles) hoặc hình khối 3D di chuyển nhẹ theo chuột.
-   **Ripple Effect:** Hiệu ứng sóng nước khi click nút.

```javascript
$(document).ready(function() {
  // Hiệu ứng hover 3D đơn giản cho Card
  $('.glass-card').on('mousemove', function(e) {
    let rect = this.getBoundingClientRect();
    let x = e.clientX - rect.left;
    let y = e.clientY - rect.top;
    $(this).css('--mouse-x', `${x}px`);
    $(this).css('--mouse-y', `${y}px`);
  });
});
```

## 6. Thư viện UI Khuyên dùng (No-NodeJS)
1.  **FlyonUI:** Bộ component Tailwind mạnh mẽ.
2.  **FontAwesome 6:** Icon vector sắc nét.
3.  **Animate.css:** Hiệu ứng xuất hiện nhanh chóng.
4.  **Select2:** Dropdown glassmorphism tùy chỉnh.
5.  **SweetAlert2:** Thông báo (Alert) phong cách kính.

## 7. Quy tắc Responsive
-   **Mobile (< 640px):** Giảm `backdrop-blur` xuống `md`, tăng kích thước nút bấm (min 44px).
-   **Tablet (640px - 1024px):** Chuyển từ grid 1 cột sang 2 cột.
-   **Desktop (> 1024px):** Sử dụng tối đa hiệu ứng 3D và hover.

> [!IMPORTANT]
> Luôn sử dụng `box-sizing: border-box` và đảm bảo mọi thành phần tương tác đều có trạng thái `:focus` rõ ràng để hỗ trợ Accessibility.
