# 🎮 FINAL PROJECT — GAME MÊ CUNG (MAZE GAME)

<div align="center">

![C++](https://img.shields.io/badge/C++-17-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![Platform](https://img.shields.io/badge/Platform-Windows-orange?style=for-the-badge&logo=windows&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![CTDL](https://img.shields.io/badge/CTDL%20%C3%81p%20D%E1%BB%A5ng-4-blueviolet?style=for-the-badge)

**Ứng dụng mô phỏng trò chơi Mê cung tương tác thời gian thực, tự động tạo ma trận liên thông và giải thuật tối ưu hóa đồ thị đồ sộ** [📌 Giới thiệu](#-giới-thiệu) · [🗂 Cấu trúc](#-cấu-trúc-dự-án) · [🧠 Cấu trúc dữ liệu](#-cấu-trúc-dữ-liệu--giải-thuật) · [⚙️ Cài đặt](#️-cài-đặt--chạy) · [🧪 Kiểm thử](#-hệ-thống-kiểm-thử-unit-tests)

</div>

---

## 📌 Giới Thiệu

Đồ án cuối kỳ môn **Cấu trúc Dữ liệu và Giải thuật (DSA)** thực hiện bởi sinh viên **Bùi Văn Nam** (MSSV: **2125110145**), lớp học phần **DSALab-HIT**. Dự án giải quyết trọn vẹn bài toán xây dựng trò chơi Maze Game trên giao diện dòng lệnh CLI thông qua các điểm nhấn kỹ thuật:

- ✅ **Sinh mê cung tự động:** Thuật toán đệ quy đào tường đảm bảo bản đồ luôn liên thông và duy nhất.
- ✅ **Cơ chế Hoàn tác (Undo):** Sử dụng cấu trúc danh sách liên kết tự định nghĩa để đi lùi bước chân thời gian thực.
- ✅ **Trình duyệt tự động:** Tích hợp đồng thời 2 giải thuật tìm kiếm đồ thị nền tảng BFS và DFS.
- ✅ **Lưu trữ tệp tin:** Hỗ trợ cơ chế serialization/deserialization ma trận trích xuất trực tiếp ra file `.txt`.
- ✅ **Chuẩn chỉnh học phần:** Tách file cấu trúc rõ ràng `.h`/`.cpp`, tích hợp sẵn 5 kịch bản Unit Test tự động.

---

## 🗂 Cấu Trúc Dự Án

Thư mục bài nộp được phân tách mô-đun hóa nghiêm ngặt theo đúng cấu trúc chuẩn của kho lưu trữ môn học:
MSSV2125110145_HoTenbuivannam_DeTaiGame Mê Cung (Maze Game)/
│
├── 📁 src/
│   ├── MazeGam.h        # Khai báo cấu trúc Point, Node và nguyên mẫu lớp MazeGame
│   ├── source.cpp       # Triển khai chi tiết logic toán học, xử lý file và giải thuật
│   └── cd.cpp           # Luồng điều khiển menu hệ thống chính (Hàm main)
│
├── 📁 tests/
│   └── test_cases.cpp   # Hệ thống tự động kích hoạt 5 kịch bản kiểm thử độc lập
│
└── README.md            # Tài liệu hướng dẫn kỹ thuật toàn diện này
---

## 🧠 Cấu Trúc Dữ Liệu & Giải Thuật

### ⏱ Bảng Phân Tích Độ Phức Tạp Hệ Thống

Để tối ưu hóa chi phí tài nguyên, hệ thống áp dụng phối hợp **4 cấu trúc dữ liệu** cốt lõi với hiệu năng vận hành cụ thể như sau:

| Thành Phần Kỹ Thuật | Cấu Trúc Dữ Liệu Sử Dụng | Vai Trò & Vị Trí Trong Mã Nguồn | Thời Gian (Worst) | Không Gian |
|---------------------|--------------------------|---------------------------------|-------------------|------------|
| **Khung lưới mê cung** | 2D Vector (`std::vector`) | Lưu trữ ma trận thực tế của bản đồ và các ký hiệu vật lý. | $O(1)$ truy cập | $O(W \times H)$ |
| **Sinh Maze & Giải DFS**| Ngăn xếp (`std::stack`) | Đào tường ngẫu nhiên và tìm đường duyệt theo chiều sâu. | $O(V + E)$ | $O(V)$ |
| **Tìm đường ngắn nhất**| Hàng đợi (`std::queue`) | Tìm đường cứu hộ theo cơ chế loang sóng chiều rộng (BFS).| $O(V + E)$ | $O(V)$ |
| **Cơ chế Hoàn tác (Undo)**| Danh sách liên kết đơn | Tự định nghĩa `HistoryNode` lưu chuỗi tọa độ bước chân. | $O(1)$ thêm/xóa | $O(K)$ bước |

---

## ⚙️ Cài Đặt & Chạy

### Yêu cầu hệ thống
- **Compiler:** g++ tương thích tiêu chuẩn C++17 trở lên.
- **Hệ điều hành:** Khuyến khích môi trường **Windows** (do chương trình sử dụng thư viện bắt phím thời gian thực `<conio.h>` và tập lệnh dọn màn hình hệ thống `system("cls")`).

### Biên dịch Trò chơi chính
Mở cửa sổ dòng lệnh (Terminal / CMD) tại thư mục gốc của đồ án và thực thi chuỗi lệnh sau:
```bash
# Di chuyển vào phân vùng mã nguồn
cd src

# Biên dịch gộp các file mô-đun bằng chuẩn C++17
g++ -std=c++17 cd.cpp source.cpp -o ../game.exe

# Quay ngược lại thư mục gốc và chạy trò chơi
cd ..
./game.exe
