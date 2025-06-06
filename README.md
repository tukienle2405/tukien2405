#Bài 1.1 <br>
#Công nghệ sử dụng<br>
library: <br>
PIL là thư viện xử lý ảnh trong Python, thường được sử dụng để thao tác ảnh, hỗ trợ mở, chỉnh sửa và chuyển đổi dạng hình ảnh. <br>
Numpy là thư viện được sử dụng để nhập khẩu với bí danh (alias) là np.<br>
Matplotlib là thư viện được sử dụng để vẽ đồ thị<br>
Scipy, imageio.v2 được import tuy nhiên không được dùng trong đoạn code này.<br>
#Thuật toán sử dụng<br>
Thuật toán được sử dụng trong bài này là Inversion<br>
#Giải thích cách hoạt động<br>
Trong ảnh grayscale có mỗi pixel có giá trị từ 0 cho đến 255 (0 là đen, 255 là trắng)<br>
Và đảo âm ảnh là lấy pixel mới bằng công thức: <br>
![Image](https://github.com/user-attachments/assets/925c3b46-c216-4b65-b1d1-515d92670bee) <br>

#Bài 1.2: <br>
#Công nghệ sử dụng: <br>
library: <br>
PIL là thư viện xử lý ảnh trong Python, thường được sử dụng để thao tác ảnh, hỗ trợ mở, chỉnh sửa và chuyển đổi dạng hình ảnh. <br>
Numpy là thư viện được sử dụng để nhập khẩu với bí danh (alias) là np.<br>
Matplotlib là thư viện được sử dụng để vẽ đồ thị<br>
Math, Scipy, imageio.v2 được import tuy nhiên không được dùng trong đoạn code này.<br>
#Thuật toán sử dụng<br>
Thuật toán được sử dụng trong bài này là thuật toán gamma (hiệu chỉnh gamma)
#Giải thích cách hoạt động <br>
Hiệu chỉnh gamma là thuật toán được sử dụng để xử lý ảnh phi tuyến, thường được sử dụng để chỉnh độ sáng, tối của ảnh. Cải thiện vùng sáng và tối của ảnh. <br>
Sử dụng thuật toán trong đoạn code này để điều chỉnh độ sáng của ảnh theo kiểu phi tuyến. Giúp cho ảnh trông rõ hơn và đẹp hơn.
Trong đoạn code này cho gamma = 0.5 (gamma < 1 thì làm sáng ảnh nếu ảnh gốc bị tối, gamma > 1 thì ngược lại) <br>
![Image](https://github.com/user-attachments/assets/e8f81ab2-e7d6-492f-ac8d-2aa438a922ea) <br>

#Bài 1.3: <br>
#Công nghệ sử dụng: <br>
library: <br>
PIL là thư viện xử lý ảnh trong Python, thường được sử dụng để thao tác ảnh, hỗ trợ mở, chỉnh sửa và chuyển đổi dạng hình ảnh. <br>
Numpy là thư viện được sử dụng để nhập khẩu với bí danh (alias) là np.<br>
Matplotlib là thư viện được sử dụng để vẽ đồ thị<br>
Math, Scipy, imageio.v2 được import tuy nhiên không được dùng trong đoạn code này.<br>
#Thuật toán sử dụng<br>
Thuật toán được sử dụng trong bài này là thuật toán biến đổi Logarit (Logarithmic Transformation) <br>
Biến đổi Logarit là thuật toán được sử dụng để mở rộng các giá trị pixel ở vùng tối (cường độ thấp) và nén các giá trị pixel ở vùng sáng (cường độ cao). Giúp làm nổi bật một số chi tiết của ảnh bị khuất do độ tương phản không đủ. <br>
Dòng code này dùng để tìm giá trị pixel lớn nhất để chuẩn hóa trong công thức Log
![Image](https://github.com/user-attachments/assets/ce89f96f-d6e6-4130-83f7-660194248d33) <br>
Dòng code này bắt đầu sử dụng thuật toán, áp dụng công thức của thuật toán lên toàn bộ pixel (riêng lẻ không theo khối) <br>
![Image](https://github.com/user-attachments/assets/a53194ea-175f-4800-b28b-d26bd203e26f) <br>

#Bài 1.4: <br>
#Công nghệ sử dụng: <br>
library: <br>
PIL là thư viện xử lý ảnh trong Python, thường được sử dụng để thao tác ảnh, hỗ trợ mở, chỉnh sửa và chuyển đổi dạng hình ảnh. <br>
Numpy là thư viện được sử dụng để nhập khẩu với bí danh (alias) là np.<br>
Matplotlib là thư viện được sử dụng để vẽ đồ thị<br>
Math, Scipy, imageio.v2 được import tuy nhiên không được dùng trong đoạn code này.<br>
#Thuật toán sử dụng<br>
Thuật toán được sử dụng trong bài này là thuật toán Histogram Equalization <br?
Histogram Euqalization là thuật toán được sử dụng để cải thiện độ tương phản của ảnh xám đối với những bức ảnh quá tối hoặc quá sáng. <br>
Làm phẳng (flatten) mảng 2D thành mảng 1D
![Image](https://github.com/user-attachments/assets/a4c79df5-3a39-4974-a7a9-74b2b3690118)
Tính histogram và các khoảng bin
![Image](https://github.com/user-attachments/assets/93de2502-1f85-4a3e-bd85-e2d3e16c03b4)
Tính hàm phân phối tích lũy (CDF)
![Image](https://github.com/user-attachments/assets/808dc8ea-9f09-4c6a-8431-bde85c41d61d)
Các giá trị CDF bằng 0 sẽ bị che (mask), phần còn lại được giữ lại trong cdf_m
![Image](https://github.com/user-attachments/assets/5127e38a-edea-4d5c-8a12-996e8ed4e5e1)








