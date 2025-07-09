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
I(x,y) là giá trị cường độ pixel trong ảnh gốc <br>
I(x,y) + 1 là giá trị cường độ pixel tại vị trí dịch sang 1 <br>
B(x,y) là kết quả thể hiện sự thay đổi tại biên. <br>
Ví dụ:
I ban đầu = [120,125,130]
I thứ = [115, 120,135]
Suy ra B = [5, 5, 5], cho thấy mức độ thay đổi đều nhau giữa hai ảnh, nghĩa là biên có mặt tại mọi ví trí nhưng không có điểm mạnh. <br>
#Code chính <br>
<img width="443" height="33" alt="Image" src="https://github.com/user-attachments/assets/7170b83e-5c46-4e5c-9a97-15acad8c2483" /> <br>
Đây là dòng thực hiện phép trừ giữa ảnh gốc và ảnh dịch chuyển, từ đó phát hiện biên thông qua sự thay đổi cường độ pixel. <br>

2.3 Dò tìm cạnh với Sobel Filter <br>
Mục đích <br>
Đọc ảnh: Mở ảnh gốc bằng Pillow. <br>
Tính gradient theo trục x: Dùng toán tử Sobel theo phương dọc (axis=0). <br>
Tính gradient theo trục y: Dùng toán tử Sobel theo phương ngang (axis=1). <br>
Tổng hợp biên: Cộng độ lớn gradient hai hướng để làm nổi bật rìa đối tượng. <br>
Hiển thị kết quả: Hiển thị ảnh biên sau khi xử lý. <br>
#Công thức toán học <br>
#Code chính <br>
<img width="258" height="87" alt="Image" src="https://github.com/user-attachments/assets/b5b90ddf-0478-4816-aef3-de41921d1dff" /> <br>
Những đoạn code trên là phần thực hiện tính toán biên bằng toán tử Sobel theo cả hai hướng x và y, sau đó cộng lại để làm nổi bật vùng biên trong ảnh. <br>

2.4 BXác định góc của đối tượng <br>

Mục đích <br>
Đọc ảnh: Mở ảnh gốc bằng Pillow. <br>
Xác định các điểm góc – nơi có sự thay đổi cường độ mạnh theo cả hai chiều (x và y). <br>
Các điểm góc là đặc trưng quan trọng trong việc so khớp ảnh, nhận dạng vật thể, tái tạo 3D. <br>
Ứng dụng trong theo dõi chuyển động, ghép ảnh (panorama), phát hiện đối tượng. <br>
#Công thức toán học <br>
#Code chính <br>
<img width="286" height="311" alt="Image" src="https://github.com/user-attachments/assets/cc61f812-c2b4-4cae-bca9-9b8e781734af" /> <br>
Tính gradient Ix, Iy. <br>
Làm trơn các thành phần ma trận cấu trúc. <br>
Tính giá trị phản hồi R để xác định điểm góc. <br>

2.5 Dò tìm hình dạng cụ thể trong ảnh với Hough Transform <br>
2.5.1 Dò tìm đường thẳng trong ảnh <br>

Mục đích <br>
Phát hiện các đường thẳng trong ảnh bằng cách biến đổi từ không gian ảnh sang không gian tham số (Hough space). <br>
Tích lũy các điểm ảnh sáng theo dạng tuyến tính để xác định vị trí và hướng của các đường thẳng. <br>
Ứng dụng trong nhận diện đường biên, mép vật thể, tách biên ảnh kỹ thuật (như ảnh bản vẽ, sơ đồ). <br>
#Công thức toán học <br>
p = x.cos(0) + y.sin(0) <br>
x,y là tọa độ điểm pixel trong ảnh <br>
0 là góc của đường thẳng <br>
p là khoảng cách từ gốc tọa độ đến đường thẳng theo phương vuông góc <br>
#Code chính <br>
<img width="472" height="424" alt="Image" src="https://github.com/user-attachments/assets/de9c3d5b-974a-4e49-ba16-01e8ca88e413" /> <br>
Lặp qua các điểm ảnh sáng (giá trị lớn) <br>
Tính ρ cho từng 𝜃 <br>
Tăng giá trị tại vị trí tương ứng trong không gian Hough (ho) <br>

2.5.2 Dò tìm đường tròn trong ảnh <br>

Mục đích <br>
Chuyển ảnh màu sang ảnh xám, tạo đầu vào xử lý.<br>
Xác định các điểm góc trong ảnh – nơi có sự thay đổi cường độ lớn theo cả hai hướng (x và y).
Làm nổi bật các điểm đặc trưng dùng cho việc nhận dạng, theo dõi chuyển động hoặc khớp ảnh.
Ứng dụng trong thị giác máy tính như ghép ảnh panorama, nhận diện đối tượng, phân tích cảnh.
#Công thức toán học <br>
#Code chính <br>
<img width="519" height="114" alt="Image" src="https://github.com/user-attachments/assets/382b151a-afbc-45e9-9303-486c4f58d8b6" /> <br>
rgb2gray(data): chuyển ảnh màu sang ảnh xám để dễ phát hiện góc. <br>
corner_harris(image_gray, k=0.001): áp dụng thuật toán Harris Corner Detector để phát hiện các điểm góc trong ảnh. <br>

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
