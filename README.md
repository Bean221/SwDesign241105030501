## Critical Rendering Path

### Giới thiệu

**Critical Rendering Path (CRP)** là quá trình trình duyệt chuyển đổi HTML, CSS và JavaScript thành nội dung có thể hiển thị trên màn hình. Nếu có các yếu tố ngăn cản quá trình này, trang web có thể **tải chậm** hoặc **không hiển thị đúng cách**.

### Các bước chính trong CRP

1. **Xử lý HTML**: Trình duyệt tải HTML và tạo ra **DOM (Document Object Model)**.
2. **Xử lý CSS**: CSS được tải về và xử lý thành **CSSOM (CSS Object Model)**.
3. **Kết hợp DOM & CSSOM**: DOM và CSSOM kết hợp để tạo **Render Tree**.
4. **Layout (Bố cục)**: Trình duyệt tính toán vị trí của các phần tử.
5. **Painting (Vẽ nội dung)**: Trình duyệt vẽ các phần tử lên màn hình.

### Cách tối ưu hóa CRP

- **Giảm số lượng tài nguyên chặn hiển thị** bằng cách sử dụng `async` hoặc `defer` với JavaScript.
- **Sử dụng `preload` và `prefetch`** để tải trước các tài nguyên quan trọng.
- **Nén và tối ưu hóa hình ảnh** để tăng tốc thời gian tải trang.

---

## XSS, CSRF

### XSS (*Cross-Site Scripting*)

**XSS** là một trong những lỗ hổng bảo mật phổ biến nhất trên web. Nó cho phép kẻ tấn công **chèn mã độc JavaScript** vào trang web để thực thi trên trình duyệt của nạn nhân.

#### Các loại XSS:

1. **Stored XSS**: Mã độc được lưu trữ trên máy chủ và được tải về khi người dùng truy cập trang web.
2. **Reflected XSS**: Mã độc được chèn vào URL hoặc form input và phản hồi lại người dùng.
3. **DOM-based XSS**: Tấn công xảy ra khi JavaScript trên client-side xử lý dữ liệu không an toàn.

#### Cách phòng chống:

- **Lọc và mã hóa đầu vào người dùng** trước khi hiển thị trên trang.
- **Sử dụng CSP (Content Security Policy)** để hạn chế việc thực thi script.
- **Tránh sử dụng `eval()` hoặc `innerHTML`** khi xử lý dữ liệu đầu vào.

### CSRF (*Cross-Site Request Forgery*)

**CSRF** là một kiểu tấn công mà kẻ tấn công **lợi dụng phiên đăng nhập hợp lệ của người dùng** để thực hiện các hành động trái phép.

#### Cách phòng chống:

- **Sử dụng token CSRF** trong các biểu mẫu và request quan trọng.
- **Kiểm tra referrer header** để đảm bảo request đến từ nguồn hợp lệ.
- **Giới hạn thời gian sống của session** để giảm thiểu rủi ro.

---

## HTTP & SSL

### HTTP (*HyperText Transfer Protocol*)

HTTP là giao thức truyền tải siêu văn bản được sử dụng trên World Wide Web.

#### Nhược điểm của HTTP:
- Không bảo mật, dễ bị **tấn công Man-in-the-Middle (MITM)**.
- Dữ liệu được truyền dưới dạng **plain text** và có thể bị đánh cắp.

### SSL (*Secure Sockets Layer*)

**SSL** là công nghệ mã hóa giúp bảo vệ dữ liệu truyền tải giữa trình duyệt và máy chủ web.

#### Cách hoạt động của SSL:
- Trình duyệt yêu cầu chứng chỉ SSL từ máy chủ.
- Máy chủ gửi chứng chỉ SSL đã được xác thực bởi **CA (Certificate Authority)**.
- Trình duyệt kiểm tra chứng chỉ và thiết lập kết nối an toàn.

#### Tại sao cần SSL?
- **Bảo vệ dữ liệu người dùng** khi truyền qua internet.
- **Tăng độ tin cậy của website** đối với khách hàng.
- **Cải thiện SEO** vì Google ưu tiên các trang web có HTTPS.

---

## CSP (*Content Security Policy*)

**CSP** giúp ngăn chặn **tấn công XSS và data injection** bằng cách kiểm soát tài nguyên nào được phép tải trên trang web.

### Cấu hình CSP cơ bản:
```http
Content-Security-Policy: default-src 'self'; img-src https://*; child-src 'none';
```

### Cách triển khai CSP
- **Sử dụng HTTP header** để đặt chính sách bảo mật.
- **Dùng thẻ `<meta>`** nếu không thể thay đổi cấu hình máy chủ.

---

# HTML

## Semantic

Semantic HTML giúp **công cụ tìm kiếm hiểu nội dung trang web tốt hơn**, từ đó cải thiện **SEO và khả năng truy cập**.

### Các thẻ HTML Semantic phổ biến:
| Thẻ | Mô tả |
|------|--------------------------------|
| `<article>` | Định nghĩa một bài viết độc lập |
| `<section>` | Chia trang thành các phần nội dung |
| `<header>` | Phần đầu của trang hoặc một phần nội dung |
| `<footer>` | Phần chân trang hoặc phần cuối của nội dung |

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
