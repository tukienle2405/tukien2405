#Nhậo môn xử lý ảnh số TH05_LAB4 <br>
#Phân vùng  <br>
Sinh viên thực hiện: Lê Khương Tử Kiên Msvv: 2374802010588 <br>
Môn học: Nhập môn xử lý ảnh số <br>
Giảng viên: Đỗ Hữu Quân <br>

#Giới thiệu <br>
Bài lab này nhằm mục đích thực hiện các kỹ thuật phân vùng ảnh (segmentation) – một bước quan trọng và nền tảng trong lĩnh vực xử lý ảnh số. Phân vùng ảnh là quá trình chia ảnh thành các vùng có ý nghĩa, thường ứng với các đối tượng hoặc khu vực quan tâm trong ảnh <br>
-Tách đối tượng khỏi nền, hỗ trợ nhận dạng và theo dõi đối tượng <br>
-Giảm độ phức tạp của ảnh, giúp tăng tốc xử lý và phân tích <br>
-Chuẩn bị dữ liệu cho các bước xử lý tiếp theo như trích đặc trưng, nhận diện hình dạng, phân loại hoặc đo lường <br>

#Công nghệ sử dụng <br>
Python: Ngôn ngữ chính<br>
Pillow (PIL): Đọc ảnh, chuyển sang ảnh xám, và tạo ảnh từ mảng<br>
NumPy: Xử lý ảnh dưới dạng mảng số học<br>
Matplotlib: Hiển thị ảnh trước và sau xử lý<br>
Scikit-Image (skimage.filters.threshold_otsu): Tính toán ngưỡng Otsu để phân tách ảnh nhị phân<br>

#Chi tiết các phép biến đổi và công thức <br>
2. Viết chương trình phân vùng ảnh <br>
2.1 Phân theo histogram <br>
2.1.1 Phương pháp otsu <br>

Mục đích <br>
Đọc ảnh màu và chuyển sang ảnh xám <br>
Tính ngưỡng Otsu tự động để phân chia ảnh thành hai vùng: vùng nền và vùng đối  <br>
Tạo ảnh nhị phân dựa trên ngưỡng này (ảnh chỉ có hai mức: đen và trắng) <br>
Hiển thị ảnh gốc và ảnh sau phân ngưỡng để quan sát kết quả <br>
#Công thức toán học <br>
#Code chính <br>
<img width="321" height="174" alt="Image" src="https://github.com/user-attachments/assets/5520f9a4-006b-42aa-a8e3-f2979fde4109" /> <br>
np.asarray(data): Chuyển ảnh xám từ đối tượng PIL sang mảng NumPy để xử lý. <br>
threshold_otsu(a): Tính toán ngưỡng phân tách tối ưu bằng thuật toán Otsu. <br>
a > thres: Phân ngưỡng tạo ảnh nhị phân (giá trị True nếu pixel > ngưỡng, False nếu không). <br>

