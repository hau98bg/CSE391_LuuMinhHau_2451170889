Câu A1 (5đ)

1. Thẻ viewport chuẩn:

<meta name="viewport" content="width=device-width, initial-scale=1.0">

Giải thích:
- width=device-width: đặt chiều rộng trang bằng đúng chiều rộng thiết bị
- initial-scale=1.0: mức zoom ban đầu là 100%, không phóng to/thu nhỏ

--------------------------------------------------

2. Nếu thiếu thẻ viewport:

- iPhone sẽ render trang theo layout width mặc định (~980px)
- Trang bị thu nhỏ lại để vừa màn hình
- Text nhỏ, phải zoom thủ công mới đọc rõ
- Layout desktop bị co lại trên mobile

--------------------------------------------------

3. Mobile-First vs Desktop-First

Mobile-First:
- Viết CSS cho mobile trước, sau đó nâng cấp cho màn hình lớn

Ví dụ:

body{
    font-size: 14px;
}

@media (min-width: 768px){
    body{
        font-size: 16px;
    }
}

Desktop-First:
- Viết CSS cho desktop trước, sau đó giảm cho mobile

Ví dụ:

body{
    font-size: 16px;
}

@media (max-width: 768px){
    body{
        font-size: 14px;
    }
}

--------------------------------------------------

4. Tại sao Mobile-First được khuyên dùng:

- Tối ưu hiệu năng cho thiết bị yếu
- Dễ mở rộng lên màn hình lớn hơn
- Phù hợp xu hướng người dùng dùng mobile nhiều hơn desktop
- CSS rõ ràng hơn, ít override phức tạp

câu a2 (5đ) — breakpoints

-xs (extra small)
kích thước: dưới 576px
thiết bị: điện thoại nhỏ
lưới sản phẩm: 1 cột

-sm (small)
kích thước: từ 576px trở lên
thiết bị: điện thoại lớn
lưới sản phẩm: 2 cột

-md (medium)
kích thước: từ 768px trở lên
thiết bị: tablet
lưới sản phẩm: 2–3 cột

-lg (large)
kích thước: từ 992px trở lên
thiết bị: laptop
lưới sản phẩm: 3–4 cột

-xl (extra large)
kích thước: từ 1200px trở lên
thiết bị: desktop / màn hình lớn
lưới sản phẩm: 4–5 cột

Câu A3 (5đ)

375px (iPhone SE)  → 100%
600px              → 540px
800px              → 720px
1000px             → 960px
1400px             → 1140px

Câu A4 (5đ)

1. Variables ($primary-color)

SCSS cho phép tạo biến để tái sử dụng giá trị.

Ví dụ:
$primary-color: blue;

button{
    background: $primary-color;
}

--------------------------------------------------

2. Nesting (CSS lồng nhau)

Cho phép viết CSS theo cấu trúc giống HTML.

Ví dụ:
nav{
    ul{
        list-style: none;
    }
    li{
        display: inline-block;
    }
}

--------------------------------------------------

3. Mixins (@mixin, @include)

Dùng để tái sử dụng đoạn CSS nhiều lần.

Ví dụ:
@mixin center{
    display: flex;
    justify-content: center;
    align-items: center;
}

.box{
    @include center;
}

--------------------------------------------------

4. @extend / Inheritance

Cho phép kế thừa style từ selector khác.

Ví dụ:
.btn{
    padding: 10px;
    border: none;
}

.btn-primary{
    @extend .btn;
    background: blue;
}

--------------------------------------------------

5. Vì sao browser không đọc được .scss?

- Trình duyệt chỉ hiểu CSS thuần (plain CSS)
- SCSS là ngôn ngữ tiền xử lý (preprocessor)

Cần bước chuyển:

SCSS → compiler (Sass) → CSS → browser