# PHẦN A

/A1
*1
5 bước xảy ra (từ DNS lookup đến render):
1. DNS Lookup: Trình duyệt gửi yêu cầu đến máy chủ DNS để tìm địa chỉ IP tương ứng với tên miền shopee.vn.
2. TCP Handshake: Trình duyệt thiết lập kết nối TCP với máy chủ thông qua địa chỉ IP vừa tìm được.
3. TLS/SSL Handshake: Vì đây là HTTPS, trình duyệt và máy chủ tiến hành trao đổi chứng chỉ bảo mật để mã hóa dữ liệu.
4. HTTP Request: Trình duyệt gửi một yêu cầu HTTP GET đến máy chủ để lấy nội dung trang web (file HTML).
5. HTTP Response & Rendering: Máy chủ gửi lại file HTML. Trình duyệt nhận file, phân tích (parse) HTML, tải thêm các tài liệu liên quan (CSS, JS, hình ảnh) và tiến hành dựng (render) giao diện lên màn hình.

*2
Tab Network cho thấy thông tin về tất cả các tài nguyên mà trang web đang tải về, bao gồm: các yêu cầu HTTP, trạng thái phản hồi, kích thước file, thời gian tải và loại tài nguyên (hình ảnh, script, stylesheet, v.v.).
- Ảnh mô tả network: network.png,network.png.

/A2
- Lỗi 1: Dùng <div class="header">
sửa: <header>
- Lỗi 2: Dùng <div class="menu">
sửa: <nav>
- Lỗi 3: Dùng <div class="title">
sửa: <h1> hoặc <h2>
- Lỗi 4: Dùng <div class="footer">
sửa: <footer>

/A3
Hộp 1  
Text A Text B  
Hộp 2  
Text C **Text D**  
Hộp 3 

/A4
Giải thích sự khác nhau giữa <thead>, <tbody>, <tfoot>:
- <thead> (Table Header): Dùng để chứa hàng đầu tiên của bảng (các tiêu đề cột). Nó giúp xác định phần thông tin mô tả cho dữ liệu bên dưới. Khi in một bảng dài ra nhiều trang giấy, một số trình duyệt sẽ lặp lại phần <thead> ở đầu mỗi trang.

- <tbody> (Table Body): Đây là phần chính của bảng, chứa toàn bộ dữ liệu thực tế. Một bảng có thể có nhiều <tbody> để phân chia các nhóm dữ liệu khác nhau.

- <tfoot> (Table Footer): Dùng để chứa hàng tổng kết hoặc thông tin bổ sung ở cuối bảng (ví dụ: tổng tiền, tổng điểm). Tương tự như <thead>, khi in ấn, phần này có thể được lặp lại ở cuối mỗi trang giấy.

Tại sao KHÔNG NÊN dùng table để tạo layout trang web? (Ghi rõ ít nhất 3 lý do):
- Vi phạm ý nghĩa Semantic (Semantic Correctness): * Thẻ <table> được sinh ra chỉ để hiển thị dữ liệu bảng (tabular data) như danh sách sinh viên, bảng lương, thời khóa biểu. Dùng nó để dàn trang (chia cột trái, cột phải) làm cho các bộ máy tìm kiếm (Google) và các thiết bị đọc màn hình dành cho người khiếm thị không hiểu được cấu trúc thực sự của nội dung trang web.

- Khó khăn khi làm Responsive (Mobile-friendly): * Bảng có cấu trúc rất cứng nhắc. Trên màn hình máy tính có thể hiển thị tốt, nhưng trên điện thoại di động, bảng không thể tự động xếp chồng các cột lên nhau một cách linh hoạt như CSS Flexbox hay Grid. Điều này khiến người dùng phải kéo ngang màn hình rất khó chịu.

- Ảnh hưởng đến tốc độ tải trang (Performance): * Trình duyệt thường phải nhận được toàn bộ nội dung trong thẻ <table> thì mới bắt đầu tính toán và hiển thị ra màn hình. Nếu bạn dùng bảng cho toàn bộ layout, người dùng sẽ phải chờ lâu hơn để thấy được nội dung thay vì cách hiển thị từng phần (progressive rendering) như khi dùng các thẻ <div>, <header>, <main>.

# Phần C

