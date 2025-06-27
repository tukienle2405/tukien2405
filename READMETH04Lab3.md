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
1. Chương trình biến đổi ảnh <br>
1.1 Đọc ảnh và cắt vùng ảnh <br>
Mục đích <br>
Trích xuất một vùng nhỏ từ ảnh gốc <br>
Loại bỏ các vùng không cần thiết để tập trung vào phần quan trọng <br>
Chuẩn bị dữ liệu cho các bước xử lý ảnh tiếp theo (như phân tích đặc trưng của ảnh và nhận dạng ảnh...) <br>
Tiết kiệm bộ nhớ và tăng tốc xử lý bằng cách làm việc với vùng ảnh nhỏ hơn <br>
#Code chính <br>
![Image](https://github.com/user-attachments/assets/9feeaa5b-418e-4c1d-a553-9a6d8aa03436) <br>
Dòng code này thực hiện cắt vùng ảnh từ 'data' vùng mình chọn. <br>
1.2 Tịnh tiến đơn (Translation/Shift Transformation) <br>
Mục đích <br>
Di chuyển toàn bộ ảnh sang một vị trí mới trên hệ tọa độ ảnh <br>
Dịch chuyển ảnh theo trục ngang và dọc mà không làm thay đổi nội dung của ảnh <br>
Có thể ứng dụng được trong tiền xử lý ảnh, căn chỉnh ảnh hoặc là mô phỏng chuyển động <br>
Rất có ích khi cần phải so sánh ảnh ở nhiều vị trí hoặc kết hợp nhiều lớp ảnh <br>
#Công thức toán học <br>
                                      (x',y') = (x+Δx, y+Δy) <br>
(x,y) là tọa độ ban đầu của <br>
(x',y') là tọa độ mới sau khi tịnh tiến ảnh <br>
Δx là độ dịch theo trục ngang <br>
Δy là độ dịch theo trục dọc <br>
#Code chính <br>
![Image](https://github.com/user-attachments/assets/fb0bf531-6b15-42dd-bef7-885e80f13c67) <br>
1.3 Thay đổi kích thước ảnh <br>
Mục đích <br>
Phóng to hoặc thu nhỏ hình ảnh theo tỉ lệ yêu cầu <br>
Điều chỉnh ảnh để phù hợp với kích thước đầu của các mô hình xử lý ảnh <br>
Tiết kiệm bộ nhớ và khả năng xử lý nhanh với ảnh có kích thước <br>
Được sử dụng trong trước xử lý ảnh, dựng ảnh động hoặc hiển thị ảnh theo khung định sẵn (UI/UX) <br>
#Công thức toán học <br>
                               x' = sx * x <br>
                               y' = sy * y <br>
   x,y là tọa độ gốc <br>
   x',y' là tọa độ mới sau khi thay đổi kích thước ảnh <br>
   sx, sy là hệ số co giãn theo chiều ngang, dọc <br>
#Code chính <br>
![Image](https://github.com/user-attachments/assets/02e3e04e-6a47-4505-8d43-fa85df36e213) <br>
data là ảnh gốc dưới dạng numpy <br>
2: là hệ số phóng to <br>
1.4 Xoay ảnh <br>
Mục đích <br>
Thực hiện xoay toàn bộ ảnh quanh một điểm với một góc cụ thể (thường chọn là tâm ảnh) <br>
Dùng để hiệu chỉnh góc nhìn, xoay vật thể về hướng chuẩn <br>
Hữu ích trong xử lý ảnh y tế, ảnh vệ tinh, và các hệ thống thị giác máy <br>
#Công thức toán học
                          x' = cosθ - sinθ [x] <br>
                          y' = sinθ - cosθ [y] <br>
  x,y là tọa độ điểm gốc <br>
  x',y' là tọa độ điểm sau khi xoay <br>
  θ là góc xoay <br>
#Code chính <br>
![Image](https://github.com/user-attachments/assets/2eed4092-3ce9-4d7e-a239-3dbf79bd90b0) <br>
data là ảnh gốc dưới dạng numpy <br>
20 là góc xoay theo đơn vị là độ <br>
1.5 Giãn ảnh nhị phân (Dilation) <br>
Mục đích <br> 
Mở rộng các vùng trắng trong ảnh nhị phân <br>
Lấp đầy các lỗ nhỏ, khe hở hoặc kết nối các đối tượng gần nhau <br>
Tăng kích thước các đối tượng sáng và giúp làm nổi bật cấu trúc chính <br>
#Công thức toán học: <br>
#Code chính <br>
![Image](https://github.com/user-attachments/assets/458e9da7-bc6e-43e4-b891-5b18d9c61446) <br>
1.6 Coordinate Mapping <br>
Mục đích <br>
Làm biến dạng ảnh một cách ngẫu nhiên bằng cách thay đổi vị trí của từng pixel dựa trên nhiễu tọa độ <br>
Tạo hiệu ứng làm méo ảnh, giống như nhìn qua mặt kính cong hoặc dòng nước gợn sóng <br>
#Công thức toán học <br>
                              I'(x,y) = I(x+Δx(x,y), y+Δy(x,y)) <br>
   I(x,y) là tọa đổ ảnh gốc <br> 
   I'(x,y) là ảnh sau khi bị biến dạng tại ví trí gốc <br>
   Δx(x,y),Δy(x,y) là độ lệch ngẫu nhiên của từng điểm ảnh <br>
#Code chính <br>
![Image](https://github.com/user-attachments/assets/37ee5594-f70c-49bd-a087-13a85ea3cd26) <br>
1.7 Biến đổi chung
Mục đích <br>
Thực hiện biến đổi tọa độ tùy để tạo ra hiệu ứng biến dạng đặc biệt cho hình ảnh <br>
#Công thức toán học <br>
                                I'(x,y) = I(fx(x,y),fy(x,y)) <br>
  I(x,y): giá trị điểm ảnh gốc tại tọa độ (x,y) <br>
  I'(x,y): giá trị điểm ảnh trong ảnh đã bị biến đổi <br>
  fx(x,y), fy(x,y) đây là các hàm ánh xạ tọa độ do người dùng tự định nghĩa <br>
#Code chính <br>
![Image](https://github.com/user-attachments/assets/6de4e8d5-526b-4698-89de-8f486c4a3943) <br>