2.1.2 Phương pháp Adaptive Thresholding<br>
Mục đích <br>
Chia ảnh xám thành ảnh nhị phân (chỉ gồm đen và trắng)<br>
Tính ngưỡng phân tách cục bộ cho từng vùng nhỏ trong ảnh thay vì dùng một ngưỡng toàn cục (như Otsu)<br>
Xử lý hiệu quả trong các trường hợp ảnh bị chênh sáng, đổ bóng, nhiễu sáng theo vùng<br>
#Công thức toán học <br>
s(x,y) = {1, nếu f(x,y) > T(x,y) <br>
         {0, nếu f(x,y) <= T(x,y) <br>
f(x,y) là giá trị mức xám của pixel tại vị trí (x,y) <br>
T(x,y)  ngưỡng cục bộ tại vùng xung quanh pixel đó (ví dụ: trung bình trong cửa sổ <br>
f(x,y) là giá trị pixel đầu ra (0 hoặc 1 trong ảnh nhị phân) <br>
Ví dụ:
s(x,y) = {1, nếu f(x,y) > T(x,y) - offset <br>
         {0, nếu f(x,y) <= T(x,y) - offset <br>
Giá trị pixel gốc tại vị trí (x, y): f(x, y) = 130
Giá trị trung bình vùng lân cận: T(x, y) = 125
Offset: 10
Suy ra: Ngưỡng cục bộ hiệu chỉnh: T(x, y) - offset = 125 - 10 = 115
#Code chính <br>
<img width="362" height="121" alt="Image" src="https://github.com/user-attachments/assets/521632b0-14b9-495e-bfbf-18cb3cf27590" /> <br>
np.asarray(data): chuyển ảnh xám từ định dạng PIL sang mảng NumPy để xử lý. <br>
threshold_local(a, 39, offset=10): tính ngưỡng riêng cho từng vùng 39×39 và giảm ngưỡng đi 10 đơn vị để tạo độ phân tách tốt hơn giữa nền và đối tượng. <br>

2.2 Phân vùng theo region <br>
Mục đích <br>
Tách riêng các đối tượng (tế bào, vùng ảnh) dính liền nhau bằng kỹ thuật watershed segmentation.<br>
Sử dụng phân ngưỡng Otsu để tạo ảnh nhị phân ban đầu, tách nền – đối tượng.<br>
Thực hiện phép co ảnh (erosion) để làm nhỏ vùng đối tượng, giảm phân đoạn quá mức.<br>
Biến đổi khoảng cách (distance transform) giúp xác định tâm của các vùng đối tượng.<br>
Áp dụng phân ngưỡng lần nữa để xác định vùng tiền cảnh rõ ràng.<br>
Gán nhãn vùng tiền cảnh để cung cấp marker đầu vào cho thuật toán watershed.<br>
Áp dụng thuật toán watershed để phân tách chính xác các vùng chồng lấn.<br>
#Công thức toán học <br>

#Code chính <br>
<img width="710" height="422" alt="Image" src="https://github.com/user-attachments/assets/700d41d7-8a70-4572-be56-afa9fb299848" /> <br>
Chuyển ảnh màu sang ảnh xám để xử lý dễ dàng hơn.<br>
Dùng ngưỡng Otsu để tạo ảnh nhị phân, tự động tách nền và đối tượng mà không cần chỉ định ngưỡng thủ công.<br>
Áp dụng phép co ảnh (erosion) để loại bỏ nhiễu và làm co các vùng dính liền, giúp cải thiện độ chính xác phân đoạn.<br>
Thực hiện biến đổi khoảng cách (distance transform) nhằm xác định tâm (trung tâm) của mỗi vùng đối tượng.<br>
Phân ngưỡng ảnh khoảng cách để giữ lại các điểm có khoảng cách lớn nhất – chính là tiền cảnh (foreground).<br>
Gán nhãn các vùng tiền cảnh để tạo marker cho thuật toán Watershed.<br>
Áp dụng thuật toán Watershed để phân chia chính xác các vùng đối tượng chồng lấn nhau bằng cách mô phỏng nước tràn và chặn lại tại các "đường ranh".<br>

2.3 Biến đổi đối tượng trong ảnh <br>
2.3.1 Sử dụng binary_dilation <br>

Mục đích <br>
Chuyển ảnh gốc thành ảnh xám để có thể xử lý theo mức xám.<br>
Áp dụng phép giãn (dilation) để mở rộng vùng sáng (mức xám cao), làm cho các đối tượng trong ảnh trở nên lớn hơn hoặc dính liền nhau.<br>
Sử dụng iterations=50, tức lặp lại phép giãn 50 lần → mở rộng rất mạnh, nhằm mục đích tạo vùng bao lớn hoặc kết nối các vùng rời rạc.<br>
Hiển thị ảnh sau giãn, để quan sát kết quả biến đổi.<br>
#Công thức toán học <br>
#Code chính <br>
<img width="412" height="24" alt="Image" src="https://github.com/user-attachments/assets/59818287-26f8-40ae-98a8-d670ad741022" /> <br>
nd.binary_dilation(data, iterations = 50) là hàm thực hiện giãn ảnh nhị phân từ thư viện scipy.ndimage.<br>
data là ảnh đầu vào (nên là ảnh nhị phân – chỉ gồm 0 và 1).<br>
iterations=50 là số lần lặp phép giãn; mỗi lần sẽ mở rộng vùng sáng ra một lớp pixel.<br>

2.3.2 Giãn ảnh nhị phân (Dilation) <br>

Mục đích <br> 
Chuyển ảnh xám từ ảnh gốc, dùng làm dữ liệu đầu vào.<br>
Định nghĩa phần tử cấu trúc dạng chữ thập 3×3 để xác định hình dạng lọc.<br>
Áp dụng phép mở ảnh (binary opening) với 25 lần lặp để:
Loại bỏ các vật thể nhỏ hoặc nhiễu trong ảnh.<br>
Làm trơn biên các đối tượng lớn.<br>
Bảo toàn hình dạng chính nhưng loại bỏ chi tiết không mong muốn.<br>
Hiển thị ảnh kết quả sau khi xử lý để quan sát sự khác biệt.<br>
#Công thức toán học: <br>
#Code chính <br>
<img width="506" height="124" alt="Image" src="https://github.com/user-attachments/assets/7bafc0a3-70f8-4a7b-9717-8d206e03df97" /> <br>
structure=s: chỉ định hình dạng phần tử cấu trúc (ở đây là hình chữ thập 3×3) – ảnh hưởng trực tiếp đến cách mở được thực hiện.<br>
iterations=25: thực hiện phép mở 25 lần lặp liên tiếp, giúp loại bỏ mạnh các chi tiết nhỏ và làm mịn biên tốt hơn.<br>
nd.binary_opening(data, structure=s, iterations =25) là hàm từ thư viện scipy.ndimage <br>

2.3. Sử dụng binary_erosion <br>

Mục đích <br>
Chuyển ảnh màu sang ảnh xám để làm đầu vào xử lý ảnh nhị phân.<br>
Định nghĩa phần tử cấu trúc hình chữ thập 3×3, xác định hình dạng và hướng tác động của phép co ảnh.<br>
Thực hiện phép co nhị phân (binary_erosion) với 50 lần lặp, giúp:
Làm thu hẹp các vùng sáng (đối tượng) trong ảnh.<br>
Loại bỏ các chi tiết nhỏ, các vùng mảnh hoặc nhiễu không đáng kể.<br>
Tách biệt các vùng sáng gần nhau nếu chúng chỉ nối với nhau bằng một vùng hẹp.<br>
Hiển thị ảnh sau khi co, giúp người dùng trực quan đánh giá ảnh đã được làm mảnh hoặc lọc nhiễu.<br>
#Công thức toán học <br>
#Code chính <br>
<img width="507" height="123" alt="Image" src="https://github.com/user-attachments/assets/ca656a4a-8514-4946-8ab2-8614383c2932" /> <br>
structure=s: xác định hình dạng của phần tử cấu trúc – ở đây là hình chữ thập 3×3, giúp xác định vùng lân cận khi co ảnh.<br>
iterations=50: thực hiện co ảnh 50 lần liên tiếp, tức mỗi lần sẽ thu hẹp vùng sáng thêm một lớp pixel theo phần tử cấu trúc → làm nhỏ hoặc biến mất hoàn toàn các vùng mỏng.<br>
nd.binary_erosion(data, structure=s, iterations=50): hàm trong scipy.ndimage thực hiện phép co ảnh nhị phân:<br>

2.3.4 Sử dụng binary_closing <br>

Mục đích <br>
Chuyển ảnh màu sang ảnh xám, tạo đầu vào xử lý.<br>
Định nghĩa phần tử cấu trúc hình chữ thập 3×3, dùng để xác định vùng lân cận khi đóng.<br>
Áp dụng phép đóng ảnh (binary closing) với 25 lần lặp để: <br>
Làm đầy các lỗ nhỏ hoặc khoảng trống trong vùng sáng (đối tượng). <br>
Kết nối các vùng sáng gần nhau thành một khối liền mạch.<br>
Làm mượt các đường viền bằng cách lấp các khe hẹp hoặc rãnh sâu.<br>
#Công thức toán học <br>
#Code chính <br>
<img width="513" height="126" alt="Image" src="https://github.com/user-attachments/assets/35ae5746-34f7-4809-881d-e69a96f4bc50" /> <br>
structure=s: phần tử cấu trúc dạng chữ thập, xác định vùng lân cận khi đóng ảnh.<br>
iterations=25: lặp phép đóng 25 lần, giúp mở rộng hiệu ứng (lấp lỗ, kết nối vùng sáng).<br>
nd.binary_closing(data, structure=s, iterations=25): thực hiện phép đóng nhị phân <br>
