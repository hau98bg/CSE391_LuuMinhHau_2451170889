Câu A1.1:
- Khi gõ Https://shopee.vn vào trình duyệt và ấn Enter, các bước lần lượt xảy ra là:
 + request được gửi đi
 + chrome phân tích nhận giao thức https và domain là shopee.vn
 + tìm địa chỉ của shoppe.vn, DNS trả về kết quả IP
 + duyệt tìm địa chỉ IP vừa có 
 + thiết lập kết nối TCP tới server(Https- cổng 443)
 +trình duyệt kiểm tra tính bảo mật và tạo kết nối
 + trình duyệt gửi http reques(muốn mở trang chủ shoppe)-> server xử lý và phản hồi gồm mã nguồn của shoppe.vn 
 + trình duyệt đọc mã HTML, tải thêm css, javaScript, hình ảnh, sau đó ghép lại tất cả để đưa ra giao diện hoàn chỉnh của shoppe.vn
A1.2
-Trong DevTools của Chrome, tab Network cho thấy thông tin:
 + danh sách all request của trang 
 +status của từng request
 + name file trong web(html, css, js, ảnh)
 + kích thuoicws cảu file 
 +thời gian tải 
 +tổng thời gian load trang 
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
 +Ảnh không có thuộc tính `alt`
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


