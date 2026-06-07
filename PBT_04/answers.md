Câu A1:
 Câu A1:

- static
  + Vẫn chiếm chỗ trong flow: Có
  + Tham chiếu vị trí: Vị trí mặc định trong document flow
  + Cuộn theo trang: Có
  + Use case: Bố cục thông thường

- relative
  + Vẫn chiếm chỗ trong flow: Có
  + Tham chiếu vị trí: So với vị trí ban đầu của chính nó
  + Cuộn theo trang: Có
  + Use case: Dịch chuyển phần tử, làm mốc cho absolute

- absolute
  + Vẫn chiếm chỗ trong flow: Không
  + Tham chiếu vị trí: Parent gần nhất có position khác static
  + Cuộn theo trang: Có
  + Use case: Popup, badge, menu con

- fixed
  + Vẫn chiếm chỗ trong flow: Không
  + Tham chiếu vị trí: Viewport
  + Cuộn theo trang: Không
  + Use case: Nút lên đầu trang, thanh hỗ trợ

- sticky
  + Vẫn chiếm chỗ trong flow: Có
  + Tham chiếu vị trí: Vị trí ban đầu, sau đó bám viewport
  + Cuộn theo trang: Có (đến ngưỡng thì bám lại)
  + Use case: Header, menu điều hướng

Khi nào absolute tham chiếu body?

- Khi không có phần tử cha nào có thuộc tính position khác static.
- Lúc này phần tử absolute sẽ lấy body (hoặc viewport) làm mốc định vị.

Khi nào absolute tham chiếu parent?

- Khi có phần tử cha gần nhất có position là relative, absolute, fixed hoặc sticky.
- Khi đó phần tử absolute sẽ định vị dựa trên phần tử cha này.

Giải thích khái niệm "nearest positioned ancestor":

- Nearest positioned ancestor là phần tử tổ tiên gần nhất có thuộc tính position khác static.
- Đây là phần tử được absolute dùng làm mốc để tính các thuộc tính top, left, right, bottom.

Câu A2

1. Trường hợp 1

Bố cục:
- 1 hàng
- 4 cột bằng nhau

Sơ đồ:

+-----+-----+-----+-----+
|  1  |  2  |  3  |  4  |
+-----+-----+-----+-----+

2. Trường hợp 2

Bố cục:
- 3 hàng
- 2 cột

Sơ đồ:

+-----+-----+
|  1  |  2  |
+-----+-----+
|  3  |  4  |
+-----+-----+
|  5  |  6  |
+-----+-----+

3. Trường hợp 3

Bố cục:
- 1 hàng
- Item 1 ở bên trái
- Item 2 ở giữa
- Item 3 ở bên phải
- Các item căn giữa theo chiều dọc

Sơ đồ:

+---------------------------+
|  1        2          3    |
+---------------------------+

4. Trường hợp 4

Bố cục:
- 1 hàng
- 3 cột
- Cột 1 rộng 200px
- Cột 2 chiếm phần còn lại
- Cột 3 rộng 200px

Sơ đồ:

+--------+----------------+--------+
|   1    |       2        |   3    |
+--------+----------------+--------+

5. Trường hợp 5

Bố cục:
- 3 cột
- 3 hàng
- Item 7 nằm ở hàng cuối cùng

Sơ đồ:

+-----+-----+-----+
|  1  |  2  |  3  |
+-----+-----+-----+
|  4  |  5  |  6  |
+-----+-----+-----+
|  7  |     |     |
+-----+-----+-----+

Item cuối cùng (item 7) nằm ở hàng 3, cột 1.

Câu B1:
![ảnh Trạng thái header khi scroll ](/PBT_04/Screenshot_Answer/Screenshot%202026-06-07%20125635.png)
![ảnh Trạng thái sidebar khi scroll ](/PBT_04/Screenshot_Answer/Screenshot%202026-06-07%20125657.png)
![ảnh Badge trên card ](/PBT_04/Screenshot_Answer/Screenshot%202026-06-07%20125725.png)

Câu C1

1. Navigation bar ngang (logo + menu + buttons)
- Flexbox
Giải thích:
Flexbox phù hợp với bố cục 1 chiều theo hàng ngang và dễ căn chỉnh khoảng cách giữa các phần tử.

2. Lưới ảnh Instagram (3 cột đều nhau, số ảnh không biết trước)
- Grid
Giải thích:
Grid phù hợp với bố cục dạng hàng và cột. Dễ tạo lưới ảnh đều nhau.

3. Layout blog: main content + sidebar
- Grid
Giải thích:
Grid giúp chia bố cục thành các cột rõ ràng như content và sidebar.

4. Footer với 4 cột thông tin (Về chúng tôi, Liên kết, Hỗ trợ, Liên hệ)
- Grid
Giải thích:
Grid giúp chia đều 4 cột và quản lý bố cục dễ dàng.

5. Card sản phẩm (ảnh trên, text giữa, nút dưới — nút luôn dính đáy)
- Flexbox
Giải thích:
Flexbox theo chiều dọc giúp sắp xếp nội dung trong card và dùng margin-top: auto để đẩy nút xuống đáy.

Câu C2

1. Lỗi 1: Cards không đều chiều cao — nút "Mua" bị nhảy lên/xuống
 ![ảnh lỗi](./Screenshot_Answer/Screenshot%202026-06-07%20140950.png)
Nguyên nhân:
Các card có lượng nội dung khác nhau nên chiều cao khác nhau. Nút "Mua" nằm ngay sau nội dung nên vị trí không đồng đều.

Code sửa:

.card{
    width: 30%;
    margin: 1.5%;
    display: flex;
    flex-direction: column;
}

.card .btn{
    margin-top: auto;
}

![ảnh sau khi sửa](./Screenshot_Answer/Screenshot%202026-06-07%20141018.png)
2. Lỗi 2: Muốn items nằm giữa cả ngang lẫn dọc trong container 100vh, nhưng item vẫn dính góc trái trên
![ảnh lỗi](./Screenshot_Answer/Screenshot%202026-06-07%20141105.png)
Nguyên nhân:
Container đã dùng display: flex nhưng chưa căn giữa theo trục ngang và trục dọc.

Code sửa:

.hero{
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}

.hero-content{
    text-align: center;
}
![ảnh sau khi sửa](./Screenshot_Answer/Screenshot%202026-06-07%20141321.png)
3. Lỗi 3: Sidebar bị co lại khi content quá dài
![ảnh lỗi](./Screenshot_Answer/Screenshot%202026-06-07%20141608.png)
Nguyên nhân:
Flexbox mặc định cho phép các phần tử co lại để vừa container nên sidebar có thể bị thu hẹp.

Code sửa:

.layout{
    display: flex;
}

.sidebar{
    width: 250px;
    flex-shrink: 0;
}

.content{
    flex: 1;
}