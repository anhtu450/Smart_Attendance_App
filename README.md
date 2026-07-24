# Smart Attendance App (Hệ thống Điểm danh Thông minh)

## Giới thiệu
Smart Attendance App là ứng dụng điểm danh thông minh tích hợp công nghệ trí tuệ nhân tạo (AI) nhận diện khuôn mặt. 
Dự án này được thiết kế dành riêng cho giảng viên, giúp tự động hóa quá trình điểm danh lớp học chỉ qua một lần chụp ảnh tập thể. Hệ thống sử dụng Backend được viết bằng FastAPI để xử lý ảnh tốc độ cao kết hợp cùng lõi AI nhận diện khuôn mặt mạnh mẽ.

### Cấu trúc dự án hiện tại
* `face_recognition/`: Thư mục chứa lõi AI nhận diện khuôn mặt.
* `main.py`: File khởi tạo Backend Server (FastAPI).
* `requirements.txt`: Chứa danh sách các thư viện Python cần thiết.
* `LICENSE`: Giấy phép mã nguồn của dự án.

## Hướng dẫn Cài đặt
Yêu cầu hệ thống phải cài đặt sẵn **Python**.

1. Mở Terminal/Command Prompt tại thư mục gốc của dự án (thư mục chứa file `main.py`).
2. Chạy lệnh sau để cài đặt tất cả các thư viện phụ thuộc:
   ```bash
   pip install -r requirements.txt
   ```

## Hướng dẫn Khởi chạy Server
Để khởi động Backend API server cục bộ, sử dụng lệnh sau:
```bash
uvicorn main:app --reload
```
Sau khi server chạy thành công, bạn có thể:
- Truy cập Server tại: `http://localhost:8000`
- Xem tài liệu API tự động (Swagger UI) tại: `http://localhost:8000/docs`

## Credit & Tài liệu tham khảo
Phần lõi AI nhận diện khuôn mặt của dự án này được xây dựng dựa trên thư viện mã nguồn mở [face_recognition](https://github.com/ageitgey/face_recognition) do tác giả **Adam Geitgey** phát triển (dựa trên dlib). 
Xin gửi lời cảm ơn đến Adam Geitgey vì đã tạo ra một công cụ AI vô cùng hữu ích và dễ sử dụng cho cộng đồng!
