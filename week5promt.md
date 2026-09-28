# Nhật ký Prompt - Tuần 5

**1. Yêu cầu làm mịn hiệu ứng cuộn và Hover**
- **Prompt:** "Làm thế nào để tạo hiệu ứng hover có bóng đổ và nút bấm nhích lên 3px, đồng thời làm mượt chuyển động bằng cubic-bezier?"
- **Kết quả:** Đã áp dụng `transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1), box-shadow 0.3s ease;` vào class `.button`.

**2. Tối ưu hiệu năng Animation (Refactoring)**
- **Prompt:** "Thay vì dùng width để chạy thanh kỹ năng gây giật lag, hãy dùng transform scaleX để tối ưu performance."
- **Kết quả:** Chuyển sang dùng `transform: scaleX(0)` đến `scaleX(1)` kết hợp `transform-origin: left;` giúp thanh Skill bar chạy mượt mà ở 60fps.

**3. Khắc phục lỗi hiển thị nền tối**
- **Prompt:** "Chữ đang bị đen trên nền tối, hãy chuyển sang chữ trắng và xám sáng, đồng thời tích hợp form điền thông tin Glassmorphism."
- **Kết quả:** Cập nhật biến CSS `--text-dark: #ffffff;` và làm form liên hệ với hiệu ứng kính mờ `backdrop-filter: blur(12px)`.