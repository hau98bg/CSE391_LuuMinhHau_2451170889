Câu A1.1:
- Khi gõ Https://shopee.vn vào trình duyệt và ấn Enter, các bước lần lượt xảy ra là:
 + request được gửi đi
 + chrome phân tích nhận giao thức https và domain là shopee.vn
 + tìm địa chỉ của shoppe.vn, DNS trả về kết quả IP
 + duyệt tìm địa chỉ IP vừa có 
 + thiết lập kết nối TCP tới server(Https- cổng 443)
 + trình duyệt kiểm tra tính bảo mật và tạo kết nối
 + trình duyệt gửi http reques(muốn mở trang chủ shoppe)-> server xử lý và phản hồi gồm mã nguồn của shoppe.vn 
 + trình duyệt đọc mã HTML, tải thêm css, javaScript, hình ảnh, sau đó ghép lại tất cả để đưa ra giao diện hoàn chỉnh của shoppe.vn

câu A1.2
-Trong DevTools của Chrome, tab Network cho thấy thông tin:
 + danh sách all request của trang 
 + status của từng request
 + name file trong web(html, css, js, ảnh)
 + kích thuoicws cảu file 
 + thời gian tải 
 + tổng thời gian load trang 
-ảnh chụp tab Network:
 + ![tab Network shoppe](<Screenshot 2026-04-22 134953.png>)

Câu A2:
-code web cũ 
    <div class="header">
        <div class="logo">ShopTLU</div>
        <div class="menu">
            <div><a href="/">Trang chủ</a></div>
            <div><a href="/products">Sản phẩm</a></div>
        </div>
    </div>
    <div class="main">
        <div class="product">
            <div class="title">iPhone 16 Pro</div>
            <div class="price">25.990.000đ</div>
            <div class="image"><img src="iphone.jpg"></div>
        </div>
    </div>
    <div class="footer">© 2026 ShopTLU</div>
- trang web này bị đánh giá thấp bởi vì:
 + dùng toàn thẻ <div> cho trang 
- lỗi semantic:
 + <div class="header">  -> <header>
 + <div class="menu">    -> <nav>
 + <div class="main">    -><main>
 + <div class="product"> -><article>
 + <div class="footer">  -><footer>
 + <div class="title">   -><h1>
 + Ảnh không có thuộc tính `alt`
- code sau khi sửa: 
    html 
    <header>
        <div class="logo">ShopTLU</div>

        <nav>
            <ul>
                <li><a href="/">Trang chủ</a></li>
                <li><a href="/products">Sản phẩm</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <article class="product">
            <h1>iPhone 16 Pro</h1>
            <p class="price">25.990.000đ</p>

            <img src="iphone.jpg" alt="Điện thoại iPhone 16 Pro">
        </article>
    </main>

    <footer>
        © 2026 ShopTLU

Câu A3:
-[mô tả code](screenshot/sreenshot-A3.png)
-giải thích:
 + có 3 hộp 1, 2, 3 vì có 3 thẻ <div>
 +Text a, Text b nằm cùng 1 dòng vì cùng là thẻ <span>
 +Text c, Text d nằm cùng 1 dòng vì cùng là thẻ <span> và text d được in đậm vì thẻ<strong>

Câu A4:
- Sự khác nhua giữa <thead>, <tbody>, <tfoot>:
 +vai trò:
 --<thead>: hheader(đầu bảng) tiêu đề cột
 --<tbody>: body(thân giữa bảng) dữ liệu chính
 --<tfoot>: footer(cuối bảng) tổng kết 

-Tại sao không nên dùng TABLE để tạo layout cho trang web bởi vì:
 + Table chỉ dùng cho dữ liệu dạng bảng(danh sách, so sánh, thống kê)
 + Table thường có giao diện cố định, khi dùng ở màn hình nhỏ sẽ gây vỡ giao diện
 + code dài dòng và khó sửa vì nhiều phải lồng nhiều thẻ <table>,<tr>,<td>
 + SEO kém: công cụ tìm kiếm khó hiểu đâu là nội dung chính, menu, hay footer của trang
 + hiệu năng kém: trình duyệt phải tính toán toàn bộ bảng rồi mới hiển thị

Câu B3:
Lỗi 1: Dòng 1 — <!DOCTYPE> sai chuẩn — Sửa thành <!DOCTYPE html>
Lỗi 2: Dòng 4 — Thẻ <title> không đóng — Thêm </title>
Lỗi 3: Dòng 5 — charset viết sai "utf8" — Sửa thành "UTF-8"
Lỗi 4: Dòng 9 — Thẻ <h1> không đóng đúng — Sửa </h1>
Lỗi 5: Dòng 13 — Thẻ <a> không đóng — Sửa thành </a>
Lỗi 6: Dòng 13 — href="home" không phải anchor hợp lệ — Sửa thành href="#home"
Lỗi 7: Dòng 20 — Thiếu dấu ngoặc kép src=iphone.jpg — Sửa thành src="iphone.jpg"
Lỗi 8: Dòng 20 — Thiếu thuộc tính alt cho img — Thêm alt="iPhone 16 Pro"
Lỗi 9: Dòng 23 — Thẻ <b> đóng sai vị trí — Đưa </b> vào trước </p>
Lỗi 10: Dòng 28 — Table thiếu <thead> và <tbody> (lỗi semantic) — Thêm đầy đủ
Lỗi 11: Dòng 29 — Dùng <td> cho header — Sửa thành <th>
Lỗi 12: Dòng 39 — Có 2 thẻ <main> (sai semantic) — Đổi cái thứ 2 thành <aside>
Lỗi 13: Dòng 44 — Thẻ <p> trong footer không đóng — Thêm </p>
Lỗi 14: Thiếu thuộc tính lang trong <html> — Thêm lang="vi"

