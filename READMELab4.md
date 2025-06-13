#Bài 1: 
#Công nghệ sử dụng
Python: Ngôn ngữ chính. <br>
PIL (Pillow): Đọc và ghi ảnh. <br>
Numpy: Xử lý ảnh dưới dạng mảng số học. <br>
Matplotlib: Hiển thị ảnh gốc và ảnh sau biến đổi. <br>
#Thuật toán sử dụng gồm 5 
Inverse Transformation - Đảo ngược mức xám <br>
Gamma Correction - Điều chỉnh độ sáng dựa theo lũy thừa <br>
Logarithmic Transformation - Tăng cường chi tiết vùng tối <br>
Histogram Equalization - Cân bằng histogram, tăng độ tương phản <br>
Contrast Stretching	- Căng giãn độ tương phản ảnh <br>
#Giải thích cách hoạt động thuật toán <br>
Thuật toán Inverse Transformation <br>
Mỗi pixel p được biến đổi thành 255 - p. <br>
Làm sáng vùng tối và tối vùng sáng. <br>
Ứng dụng: Tạo hiệu ứng âm bản. <br>
![Image](https://github.com/user-attachments/assets/1ce5e8ee-3c67-4d68-a1d4-4fa97322e444) <br>
Thuật toán Gamma Correction <br>
Chuyển giá trị pixel về khoảng [0,1]. <br>
Áp dụng hàm mũ: p' = p^γ. <br>
Với γ < 1: ảnh sáng hơn, γ > 1: ảnh tối hơn. <br>
Ứng dụng: Điều chỉnh sáng phù hợp với mắt người hoặc hiển thị. <br>
![Image](https://github.com/user-attachments/assets/3fbb608e-17e0-483b-a4cf-cc7033e77d6e) <br>
Thuật toán Logarithmic Transformation <br>
Tăng cường độ chi tiết trong vùng tối. <br>
Logarit nén phạm vi giá trị lớn nên làm nổi bật vùng tối. <br>
Ứng dụng: ảnh bị thiếu sáng.
![Image](https://github.com/user-attachments/assets/157ce837-486f-475e-897b-5e140f9a28fb) <br>
Thuật toán Histogram Equalization <br>
Tính histogram (phân phối mức xám). <br>
Tính CDF (hàm phân phối tích lũy). <br>
Dàn đều lại giá trị mức xám trên toàn khoảng [0, 255]. <br>
Ứng dụng: Tăng độ tương phản tổng thể ảnh. <br>
![Image](https://github.com/user-attachments/assets/528b9b94-1c5d-495c-9070-f19277c1709a) <br>
Thuật toán Contrast Stretching <br>
Dò ngưỡng sáng tối thực tế a và b. <br>
Tăng độ tương phản bằng cách giãn đều từ a → b sang 0 → 255. <br>
Ứng dụng: Cải thiện ảnh mờ nhạt, thiếu sáng rõ. <br>
![Image](https://github.com/user-attachments/assets/da30cce3-44d9-4f88-89fc-f74104a8f9e6) <br>
#Bài 2:
#Công nghệ sử dụng
Python: Ngôn ngữ chính. <br>
Pillow (PIL): Mở ảnh và lưu ảnh. <br>
Numpy: Xử lý ảnh dưới dạng mảng số học. <br>
Matplotlib: Hiển thị ảnh gốc và ảnh đã xử lý. <br>
SciPy (fftpack): Thực hiện biến đổi Fourier nhanh (FFT) và các thao tác miền tần số. <br>
#Thuật toán sử dụng gồm 3 <br>
Fast Fourier Transform (FFT) - Hiển thị phổ tần số <br>
Butterworth Lowpass Filter - Giữ lại tần số thấp (làm mịn ảnh) <br>
Butterworth Highpass Filter - Giữ lại tần số cao (làm sắc nét ảnh) <br>
#Giải thích cách hoạt động thuật toán
#Fast Fourier Transform (FFT)
fft2: Biến đổi Fourier 2D ảnh từ miền không gian sang miền tần số. <br>
fftshift: Đưa tần số thấp về giữa ảnh. <br>
log: Dùng log để hiển thị rõ ràng các chi tiết nhỏ. <br>
Kết quả là một ảnh biểu diễn phổ tần số. <br>
![Image](https://github.com/user-attachments/assets/8fd5479d-32cf-48d2-a363-fa00f81953b6) <br>
#Butterworth Lowpass Filter (lọc thông thấp)
Mục đích: Giữ lại tần số thấp, loại bỏ tần số cao (chi tiết, nhiễu). <br>
d0: Bán kính ngưỡng cắt tần số. <br>
bac: Bậc của bộ lọc (độ dốc của biên lọc). <br>
Tạo mặt nạ lọc tần số thấp, rồi nhân vào ảnh miền tần số → đảo ngược về miền không gian. <br>
Ứng dụng: Làm mờ ảnh, loại nhiễu cao tần. <br>
![Image](https://github.com/user-attachments/assets/c03e5cf4-3fb6-4061-b158-47233bed6e00) <br>
Butterworth Highpass Filter (lọc thông cao) <br>
Tương tự như lowpass, nhưng ngược lại: loại bỏ tần số thấp, giữ lại tần số cao. <br>
Làm rõ ranh giới, sắc nét chi tiết biên. <br>
Ứng dụng: Làm sắc ảnh, làm rõ biên. <br>
![Image](https://github.com/user-attachments/assets/c03e5cf4-3fb6-4061-b158-47233bed6e00) <br>
#Bài 3 tương tự bài 1 vì cùng sử dụng công nghệ và các thuật toán xử lý ảnh điểm giống nhau. Tuy nhiên, điểm khác biệt là bài 3 áp dụng trên ảnh RGB (với thứ tự kênh màu bị hoán đổi ngẫu nhiên), sau đó chuyển sang ảnh xám, và áp dụng ngẫu nhiên một thuật toán xử lý thay vì cho người dùng chọn. <br>
#Bài 4 tương tự bài 2 vì cùng sử dụng các công nghệ và thuật toán xử lý ảnh trong miền tần số như FFT và Butterworth. Tuy nhiên, khác biệt nằm ở chỗ bài 4 xử lý ảnh RGB (với kênh màu bị hoán đổi ngẫu nhiên), áp dụng ngẫu nhiên một trong ba phương pháp, và bổ sung thêm bước lọc không gian (Min/Max filter) sau khi biến đổi. <br>
