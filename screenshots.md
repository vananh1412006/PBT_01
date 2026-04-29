# Bài DevTools - Phân tích Shopee.vn

## 1. Tab Elements

### a. 3 thẻ semantic HTML5 được sử dụng

- <header>: nằm ở phần đầu trang, chứa logo và thanh tìm kiếm
- <nav>: chứa menu điều hướng (danh mục sản phẩm)
- <footer>: nằm cuối trang, chứa thông tin liên hệ và chính sách

### b. 2 thẻ không dùng đúng semantic (nếu có)

- <div> được dùng thay cho <section> để chứa các khối sản phẩm
- <span> được dùng thay cho <button> trong một số nút bấm

(Đính kèm screenshot: elements_1.png)

---

## 2. Phân tích Table

- Table hiển thị: danh sách sản phẩm / thông tin sản phẩm (giá, tên, đánh giá...)

- Có sử dụng:
  - <thead>: Có
  - <tbody>: Có

(Đính kèm screenshot: table.png)

---

## 3. Phân tích Form

- Form tìm kiếm trên đầu trang

- action: "/search"
- method: "GET"

- Các input types sử dụng:
  - text (ô tìm kiếm)
  - submit (nút tìm kiếm)

(Đính kèm screenshot: form.png)