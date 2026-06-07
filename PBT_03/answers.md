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

Bài B3:
1. p → Specificity: (0,0,1)

2. body p → Specificity: (0,0,2)

3. .text → Specificity: (0,1,0)

4. .highlight → Specificity: (0,1,0)

5. p.text → Specificity: (0,1,1)

6. .text.highlight → Specificity: (0,2,0)

7. body .text.highlight → Specificity: (0,2,1)

8. #demo → Specificity: (1,0,0)

9. p#demo → Specificity: (1,0,1)

10. #demo.text.highlight → Specificity: (1,2,0)

Element cuối cùng hiển thị màu vàng (gold).
Lý do là rule #demo.text.highlight có specificity cao nhất nên được ưu tiên áp dụng.
Khi thay đổi thứ tự các rule trong file CSS, kết quả thường không đổi vì rule có specificity cao hơn vẫn thắng. Chỉ khi hai rule có cùng specificity thì rule viết sau mới được ưu tiên.

Ảnh : ![ảnh screenshot element](./Screenshot_Answer/Screenshot%202026-06-07%20115950.png)

Câu C1:

Chiều rộng thực tế của sidebar:300 + 20 + 20 + 1 + 1 =342px
Chiều rộng thực tế của content:
660 + 30 + 30 + 1 + 1 = 722px
Tổng chiều rộng:342 + 722 = 1064px
Container chỉ rộng 960px nên hai khối không đủ chỗ để nằm cùng một hàng. Vì vậy content bị đẩy xuống dòng.
Cách sửa 1:
Dùng box-sizing: border-box cho sidebar và content để padding, border được tính vào width.
Cách sửa 2:
Giữ content-box nhưng giảm width của các khối sao cho tổng kích thước thực tế không vượt quá 960px.

![ảnh sửa layout](./Screenshot_Answer/Screenshot%202026-06-07%20122244.png)

