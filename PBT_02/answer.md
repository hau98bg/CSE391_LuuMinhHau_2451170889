Câu A1:
-type="email" → Ô nhập text, kiểm tra có @ → Dùng cho đăng ký tài khoản
-type="password" → Ô nhập bị ẩn ký tự (***), không có validation đặc biệt → Dùng cho đăng nhập
-type="text" → Ô nhập văn bản bình thường, không validation → Nhập tên khách hàng
-type="number" → Ô nhập số, chỉ cho nhập số → Nhập số lượng sản phẩm
-type="tel" → Ô nhập số điện thoại, không check chặt nhưng gợi ý bàn phím số → Nhập số điện thoại giao hàng
-type="url" → Ô nhập link, kiểm tra định dạng URL → Nhập link website
-type="date" → Hiển thị chọn ngày (calendar), kiểm tra định dạng ngày → Chọn ngày sinh
-type="radio" → Nút chọn 1 trong nhiều lựa chọn → Chọn phương thức thanh toán
-type="checkbox" → Ô tích chọn nhiều lựa chọn → Chọn nhiều sản phẩm
-type="submit" → Nút bấm gửi form → Dùng để đặt hàng 

Câu A2:
<!-- Trường hợp 1 -->
<input type="text" required value="">   <!-- User để trống -->
 => value rỗng chắc không sunbmit được
 + ![th1](<Screenshot 2026-04-25 013907.png>)
<!-- Trường hợp 2 -->
<input type="email" value="abc">        <!-- User gõ "abc" -->
 => email không có dạng "abc" nên không submit được
 + ![th2](<Screenshot 2026-04-25 013922.png>)
<!-- Trường hợp 3 -->
<input type="number" min="1" max="10" value="15"> <!-- User gõ 15 -->
 => max(10) mà nhập 15 thì không submit được
 + ![th3](<Screenshot 2026-04-25 013940.png>)
<!-- Trường hợp 4 -->
<input type="text" pattern="[0-9]{10}" value="abc123"> <!-- User gõ "abc123" -->
 => pattern yêu cầu 10 chữ số nên "abc123" không đúng, không submit được
 + ![th4](<Screenshot 2026-04-25 013949.png>)
<!-- Trường hợp 5 -->
<input type="password" minlength="8" value="123">  <!-- User gõ "123" -->
 => minlenght là 8 nhưng nhập 'abc'= 3 nên không submit được

Câu A3:
- <label for ="email">: quan trọng cho người dùng screen reader:
 + screen reader sẽ đọc nội dung <label> khi người dùn focus vào <input>
 + biết ô này dùng để nập gì(email,...)
 + nếu không có <label>, screen reader chỉ đọc chung chung như “edit text”, gây khó hiểu
 + khi click vào label cũng focus vào input, thao tác dễ và nhanh hơn
-dùng <fieldset> + <legend>:
 + khi có nhóm các input liên quan
 +ví dụ:
 <fieldset>
    <legend>Thông tin giao hàng</legend>
    <label for="street">Đường:</label>
    <input type="text" id="street" name="street">
</fieldset> 
- <aria-label> dùng khi không có text nhưng vẫn cần mô tả cho screen reader
 + ví dụ: button icon
-Tại sao KHÔNG nên dùng <aria-label> khi đã có <label>?
 + tại vì <label> cung cấp đầy đủ thông tin cần thiết rồi
 + thêm <aria-label> sẽ gây trùng lặp và rối thông tin 

Câu A4:
- loading="lazy" dùng để trì hoãn việc tải ảnh cho đến khi ảnh gần xuất hiện trong viewport
- cải thiện: 
 + giảm thời gian tải trang ban đầu
 + tiết kiệm băng thông
 + tối ưu hiệu năng với trang có nhiều ảnh
- không nên dùng khi:
 + ảnh ở đầu trag=ng
 + ảnh là logo, banner chính
-A4.2 Tại sao nên cung cấp nhiều <source> trong <video>?
 + tăng khả năng tương thích với nhiều trình duyệt
 + trình duyệt tự fomat phù hợp
- format phổ biến:
 + MP4 (video/mp4)
 + WebM (video/webm)
 + Ogg (video/ogg) 
-A4.3
 + thuộc tính alt trên <img> dùng để viết mô tả cho ảnh
 + ví dụ:
 + <img src="iphone16.jpg" alt="Điện thoại iPhone 16 màu đen">   
 + <img src="luuminhhau.png" alt="ảnh đại diện của lưu minh hậu">
 + <img src="chart.png" alt="Biểu đồ doanh thu quý 1 năm 2026 tăng dần qua các tháng">

Câu A5:
- <!-- Cách 1 -->
<img src="product.jpg" alt="iPhone">

<!-- Cách 2 -->
<figure>
    <img src="product.jpg" alt="iPhone 16 Pro Max 256GB Titan">
    <figcaption>iPhone 16 Pro Max — 25.990.000đ</figcaption>
</figure>
- so sánh <img> và <figure>:
 + <img> dùng để hiển thị ảnh và cần có alt để mô tả ảnh
 + <figure> là thẻ bao(container) vẫn để hiển thị ảnh, biểu đồ, code và thường có <figcaption> đi cùng để mô tả chú thích (caption) của ảnh
-dùng cách 1 khi:
 + ảnh không cần dòng chú thích (caption) ở ảnh
  + ví dụ : <img src="avatar.jpg" alt="Ảnh đại diện của người dùng">
 + cách 2 khi ảnh cần mô tả chú thích 
  + ví dụ :
   <figure>
     <img src="product.jpg" alt="iPhone 16 Pro Max 256GB Titan">
     <figcaption>iPhone 16 Pro Max — 25.990.000đ</figcaption>
   </figure>