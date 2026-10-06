# Báo cáo Thách thức: THE INTERACTIVE SHOWCASE (Tuần 5)

## 1. Ý tưởng thiết kế (Design Concept)
Trang web được thiết kế theo phong cách **Glassmorphism** (kính mờ) kết hợp với **Dark Theme**. Mục tiêu là mang lại trải nghiệm người dùng (UX) hiện đại, cao cấp và mượt mà, nhưng không làm phân tán sự chú ý vào nội dung chính.

## 2. Top 3 Prompts bậc thầy đã sử dụng

### Prompt 1: Tối ưu Micro-interactions & Cubic-bezier
> **Prompt:** *"Hãy thiết kế hiệu ứng Micro-interaction cho các nút bấm (.button và .btn-send). Khi hover phải nổi lên nhẹ (translateY) kèm theo hiệu ứng phát sáng (box-shadow neon). Yêu cầu quan trọng: Sử dụng hàm transition với `cubic-bezier(0.4, 0, 0.2, 1)` để chuyển động trông có độ nảy tự nhiên, và tuyệt đối không dùng thuộc tính top/left/margin để tránh lag khung hình."*
**Lý do:** Đáp ứng đúng tiêu chí tối ưu hiệu năng của môn học, sử dụng GPU Acceleration (`transform`) để giao diện mượt mà trên mobile.

### Prompt 2: Card Flip 3D
> **Prompt:** *"Tạo hiệu ứng lật thẻ (Card Flip) cho Sidebar Profile. Mặt trước hiển thị tên và Avatar, mặt sau hiển thị thông tin liên hệ. Khi hover vào vùng chứa thẻ, nó sẽ xoay 180 độ theo trục Y. Hãy đảm bảo chiều sâu 3D bằng thuộc tính `perspective: 1000px` và ẩn mặt sau lúc chưa lật bằng `backface-visibility: hidden`."*
**Lý do:** Tạo điểm nhấn Interactive (Tương tác) thú vị ngay từ ánh nhìn đầu tiên, giúp tiết kiệm không gian hiển thị nhưng vẫn chứa nhiều thông tin.

### Prompt 3: Intro Animation (Hoạt ảnh khởi tạo)
> **Prompt:** *"Hãy tạo một `@keyframes slideDownFade` cho thẻ Header. Khi trang vừa tải xong, Header sẽ trượt từ trên xuống (`translateY(-50px)` đến `0`) và mờ dần rõ lên (`opacity: 0` đến `1`). Thiết lập thời gian là 0.8s."*
**Lý do:** Đáp ứng đúng yêu cầu của mục số 1 trong thách thức Tuần 5: Dẫn dắt ánh mắt người dùng khi vừa truy cập trang.

## 3. Lỗi khó nhất đã gặp và cách xử lý
- **Hiện tượng:** Khi tích hợp Animation lật thẻ 3D và các thẻ có thư viện AOS, thẻ lật bị rách hình ảnh hoặc hiển thị không đúng trên Safari điện thoại.
- **Cách xử lý cùng AI:** Nhờ AI phân tích, nhóm phát hiện ra nguyên nhân là thiếu thuộc tính `-webkit-backface-visibility: hidden;` và phải gán `transform-style: preserve-3d;` chính xác cho thẻ con. Đồng thời, không đặt `overflow: hidden` ở vùng container bọc bên ngoài.
