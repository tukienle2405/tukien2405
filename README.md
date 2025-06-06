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







