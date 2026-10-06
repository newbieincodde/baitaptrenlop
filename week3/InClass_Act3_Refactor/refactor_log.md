# Báo Cáo Hoạt Động 3: Debug & Refactor Mã Nguồn CSS (Tuần 3)

## 1. Đoạn mã lỗi / dư thừa ban đầu do AI sinh ra (Code chưa tối ưu):
```css
/* AI tự sinh mã dư thừa do thói quen cũ */
.sidebar {
  float: left; /* DƯ THỪA: Đã dùng CSS Grid thì không cần float */
  width: 250px;
  margin-top: 10px;
  margin-bottom: 10px;
  margin-left: 0px;
  margin-right: 0px; /* DƯ THỪA: Không dùng shorthand */
}

.skills-container {
  display: flex;
  display: -webkit-flex; /* DƯ THỪA trên các trình duyệt hiện đại */
  margin-right: 15px;
  margin-bottom: 15px; /* Có thể thay bằng gap */
}
```

## 2. Đoạn mã sau khi Refactor (Clean Code):
```css
:root {
  --spacing-gap: 15px;
  --sidebar-width: 250px;
}

/* Loại bỏ hoàn toàn float và dùng Shorthand margin */
.sidebar {
  width: var(--sidebar-width);
  margin: 10px 0;
}

/* Quản lý khoảng cách bằng thuộc tính gap hiện đại thay cho margin */
.skills-container {
  display: flex;
  flex-wrap: wrap;
  gap: var(--spacing-gap);
}
```

## 3. Checklist kiểm tra theo giáo trình:
- [x] Đã loại bỏ hoàn toàn thuộc tính float/table lỗi thời.
- [x] Quản lý khoảng cách giữa các khối bằng thuộc tính gap.
- [x] Sử dụng Shorthand properties cho margin/padding.