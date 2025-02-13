## Critical Rendering Path (CRP)

### Giới thiệu

**Critical Rendering Path (CRP)** là quá trình trình duyệt biến đổi HTML, CSS và JavaScript thành nội dung hiển thị trên màn hình. Việc tối ưu CRP rất quan trọng để đảm bảo trải nghiệm người dùng mượt mà và tăng tốc độ tải trang.

### Các bước trong Critical Rendering Path

1. **Xử lý HTML**:
   - Trình duyệt tải HTML từ máy chủ và xây dựng **DOM (Document Object Model)**.
   - DOM là cây cấu trúc phản ánh nội dung của tài liệu HTML.

2. **Xử lý CSS**:
   - Trình duyệt tải các file CSS và tạo **CSSOM (CSS Object Model)**.
   - CSSOM quyết định cách trang web sẽ hiển thị.

3. **Kết hợp DOM và CSSOM**:
   - DOM và CSSOM kết hợp tạo thành **Render Tree**.
   - Render Tree chỉ bao gồm các phần tử có ảnh hưởng đến giao diện người dùng.

4. **Quá trình Layout (Bố cục)**:
   - Trình duyệt tính toán vị trí và kích thước của từng phần tử trên trang.
   
5. **Quá trình Painting (Vẽ nội dung lên màn hình)**:
   - Trình duyệt vẽ các phần tử trên màn hình dựa vào thông tin từ Render Tree.
   
### Cách tối ưu hóa CRP

- **Tránh chặn hiển thị bởi CSS và JavaScript** bằng cách sử dụng `async` hoặc `defer`.
- **Tận dụng Lazy Loading** để tải nội dung khi cần thiết.
- **Giảm số lượng HTTP request** bằng cách gộp nhiều file CSS và JavaScript thành một.
- **Sử dụng CDN (Content Delivery Network)** để tối ưu tốc độ tải tài nguyên.
- **Tối ưu hình ảnh và sử dụng định dạng ảnh phù hợp (WebP, AVIF,...)**.

---

## XSS, CSRF

### Cross-Site Scripting (XSS)

**XSS** là một kiểu tấn công phổ biến trong các ứng dụng web. Hacker chèn mã JavaScript độc hại vào trang web để thực thi trên trình duyệt của người dùng.

#### Các loại XSS:
1. **Stored XSS**: Hacker lưu mã độc trên máy chủ và mã độc sẽ chạy mỗi khi người dùng truy cập trang.
2. **Reflected XSS**: Hacker chèn mã vào URL hoặc form input và phản hồi lại người dùng.
3. **DOM-based XSS**: Tấn công xảy ra khi JavaScript trên client-side xử lý dữ liệu không an toàn.

#### Cách phòng chống:
- **Sử dụng bộ lọc đầu vào (input sanitization)** để ngăn chặn mã độc.
- **Dùng Content Security Policy (CSP)** để giới hạn các nguồn script được phép thực thi.
- **Tránh sử dụng `innerHTML`, `eval()`**.

### Cross-Site Request Forgery (CSRF)

**CSRF** là một kiểu tấn công mà hacker lừa người dùng thực hiện hành động trái phép trên một trang web mà họ đã đăng nhập.

#### Cách phòng chống:
- **Sử dụng CSRF Token** trong các request quan trọng.
- **Kiểm tra HTTP Referrer Header** để đảm bảo request đến từ nguồn hợp lệ.
- **Giới hạn thời gian sống của session và yêu cầu xác thực lại**.

---

## HTTP & SSL

### HTTP (HyperText Transfer Protocol)

HTTP là giao thức truyền tải siêu văn bản, nền tảng của World Wide Web.

#### Nhược điểm của HTTP:
- Không có bảo mật, dễ bị tấn công **Man-in-the-Middle (MITM)**.
- Dữ liệu truyền tải dưới dạng **plain text**, dễ bị đánh cắp.

### SSL (Secure Sockets Layer)

SSL là công nghệ mã hóa giúp bảo vệ dữ liệu truyền tải giữa máy chủ và trình duyệt.

#### Cách hoạt động:
1. Trình duyệt yêu cầu chứng chỉ SSL từ máy chủ.
2. Máy chủ gửi chứng chỉ đã được xác thực bởi **CA (Certificate Authority)**.
3. Trình duyệt kiểm tra chứng chỉ và thiết lập kết nối an toàn.

#### Lợi ích của SSL:
- **Bảo mật dữ liệu người dùng**.
- **Tăng độ tin cậy của website**.
- **Cải thiện SEO**, vì Google ưu tiên các trang HTTPS.

---

## CSP (Content Security Policy)

CSP giúp ngăn chặn tấn công **XSS và data injection** bằng cách kiểm soát các tài nguyên được tải trên trang web.

### Cấu hình CSP cơ bản:
```http
Content-Security-Policy: default-src 'self'; img-src https://*; child-src 'none';
```

### Cách triển khai CSP:
- **Dùng HTTP header**.
- **Dùng thẻ `<meta>` trong HTML** nếu không thể thay đổi cấu hình máy chủ.

---

# HTML

## Semantic HTML

Semantic HTML giúp trang web dễ hiểu hơn với trình duyệt và công cụ tìm kiếm.

### Các thẻ HTML Semantic phổ biến:
| Thẻ | Mô tả |
|------|--------------------------------|
| `<article>` | Định nghĩa bài viết độc lập |
| `<section>` | Chia trang thành các phần nội dung |
| `<header>` | Phần đầu của trang hoặc phần nội dung |
| `<footer>` | Phần chân trang hoặc phần cuối nội dung |

Ví dụ:
```html
<article>
  <h1>Tiêu đề bài viết</h1>
  <p>Nội dung bài viết...</p>
</article>
```

---

## `<script>` & `<link>`

### 1. Thẻ `<script>`

Dùng để nhúng JavaScript vào trang web.

#### Các cách sử dụng:
- **Nhúng trực tiếp**:
```html
<script>
  console.log("Hello, world!");
</script>
```
- **Tải từ file bên ngoài**:
```html
<script src="script.js"></script>
```

#### Thuộc tính quan trọng:
| Thuộc tính | Mô tả |
|------------|----------------------------|
| `src` | Đường dẫn đến file JavaScript |
| `async` | Tải script không đồng bộ |
| `defer` | Tải script sau khi HTML tải xong |

### 2. Thẻ `<link>`

Dùng để liên kết với file CSS hoặc các tài nguyên khác.

#### Cách sử dụng:
- **Liên kết CSS**:
```html
<link rel="stylesheet" href="style.css">
```
- **Liên kết favicon**:
```html
<link rel="icon" href="favicon.ico" type="image/x-icon">
```

#### Thuộc tính quan trọng:
| Thuộc tính | Mô tả |
|------------|------------------------|
| `rel` | Loại tài nguyên liên kết |
| `href` | Đường dẫn đến file liên kết |
| `type` | Kiểu MIME của tài nguyên |
| `media` | Chỉ định kiểu thiết bị áp dụng CSS |

**Vị trí đặt `<link>`**: Trong `<head>` để trình duyệt tải CSS trước khi hiển thị nội dung trang.
