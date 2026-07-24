<div align="center">

# HỆ THỐNG ĐIỂM DANH THÔNG MINH BẰNG AI
**Khóa luận / Đồ án tốt nghiệp chuyên ngành Công nghệ Thông tin**  
*Trường Đại học Đại Nam (DNU)*

</div>

<br/>

## 📋 THÔNG TIN ĐỀ TÀI
- **Tên đề tài:** Phát triển ứng dụng điểm danh thông minh tích hợp công nghệ AI nhận diện khuôn mặt.
- **Giảng viên hướng dẫn:** TS. Trần Quý Nam
- **Sinh viên thực hiện:** Trần Anh Tú (MSSV: 1771020706)
- **Mã nguồn dự án:** [GitHub - anhtu450](https://github.com/anhtu450/Smart_Attendance_App)


---

## 🚀 GIỚI THIỆU DỰ ÁN
**Smart Attendance App** là một giải pháp điểm danh tự động dành cho Giảng viên thông qua công nghệ Trí tuệ Nhân tạo (AI). Thay vì điểm danh gọi tên truyền thống tốn thời gian, hệ thống cho phép giảng viên chụp một bức ảnh tập thể của lớp. Hệ thống sẽ tự động phân tích ảnh, nhận diện khuôn mặt từng sinh viên và trả về kết quả điểm danh ngay lập tức với độ chính xác cao.

### ✨ Các tính năng chính
- 👤 **Điểm danh AI (One-click):** Nhận diện khuôn mặt sinh viên qua ảnh chụp lớp học (cá nhân hoặc tập thể).
- ✏️ **Hiệu chỉnh thủ công:** Cho phép Giảng viên cập nhật trạng thái (Có mặt / Vắng / Đi muộn) nếu sinh viên bị khuất mặt.
- 📊 **Quản lý dữ liệu:** Quản lý thông tin Lớp học phần, Danh sách sinh viên và Lịch sử điểm danh.
- 🕒 **Đồng bộ thời gian thực:** Lưu trữ dữ liệu tức thì vào hệ thống CSDL tập trung.
- ⚡ **Kiến trúc Microservices:** Tách biệt xử lý AI và xử lý nghiệp vụ Backend giúp tối ưu hiệu năng.

---

## 🛠️ CÔNG NGHỆ SỬ DỤNG (TECH STACK)

### 1. Frontend (Mobile App)
- **Framework:** `Flutter` (Dart) - Xây dựng ứng dụng di động đa nền tảng (Android/iOS) cho Giảng viên.

### 2. Core Backend API
- **Framework:** `ASP.NET Core Web API` (C# / .NET) - Xử lý logic nghiệp vụ, phân quyền và kết nối CSDL.
- **Database:** `Microsoft SQL Server` - Lưu trữ dữ liệu người dùng, lớp học, sinh viên và lịch sử điểm danh.

### 3. AI Microservice
- **Framework:** `FastAPI` (Python) - Máy chủ API hiệu năng cao xử lý các yêu cầu AI.
- **AI Core:** `face_recognition` (dựa trên thư viện C++ `dlib`) - Trích xuất 128 đặc trưng (face encodings) để so sánh khuôn mặt.
- **Computer Vision:** `OpenCV`, `Pillow` (PIL) - Tiền xử lý và tối ưu hóa hình ảnh đầu vào.

---

## 📁 CẤU TRÚC THƯ MỤC DỰ ÁN

```text
Smart_Attendance_App/
│
├── AI_Service/                 # Microservice xử lý AI (Python FastAPI)
│   ├── face_recognition/       # Lõi thư viện bóc tách & tính vector khuôn mặt
│   ├── main.py                 # File khởi chạy FastAPI Server
│   ├── requirements.txt        # Danh sách thư viện Python
│   └── LICENSE
│
├── Backend_API/                # Core Backend Server (ASP.NET Core C#)
│   ├── Controllers/            # API Endpoints
│   ├── Models/                 # Database Entities & DTOs
│   └── appsettings.json        # Cấu hình kết nối SQL Server
│
└── Mobile_App/                 # Ứng dụng di động (Flutter)
    ├── lib/                    # Mã nguồn Giao diện & Logic UI
    └── pubspec.yaml            # Cấu hình dependencies Flutter
```

---

## ⚙️ HƯỚNG DẪN CÀI ĐẶT & CHẠY DỰ ÁN

### 1. Yêu cầu hệ thống
- **Python 3.10+** (Cho AI Microservice).
- **.NET SDK 8.0+** (Cho Backend C#).
- **Flutter SDK 3.x** (Cho Mobile App).
- **Microsoft SQL Server**.
- (Windows) **Visual Studio C++ Build Tools** để biên dịch thư viện dlib.

### 2. Cài đặt & Khởi chạy AI Microservice (Python)
```bash
# Di chuyển vào thư mục AI Service
cd AI_Service

# Tạo & Kích hoạt môi trường ảo (Tùy chọn)
python -m venv venv
venv\Scripts\activate      # Trên Windows
# source venv/bin/activate # Trên MacOS/Linux

# Cài đặt thư viện
pip install -r requirements.txt

# Khởi chạy FastAPI Server (Chạy tại http://localhost:8000)
uvicorn main:app --reload
```
*Tài liệu API Swagger tự động: http://localhost:8000/docs*

### 3. Cài đặt & Khởi chạy Backend API (C#)
```bash
# Di chuyển vào thư mục Backend
cd Backend_API

# Cập nhật Database Migration (SQL Server)
dotnet ef database update

# Khởi chạy Server
dotnet run
```

### 4. Khởi chạy Mobile App (Flutter)
```bash
# Di chuyển vào thư mục Mobile App
cd Mobile_App

# Tải các gói phụ thuộc
flutter pub get

# Chạy app trên thiết bị thật hoặc máy ảo
flutter run
```

---

## 📚 TÀI LIỆU THAM KHẢO & CREDIT
- Phần xử lý AI được xây dựng dựa trên mã nguồn mở [face_recognition](https://github.com/ageitgey/face_recognition) của tác giả **Adam Geitgey**.
- Thuật toán nhận diện được cung cấp sức mạnh từ thư viện [dlib](http://dlib.net/) của tác giả **Davis King**.
- Xin gửi lời cảm ơn đến các tác giả mã nguồn mở và Thầy hướng dẫn đã hỗ trợ hoàn thành đồ án này.
