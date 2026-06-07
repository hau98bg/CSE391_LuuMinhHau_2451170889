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