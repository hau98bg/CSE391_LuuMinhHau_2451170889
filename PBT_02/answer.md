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
<!-- Trường hợp 2 -->
<input type="email" value="abc">        <!-- User gõ "abc" -->
 => email không có dạng "abc" nên không submit được
<!-- Trường hợp 3 -->
<input type="number" min="1" max="10" value="15"> <!-- User gõ 15 -->
 => max(10) mà nhập 15 thì không submit được
<!-- Trường hợp 4 -->
<input type="text" pattern="[0-9]{10}" value="abc123"> <!-- User gõ "abc123" -->
 => pattern yêu cầu 10 chữ số nên "abc123" không đúng, không submit được
<!-- Trường hợp 5 -->
<input type="password" minlength="8" value="123">  <!-- User gõ "123" -->
 => minlenght là 8 nhưng nhập 'abc'= 3 nên không submit được