/C1
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <title>Chi tiết sản phẩm</title>
</head>
<body>

  <!-- Header + Navigation -->
  <header> <!-- header cho phần đầu trang -->
    <nav> <!-- nav cho menu điều hướng -->
      <!-- Liên kết menu -->
    </nav>
  </header>

  <!-- Breadcrumb -->
  <nav aria-label="breadcrumb"> <!-- nav vì đây là điều hướng phụ -->
    <ol> <!-- ol vì breadcrumb có thứ tự -->
      <li><a href="/">Trang chủ</a></li>
      <li><a href="/dien-thoai">Điện thoại</a></li>
      <li>iPhone 16</li>
    </ol>
  </nav>

  <!-- Khu vực sản phẩm -->
  <main> <!-- main cho nội dung chính -->

    <!-- Hình ảnh sản phẩm -->
    <section> <!-- section cho nhóm hình ảnh -->
      <!-- 5 ảnh sản phẩm -->
      <img src="..." alt="Ảnh 1">
      <img src="..." alt="Ảnh 2">
      <img src="..." alt="Ảnh 3">
      <img src="..." alt="Ảnh 4">
      <img src="..." alt="Ảnh 5">
    </section>

    <!-- Thông tin sản phẩm -->
    <section>
      <h1>Tên sản phẩm</h1> <!-- h1 cho tên -->
      <p>Giá: ...</p>
      <p>Đánh giá: ★★★★☆</p>
      <p>Mô tả ngắn...</p>
    </section>

    <!-- Bảng thông số kỹ thuật -->
    <section>
      <table>
        <thead> <!-- tiêu đề cột -->
          <tr><th>Thông số</th><th>Giá trị</th></tr>
        </thead>
        <tbody> <!-- dữ liệu -->
          <tr><td>Màn hình</td><td>6.1 inch</td></tr>
          <tr><td>Chip</td><td>A18</td></tr>
        </tbody>
        <tfoot> <!-- ghi chú -->
          <tr><td colspan="2">Thông tin tham khảo</td></tr>
        </tfoot>
      </table>
    </section>

    <!-- Review/Comment -->
    <section>
      <h2>Đánh giá & Bình luận</h2>
      <!-- Form nhập bình luận -->
      <form>
        <textarea placeholder="Viết bình luận..."></textarea>
        <button>Gửi</button>
      </form>
      <!-- Danh sách bình luận -->
    </section>

    <!-- Sidebar: sản phẩm tương tự -->
    <aside> <!-- aside cho nội dung phụ -->
      <h2>Sản phẩm tương tự</h2>
      <!-- Liệt kê sản phẩm -->
    </aside>

  </main>

  <!-- Footer -->
  <footer> <!-- footer cho phần cuối trang -->
    <p>Bản quyền © 2026</p>
  </footer>

</body>
</html>

/C2
## Câu C2 - So sánh & Tranh luận

Một đồng nghiệp cho rằng chỉ cần dùng `<div>` với class là đủ, không cần học semantic HTML. Tôi phản biện rằng cách tiếp cận này bỏ qua nhiều lợi ích quan trọng.
Thứ nhất, về SEO: Semantic HTML giúp công cụ tìm kiếm hiểu rõ cấu trúc trang. Ví dụ, khi dùng `<article>` cho một bài viết, Google sẽ nhận diện đây là nội dung chính, từ đó index chính xác hơn. Nếu chỉ dùng `<div>`, công cụ tìm kiếm khó phân biệt đâu là nội dung chính, đâu là phần phụ.
Thứ hai, về Accessibility: Người dùng khiếm thị dựa vào trình đọc màn hình để điều hướng. Các thẻ như `<header>`, `<nav>`, `<main>` cung cấp thông tin ngữ nghĩa rõ ràng, giúp họ dễ dàng di chuyển trong trang. Nếu chỉ dùng `<div>`, trải nghiệm của họ sẽ bị hạn chế.
Ví dụ cụ thể: `<nav>` cho menu điều hướng. Trình đọc màn hình sẽ thông báo “Navigation region”, giúp người dùng biết đây là khu vực menu. Nếu chỉ dùng `<div class="nav">`, thông tin này không được cung cấp.
Tất nhiên, `<div>` vẫn có chỗ đứng. Khi cần một container để nhóm nội dung hoặc áp dụng CSS mà không có thẻ semantic phù hợp, `<div>` là lựa chọn hợp lý. Tuy nhiên, việc kết hợp semantic HTML với `<div>` đúng chỗ sẽ tạo ra trang web vừa chuẩn kỹ thuật, vừa thân thiện với người dùng.

# Phần D
https://drive.google.com/drive/folders/17xxEDWvb3lFzJgE6CDhlCEDcGmboYFZB?usp=drive_link