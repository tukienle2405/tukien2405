#Nhậo môn xử lý ảnh số TH04_LAB3 <br>
#Biến đổi hình học <br>
Sinh viên thực hiện: Lê Khương Tử Kiên Msvv: 2374802010588 <br>
Môn học: Nhập môn xử lý ảnh số <br>
Giảng viên: Đỗ Hữu Quân <br>
#Giới thiệu <br>
Bài lab này sẽ giúp sinh viên có thể thực hiện chọn đối tượng trong ảnh, thay đổi kích thước ảnh, xoay ảnh và biến đổi cục <br>
#Công nghệ sử dụng <br>
Python: ngôn ngữ chính <br>
NumPy: xử lý ảnh dưới dạng mảng số học <br>
ImageIO: đọc và lưu ảnh <br>
Matplotlib: hiển thị ảnh trực quan <br>
#Chi tiết các phép biến đổi và công thức <br>
1.1 Chương trình biến đổi ảnh <br>
1. Đọc ảnh và cắt vùng ảnh <br>
Mục đích <br>
Trích xuất một vùng nhỏ từ ảnh gốc <br>
Loại bỏ các vùng không cần thiết để tập trung vào phần quan trọng <br>
Chuẩn bị dữ liệu cho các bước xử lý ảnh tiếp theo (như phân tích đặc trưng của ảnh và nhận dạng ảnh...) <br>
Tiết kiệm bộ nhớ và tăng tốc xử lý bằng cách làm việc với vùng ảnh nhỏ hơn <br>
#Code chính <br>
![Image](https://github.com/user-attachments/assets/9feeaa5b-418e-4c1d-a553-9a6d8aa03436) <br>
Dòng code này thực hiện cắt vùng ảnh từ 'data' vùng mình chọn. <br>
1.2 Tịnh tiến đơn
