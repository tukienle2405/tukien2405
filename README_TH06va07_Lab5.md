#Nhậo môn xử lý ảnh số TH05_LAB4 <br>
#Phân vùng  <br>
Sinh viên thực hiện: Lê Khương Tử Kiên Msvv: 2374802010588 <br>
Môn học: Nhập môn xử lý ảnh số <br>
Giảng viên: Đỗ Hữu Quân <br>

#Giới thiệu <br>
Bài lab này nhằm mục đích xác định và phân tích các đối tượng trong ảnh nhị phân – một bước quan trọng trong xử lý ảnh số. Thông qua việc sử dụng kỹ thuật gán nhãn (labeling) và trích xuất đặc trưng (region properties), bài lab giúp: <br>
Xác định số lượng và vị trí các đối tượng trong ảnh. <br>
Khoanh vùng các đối tượng bằng khung bao. <br>
Trích xuất các thông tin hình học như diện tích, trọng tâm của từng đối tượng. <br>
Làm nền tảng cho các ứng dụng như nhận dạng, phân loại hoặc theo dõi đối tượng. <br>

#Công nghệ sử dụng <br>
Python: Ngôn ngữ lập trình chính. <br>
Pillow: Đọc và chuyển ảnh sang xám. <br>
NumPy: Xử lý ảnh dưới dạng mảng. <br>
ImageIO: Lưu ảnh nhãn định dạng PNG. <br>
Scikit-Image: <br>
  – threshold_otsu: Phân ngưỡng ảnh bằng Otsu. <br>
  – label: Gán nhãn vùng liên thông. <br>
  – regionprops: Trích xuất đặc trưng vùng (diện tích, trọng tâm, khung bao). <br>
Matplotlib: Hiển thị ảnh và vẽ khung chữ nhật quanh các vùng được phát hiện. <br>

#Chi tiết các phép biến đổi và công thức <br>
2. Viết chương trình gán nhãn ảnh <br>
2.1 Gán nhãn nhả <br>

Mục đích <br>
Chuyển ảnh gốc sang ảnh xám để dễ dàng phân tích cường độ pixel. <br>
Sử dụng ngưỡng Otsu để phân tách đối tượng và nền một cách tự động, tạo ảnh nhị phân. <br>
Gán nhãn các vùng đối tượng liên thông trong ảnh nhị phân. Mỗi đối tượng được gán một mã số riêng biệt. <br>
Trích xuất đặc trưng hình học của từng đối tượng như: <br>
Diện tích (Area) <br>
Trọng tâm (Centroid) <br>
Khung bao (BoundingBox) <br>
Hiển thị ảnh kết quả với mỗi đối tượng được đánh dấu bằng khung chữ nhật, giúp dễ dàng nhận diện, kiểm tra và phân tích từng vùng trong ảnh. <br>
#Công thức toán học <br>
#Code chính <br>
<img width="429" height="119" alt="Image" src="https://github.com/user-attachments/assets/266824c3-6157-45b1-97ac-6126cf48fb7c" /> <br>
Tạo ảnh nhị phân từ ảnh xám bằng phương pháp Otsu để tách đối tượng ra khỏi nền.<br>
<img width="366" height="46" alt="Image" src="https://github.com/user-attachments/assets/c2017dd3-0134-4154-a705-972799af8c81" /> <br>
Gán nhãn (labeling) cho từng vùng đối tượng riêng biệt trong ảnh nhị phân.<br>
<img width="166" height="22" alt="Image" src="https://github.com/user-attachments/assets/1113058d-eccf-4813-8a91-525b40dd231b" /> <br>
Tính toán các đặc trưng hình học như diện tích, trọng tâm, khung bao cho từng vùng đã gán nhãn.<br>
<img width="671" height="165" alt="Image" src="https://github.com/user-attachments/assets/b7884e8e-1b05-43b5-a9f1-e75726dda901" /> <br>
Vẽ Bounding Box cho từng đối tượng bằng khung chữ nhật để minh họa kết quả phân tích.<br>

2.2 Dò tìm cạnh theo chiều dọc <br>
Mục đích <br>
Đọc và chuyển đổi ảnh: Mở ảnh và chuyển sang ảnh xám. <br>
Hiển thị ảnh gốc: Quan sát ảnh đầu vào. <br>
Tính hiệu ảnh: Trừ ảnh gốc và ảnh dịch chuyển bằng nd.shift. <br>
Phát hiện biên: Làm nổi bật vùng có thay đổi cường độ. <br>
Hiển thị kết quả: Hiển thị ảnh thể hiện vùng biên. <br>
#Công thức toán học <br>
B(x,y) = |I(x,y) - I(x,y) + 1| <br>
I(x,y) là giá tr07
2.6 Tìm điểm giống nhau của ảnh <br>
Mục đích <br>
Phát hiện các điểm góc (corner) trong hai ảnh bằng Harris Corner Detector. <br>
Trích xuất mô tả đặc trưng cục bộ (local patch descriptors) quanh mỗi điểm góc. <br>
So sánh và tìm các cặp điểm tương đồng giữa hai ảnh dựa trên khoảng cách Euclid giữa các descriptor. <br>
Hiển thị kết quả bằng cách nối các cặp điểm khớp tương ứng giữa hai ảnh. <br>
Ứng dụng trong nhận dạng đối tượng, ghép ảnh, và thị giác máy tính. <br>
#Công thức toán học <br>
#Code chính <br>
<img width="575" height="40" alt="Image" src="https://github.com/user-attachments/assets/c5aaecd1-6098-44f1-835a-c2b9733435ce" /> <br>
<img width="553" height="45" alt="Image" src="https://github.com/user-attachments/assets/67eff98b-53b1-493f-bbf6-7e507368bd8f" /> <br>
<img width="367" height="38" alt="Image" src="https://github.com/user-attachments/assets/188e9bd3-fd9c-4289-b40c-6d6cd0495813" /> <br>
<img width="321" height="48" alt="Image" src="https://github.com/user-attachments/assets/eee42b14-3718-4adb-a473-04504aadd51c" /> <br>
<img width="612" height="131" alt="Image" src="https://github.com/user-attachments/assets/f5945c06-63ba-480e-ab6e-1c1cb862e712" /> <br>
