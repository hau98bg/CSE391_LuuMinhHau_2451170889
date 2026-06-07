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

