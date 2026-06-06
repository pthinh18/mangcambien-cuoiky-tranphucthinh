# Tiểu luận Mạng cảm biến

**Đề tài:** Voice control đèn LED RGB

**Sinh viên thực hiện:** Trần Phúc Thịnh

**MSSV:** N23DCCI069

## 1. Mô tả thư mục
*   **`browser/`**: Chứa mã nguồn giao diện (HTML/JS) và mô hình đóng gói dưới dạng WebAssembly. Cho phép chạy kiểm thử AI thời gian thực (Real-time inference) trực tiếp trên trình duyệt thông qua Microphone.
*   **`node/`**: Môi trường thực thi Node.js để kiểm thử và chạy mô hình suy luận cục bộ (Local inference) thông qua Command Line.
*   **`edge-impulse-sdk/`**: Bộ thư viện mã nguồn mở lõi C++ (SDK) của Edge Impulse. Phụ trách tính toán các thuật toán xử lý tín hiệu số (DSP) phức tạp và vận hành mạng nơ-ron.
*   **`model-parameters/`**: Chứa các tệp Header (`.h`) định nghĩa thông số cấu hình cốt lõi của hệ thống, bao gồm các tham số trích xuất đặc trưng MFCC và thông tin các nhãn phân loại.
*   **`tflite-model/`**: Lưu trữ mô hình AI cốt lõi đã được lượng tử hóa (Quantized INT8) dưới định dạng TensorFlow Lite for Microcontrollers, tối ưu hóa triệt để dung lượng RAM/Flash cho các dòng vi điều khiển tài nguyên thấp.
*   **`CMakeLists.txt`**: Tệp tin cấu hình biên dịch tự động, hướng dẫn trình biên dịch cách liên kết toàn bộ mã nguồn C++ trên lại với nhau để sẵn sàng nạp xuống phần cứng.
*   **`.gitignore`**: Tệp cấu hình loại bỏ các tệp tin tạm thời và tệp nhị phân (`.o`, `.bin`, `build/`) sinh ra trong quá trình biên dịch, giúp kho lưu trữ luôn sạch sẽ và nhẹ gọn.
  

## 2. Hướng dẫn chạy và Demo hệ thống
Do cơ chế bảo mật của Edge Impulse yêu cầu tài khoản đăng nhập để test Real-time, cách tốt nhất để đánh giá mô hình là xem Video Demo thực tế.
👉 **Link Video Demo hệ thống:** (https://youtu.be/Z-HyyZnEpp0)
Hoặc muốn test offline: Mở file index.html trong thư mục browser bằng trình duyệt web.
**Nếu giảng viên muốn test trực tiếp trên hệ thống Edge Impulse:**
1. Truy cập dự án Public tại: https://studio.edgeimpulse.com/public/1019119/live
2. Bấm nút `Clone this project` ở góc phải để sao chép dự án về tài khoản cá nhân.
3. Chuyển đến tab **Live classification**, kết nối Micro và đọc các từ khóa: `phúc thịnh`, `màu đỏ`, `màu xanh`, `màu trắng`, `noise`.

## 3. Các phụ thuộc (Dependencies)
* Mô hình huấn luyện: 1D-CNN (Convolutional Neural Network).
* Trình duyệt web hỗ trợ WebAssembly (Google Chrome, Microsoft Edge...).
