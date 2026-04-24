Câu A1.1:
- Khi gõ Https://shopee.vn vào trình duyệt và ấn Enter, các bước lần lượt xảy ra là:
 + request được gửi đi
 + chrome phân tích nhận giao thức https và domain là shopee.vn
 + tìm địa chỉ của shoppe.vn, DNS trả về kết quả IP
 + duyệt tìm địa chỉ IP vừa có 
 + thiết lập kết nối TCP tới server(Https- cổng 443)
 + trình duyệt kiểm tra tính bảo mật và tạo kết nối
 + trình duyệt gửi http request(muốn mở trang chủ shoppe)-> server xử lý và phản hồi gồm mã nguồn của shoppe.vn 
 + trình duyệt đọc mã HTML, tải thêm css, javaScript, hình ảnh, sau đó ghép lại tất cả để đưa ra giao diện hoàn chỉnh của shoppe.vn

câu A1.2
-Trong DevTools của Chrome, tab Network cho thấy thông tin:
 + danh sách all request của trang 
 + status của từng request
 + name file trong web(html, css, js, ảnh)
 + kích thước của file 
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
    </footer>    

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

Câu B4:
-Thẻ: <header>
 + Ở: Phần đầu trang (chứa logo, thanh tìm kiếm)
-Thẻ: <nav>
 + Ở: Thanh menu danh mục sản phẩm
-Thẻ: <section>
 + Ở: Khu “Sản phẩm nổi bật”
-![3 thẻ HTML5](<Screenshot 2026-04-25 002830.png>)

*B4.2
-Nội dung: Bảng so sánh các mẫu điện thoại Samsung Galaxy S26 Series, hiển thị thông tin như cấu hình, giá và các đặc điểm của sản phẩm.
- có sử dụng thẻ <tbody> và không sử dụng <thead>
-![tab table](<Screenshot 2026-04-25 004552.png>)

*B4.3
- Form có action: /tim-kiem
 + method không thấy khai báo
- input types:
 + text(nhập từ khóa tìm kiếm)
 + submit: nút button tìm kiếm 
-![tab form](<Screenshot 2026-04-25 005315.png>)

Câu C1:
Dưới đây là cấu trúc HTML đã thiết kế:

```html
<!DOCTYPE html>
<html>
<body>

<header> <!-- phần đầu -->
    <nav> <!-- menu -->
        <a href="#">Trang chủ</a>
    </nav>
</header>

<main>

<nav aria-label="breadcrumb"> <!-- điều hướng -->
    <ol>
        <li>Trang chủ</li>
        <li>Điện thoại</li>
        <li>iPhone 16</li>
    </ol>
</nav>

<section> <!-- sản phẩm -->
    <section> <!-- ảnh -->
        <img src="#" alt="">
        <img src="#" alt="">
        <img src="#" alt="">
        <img src="#" alt="">
        <img src="#" alt="">
    </section>

    <section> <!-- thông tin -->
        <h1>Tên sản phẩm</h1>
        <p>Giá</p>
    </section>
</section>

<section> <!-- bảng -->
    <table>
        <thead>
            <tr><th></th></tr>
        </thead>
        <tbody>
            <tr><td></td></tr>
        </tbody>
    </table>
</section>

<section> <!-- đánh giá -->
    <article>...</article>
</section>

</main>

<aside> <!-- sidebar -->
</aside>

<footer> <!-- phần cuối -->
</footer>

</body>
</html>
```

Câu C2:
-đoạn văn phản biện:
 + Theo tôi, việc chỉ dùng <div> cho mọi thứ là chưa hợp lý, vì semantic HTML mang lại nhiều lợi ích rõ ràng. Trước hết là về SEO. Các công cụ tìm kiếm không chỉ đọc nội dung mà còn dựa vào cấu trúc HTML để hiểu trang web. Khi sử dụng các thẻ như <header>, <nav>, <main>, <article>, nội dung được phân chia rõ ràng hơn, giúp công cụ tìm kiếm xác định phần quan trọng và cải thiện thứ hạng. Nếu chỉ dùng <div>, cấu trúc trang sẽ kém rõ ràng.Thứ hai là về Accessibility. Người dùng sử dụng screen reader cần các thẻ semantic để điều hướng nhanh. Ví dụ họ có thể chuyển trực tiếp đến <nav> hoặc <main>. Nếu chỉ dùng <div>, việc truy cập sẽ khó khăn hơn, đặc biệt với người khiếm thị.Ví dụ, trong trang bán hàng, nếu mỗi sản phẩm được đặt trong <article>, thì cả công cụ tìm kiếm và screen reader đều hiểu đó là một nội dung độc lập, giúp hiển thị và truy cập tốt hơn.Tuy nhiên, <div> vẫn phù hợp khi dùng để chia layout hoặc làm container cho CSS. Vì vậy, theo tôi, nên kết hợp cả semantic HTML và <div> để đạt hiệu quả tốt nhất.