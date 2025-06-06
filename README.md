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
Thuật toán được sử dụng trong bài này là thuật toán Histogram Equalization <br>
Histogram Euqalization là thuật toán được sử dụng để cải thiện độ tương phản của ảnh xám đối với những bức ảnh quá tối hoặc quá sáng. <br>
Làm phẳng (flatten) mảng 2D thành mảng 1D <br>
![Image](https://github.com/user-attachments/assets/a4c79df5-3a39-4974-a7a9-74b2b3690118) <br>
Tính histogram và các khoảng bin <br>
![Image](https://github.com/user-attachments/assets/93de2502-1f85-4a3e-bd85-e2d3e16c03b4) <br>
Tính hàm phân phối tích lũy (CDF) <br>
![Image](https://github.com/user-attachments/assets/808dc8ea-9f09-4c6a-8431-bde85c41d61d) <br>
Các giá trị CDF bằng 0 sẽ bị che (mask), phần còn lại được giữ lại trong cdf_m <br>
![Image](https://github.com/user-attachments/assets/5127e38a-edea-4d5c-8a12-996e8ed4e5e1) <br>
Dòng code này trực tiếp thay đổi giá trị pixxel trong ảnh theo ánh xạ đá tính từ hàm phân phối lũy, bl là mảng 1D chứa giá trị mức xám cũ, cdf là giá trị mức xám mới (sau khi cân bằng histogram). Dòng này áp dụng thuật toán gán cho mỗi pixel trong ảnh với giá trị mức xám mới theo công thức chuẩn hóa cdf. <br>
![Image](https://github.com/user-attachments/assets/baf6b34c-0580-4fc8-a9f8-27b78ebf7561) <br>

#Bài 1.5: <br>
#Công nghệ sử dụng: <br>
library: <br>
PIL là thư viện xử lý ảnh trong Python, thường được sử dụng để thao tác ảnh, hỗ trợ mở, chỉnh sửa và chuyển đổi dạng hình ảnh. <br>
Numpy là thư viện được sử dụng để nhập khẩu với bí danh (alias) là np.<br>
Matplotlib là thư viện được sử dụng để vẽ đồ thị<br>
Math, Scipy, imageio.v2 được import tuy nhiên không được dùng trong đoạn code này.<br>
#Thuật toán sử dụng<br>
Thuật toán được sử dụng trong bài này là thuật toán Contrast Stretching
Contrast Stretching là thuật toán được sử dụng để tăng độ tương phản của ảnh xám bằng ách trải đều các mức xám hiện về có bộ dải giá trị [0,255]. Tức là một bức ảnh có khoảng hẹp từ 70-160 thì thuật toán này sẽ được áp dụng để co dãn khoảng trên thành khoảng 0-255 bằng công thức tuyến tính. <br>
Dòng code này áp dụng thuật toán Contrast Stretching, áp dụng phép tuyến tính. Đưa tất cả các giá trị trong c từ khoảng [a,b] về khoảng [0,255]. <br>
![Image](https://github.com/user-attachments/assets/fd78537f-a066-4baa-ac61-b80c258bd6ae) <br>

#Bài 1.6.1: <br>
#Công nghệ sử dụng: <br>
library: <br>
PIL là thư viện xử lý ảnh trong Python, thường được sử dụng để thao tác ảnh, hỗ trợ mở, chỉnh sửa và chuyển đổi dạng hình ảnh. <br>
Numpy là thư viện được sử dụng để nhập khẩu với bí danh (alias) là np.<br>
Matplotlib là thư viện được sử dụng để vẽ đồ thị<br>
Math, Scipy, imageio.v2 được import tuy nhiên không được dùng trong đoạn code này.<br>
Thư viện scipy sử dụng module fftpack là một module thuộc thư viện scipy thường sử dụng để cung cấp các thuật toán hiệu quả để tính Biến đổi Fourier Nhanh (FFT). <br>
#Thuật toán sử dụng<br>
Thuật toán được sử dụng trong bài này là thuật toán 2D Fast Fourier Transform - FFT2
2D Fast Fourier Transform - FFT2 là thuật toán dùng để chuyển ảnh từ miền không gian sang miền tần số. <br>
Dòng code này sử dụng thuật toán để tính biến đổi Fourier 2D của ảnh và chuyển ảnh sang miền tần số.
![Image](https://github.com/user-attachments/assets/90e084c4-fd3c-4dae-a80c-aa9f5e12a523) <br>
Dòng code này sử dụng thuật toán để sắp xếp lại phổ tần số để thành phần tần số thấp nằm ở giữa, giúp hiện thị phổ dễ nhìn và dễ phân tích hơn. <br>
![Image](https://github.com/user-attachments/assets/ddcee3b6-0d4e-4d2e-a264-362582d514d8) <br>

#Bài 1.6.2a: <br>
#Công nghệ sử dụng: <br>
library: <br>
PIL là thư viện xử lý ảnh trong Python, thường được sử dụng để thao tác ảnh, hỗ trợ mở, chỉnh sửa và chuyển đổi dạng hình ảnh. <br>
Numpy là thư viện được sử dụng để nhập khẩu với bí danh (alias) là np.<br>
Matplotlib là thư viện được sử dụng để vẽ đồ thị<br>
Math, Scipy, imageio.v2 được import tuy nhiên không được dùng trong đoạn code này.<br>
Thư viện scipy sử dụng module fftpack là một module thuộc thư viện scipy thường sử dụng để cung cấp các thuật toán hiệu quả để tính Biến đổi Fourier Nhanh (FFT). <br>
#Thuật toán sử dụng: <br>
Có 2 thuật toán được sử dụng trong bài này:
Thuật toán đầu tiên được sử dụng trong bài này là thuật toán 2D Fast Fourier Transform - FFT2
2D Fast Fourier Transform - FFT2 là thuật toán dùng để chuyển ảnh từ miền không gian sang miền tần số. <br>
Thuật toán thứ hai được sử dụng trong bài này là Butterworth Lowpass Filter (Bộ lọc thông thấp Butterworth) giúp loại bỏ hoặc làm suy giảm các tần số cao chỉ giữ lại tần số thấp, ngoài ra còn giúp loại bỏ nhiễu hoặc làm ảnh mờ đi. <br>
Dòng code này tạo bộ lọc Butterworth theo công thức toán học <br>
![Image](https://github.com/user-attachments/assets/219e2bf5-55a2-4998-a32f-ddeb9d7d2b93) <br>
Dòng này áp dụng bộ lọc lên phổ Fourier của ảnh (nhân phổ với bộ lọc) <br>
![Image](https://github.com/user-attachments/assets/c7120e4d-1fd4-4fab-9e69-b7fc3289503d) <br>

#Bài 1.6.2b: <br>
#Công nghệ sử dụng: <br>
library: <br>
PIL là thư viện xử lý ảnh trong Python, thường được sử dụng để thao tác ảnh, hỗ trợ mở, chỉnh sửa và chuyển đổi dạng hình ảnh. <br>
Numpy là thư viện được sử dụng để nhập khẩu với bí danh (alias) là np.<br>
Matplotlib là thư viện được sử dụng để vẽ đồ thị<br>
Math, Scipy, imageio.v2 được import tuy nhiên không được dùng trong đoạn code này.<br>
Thư viện scipy sử dụng module fftpack là một module thuộc thư viện scipy thường sử dụng để cung cấp các thuật toán hiệu quả để tính Biến đổi Fourier Nhanh (FFT) và phép biến đổi ngược của nó (IFFT). <br> 
#Thuật toán sử dụng: <br>
Có 3 thuật toán được sử dụng trong bài này:
Thuật toán đầu tiên được sử dụng trong bài này là thuật toán 2D Fast Fourier Transform - FFT2
2D Fast Fourier Transform - FFT2 là thuật toán dùng để chuyển ảnh từ miền không gian sang miền tần số. <br>
Thuật toán thứ hai được sử dụng trong bài này là Butterworth Lowpass Filter (Bộ lọc thông thấp Butterworth) giúp loại bỏ hoặc làm suy giảm các tần số cao chỉ giữ lại tần số thấp, ngoài ra còn giúp loại bỏ nhiễu hoặc làm ảnh mờ đi. <br>
Thuật toán thứ ba được sử dụng trong bài này là Biến đổi Fourier ngược (IFFT) giúp chuyển ảnh từ miền tần só trở lại miền không gian sau khi đã áp dụng bộ lọc (nếu chưa áp dụng bộ lọc thì IFFT sẽ tạo lại ảnh gần như là ảnh gốc).
Dòng code này tạo bộ lọc Butterworth theo công thức toán học <br>
![Image](https://github.com/user-attachments/assets/219e2bf5-55a2-4998-a32f-ddeb9d7d2b93) <br>
Dòng code này áp dụng bộ lọc lên phổ Fourier của ảnh (nhân phổ với bộ lọc) <br>
![Image](https://github.com/user-attachments/assets/c7120e4d-1fd4-4fab-9e69-b7fc3289503d) <br>
Dòng code này dùng để tái tạo ảnh sau khi xử lý <br>
![IImage](https://github.com/user-attachments/assets/737a49f8-a158-495f-be34-fbda7fbc454f) <br>









