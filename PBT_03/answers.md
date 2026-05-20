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
    
    ++Ưu/nhược:dễ quản lý, không cần file css/ không tái sử dụng được, trang bị dai nếu css nhiều

    ↓
    Inline CSS    ← ⚠️ Chỉ dùng khẩn cấp / override tạm thời
     ++ví dụ: <p style="color: red; font-size: 20px;">Xin chao</p>
     ++ưu/nhược: nhanh gọn/ khó bảo trì, không tái sử dụng được
                 