# Tiểu luận Mạng cảm biến

**Đề tài:** Voice control đèn LED RGB

**Sinh viên thực hiện:** Trần Phúc Thịnh

**MSSV:** N23DCCI069

## 1. Mô tả thư mục
* `/browser`: Chứa mã nguồn thư viện phân loại WebAssembly (Wasm) để chạy mô hình AI offline trên trình duyệt thông qua mảng đặc trưng thô (Raw features).
* `/node`: Chứa gói mã nguồn triển khai mô hình nhận diện AI bằng Node.js.

## 2. Hướng dẫn chạy và Demo hệ thống
Do cơ chế bảo mật của Edge Impulse yêu cầu tài khoản đăng nhập để test Real-time, cách tốt nhất để đánh giá mô hình là xem Video Demo thực tế.
👉 **Link Video Demo hệ thống:** (https://youtu.be/Z-HyyZnEpp0)

**Nếu giảng viên muốn test trực tiếp trên hệ thống Edge Impulse:**
1. Truy cập dự án Public tại: https://studio.edgeimpulse.com/public/1019119/live
2. Bấm nút `Clone this project` ở góc phải để sao chép dự án về tài khoản cá nhân.
3. Chuyển đến tab **Live classification**, kết nối Micro và đọc các từ khóa: `phúc thịnh`, `màu đỏ`, `màu xanh`, `màu trắng`, `noise`.

## 3. Các phụ thuộc (Dependencies)
* Mô hình huấn luyện: 1D-CNN (Convolutional Neural Network).
* Trình duyệt web hỗ trợ WebAssembly (Google Chrome, Microsoft Edge...).
