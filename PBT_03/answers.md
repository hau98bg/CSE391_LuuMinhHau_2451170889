Câu A1: 3 Cách nhúng CSS
 +  External CSS  ← ✅ Chuẩn production
     ++ví dụ: <link rel="stylesheet" href="style.css"> 
              <!-- file css: -->:
              p {
                color: green;
                font-size: 16px;
                }
     
     ++Ưu/nhược: dễ tái sử dụng, bảo trì dễ dàng/ cần thêm file css, cần thêm request tải file
    ↓
    Internal CSS  ← ✅ Prototype, single-page
     ++ví dụ:
     <head>
        <style>
            p {
                color: blue;
                font-size: 18px;
            }
        </style>
    </head>
    
    ++Ưu/nhược: dễ quản lý, không cần file css / không tái sử dụng được, trang bị nặng nếu css nhiều

    ↓
    Inline CSS    ← ⚠️ Chỉ dùng khẩn cấp / override tạm thời
     ++ví dụ: <p style="color: red; font-size: 20px;">Xin chao</p>
     ++ưu/nhược: nhanh gọn/ khó bảo trì, không tái sử dụng được

 +Câu hỏi thêm: Nếu cùng 1 element có cả 3 cách CSS đồng thời áp dụng, cách nào "thắng"? Giải thích tại sao.
  ++ Inline CSS sẽ "thắng" :inline gắn trực tiếp vào phần tử nên có độ ưu tiên cao hơn.

Câu A2:
 + h1=> Chọn: "ShopTLU"


 + .price => Chọn:
  - "25.990.000đ"
  - "45.990.000đ"


 + #app header=> Chọn:
    <header class="top-bar dark">
        ...
    </header>


 + nav a:first-child => Chọn: "Home"


 + .product.featured h2 => Chọn: "MacBook Pro"


 + article > p => Chọn:
    Trong article thứ nhất:
    - "25.990.000đ"
    - "Mô tả sản phẩm..."

    Trong article thứ hai:
    - "45.990.000đ"
    - "Mô tả sản phẩm..."


 + a[href="/"] => Chọn: "Home"


 + .top-bar.dark h1 => Chọn: "ShopTLU"   

Câu B1:
 +Các loại selector đã sử dụng:
 ++Element selector
  -body
  -table
  -th
  -td
  -footer

 ++Class selector
  -active
  -profile

 ++ ID selector
  -#main-header

 ++Descendant selector
  -nav a

 ++ Pseudo-class selector
  -nav a:hover
  -tr:nth-child(even)
  -tr:hover          

Câu B2:
 +Hộp 1 (content-box): chiều rộng thực tế = 350 px (đo từ DevTools)
 +Hộp 2 (border-box): chiều rộng thực tế = 300 px (đo từ DevTools)
 Giải thích sự khác biệt:
  +Ở content-box thì width chỉ tính phần nội dung nên khi cộng thêm padding và border, kích thước thực tế sẽ lớn hơn 300px.

  +Ở border-box thì padding và border đã nằm trong width nên chiều rộng thực tế vẫn là 300px.

 +ảnh Chụp screenshot DevTools hiển thị box model diagram cho mỗi hộp (tab Computed).
 ![ảnh conten-box](Screenshot_Answer/Screenshot%202026-06-07%20112559.png)
 ![ảnh borderbox](Screenshot_Answer/Screenshot%202026-06-07%20112635.png)