# buivannam
# 🎮 Maze Game C++ (Mô phỏng Tìm đường BFS vs DFS)

Một trò chơi giải mê cung đồ họa ASCII chạy trên giao diện dòng lệnh (Console/Terminal), được lập trình bằng ngôn ngữ **C++** theo kiến trúc hướng đối tượng (OOP). Dự án này tích hợp các thuật toán cấu trúc dữ liệu và giải thuật phổ biến như **DFS (Đệ quy/Ngăn xếp)** để tạo mê cung ngẫu nhiên và **BFS (Hàng đợi)** để tự động tìm đường đi ngắn nhất.

---

## ✨ Các tính năng chính

1. **Sinh mê cung tự động (DFS Backtracker):** Mê cung được đào đường hoàn toàn ngẫu nhiên và đảm bảo luôn có ít nhất một lối thoát hợp lệ từ điểm bắt đầu (S) tới điểm đích (E).
2. **Chế độ chơi thủ công:** Người chơi tự điều khiển ký tự `P` di chuyển trong mê cung thời gian thực bằng các phím điều hướng trực quan.
3. **Tự động giải bằng BFS:** Tìm kiếm theo chiều rộng (Breadth-First Search) giúp hiển thị đường đi ngắn nhất (`.`) từ điểm xuất phát đến đích.
4. **Tự động giải bằng DFS:** Tìm kiếm theo chiều sâu (Depth-First Search) mô phỏng hành trình dò đường mò mẫm (`*`).
5. **So sánh thuật toán:** Phân tích trực quan và đưa ra kết luận chi tiết về số bước đi (chi phí) chênh lệch giữa hai thuật toán BFS và DFS dựa trên cấu trúc ma trận lưới hiện tại.
6. **Thay đổi độ khó (Kích thước):** Cho phép người dùng tùy chỉnh kích thước chiều rộng và chiều cao của mê cung theo ý muốn.

---

## 📂 Cấu trúc mã nguồn (Project Structure)

Dự án được chia làm 3 phần mã nguồn tách biệt tuân thủ mô hình lập trình cấu trúc chuyên nghiệp:

* **`MazeGame.h` (Khai báo):** Chứa các thư viện cần thiết, hằng số hiển thị, cấu trúc tọa độ `Point` và khung xương (Blueprint) định nghĩa thuộc tính/nguyên mẫu hàm của lớp `MazeGame`.
* **`MazeGame.cpp` (Chương trình con):** Triển khai chi tiết logic xử lý toán học, điều khiển đồ họa console, và cấu trúc giải thuật của các thuật toán sinh/giải mê cung.
* **`main.cpp` (Chương trình chính):** Chứa hàm điều khiển trung tâm, quản lý luồng chạy vòng lặp và menu tương tác của người dùng.

---

## 🛠️ Hướng dẫn Biên dịch và Chạy game

### Yêu cầu hệ thống
* Hệ điều hành: Windows (Do có sử dụng thư viện `<conio.h>` và lệnh `system("cls")`).
* Trình biên dịch: GCC / G++ hoặc sử dụng các IDE như Visual Studio, Dev-C++, CLion.

### Biên dịch qua dòng lệnh (Terminal/CMD)
Di chuyển vào thư mục chứa dự án và chạy lệnh gộp dịch sau:

```bash
g++ main.cpp MazeGame.cpp -o MazeGame.exe
