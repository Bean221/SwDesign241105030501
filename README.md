## Critical Rendering Path

Kiểm tra **PageSpeed ​​Insights** sẽ cho bạn biết phần tử nào chặn tốc độ một trang hiển thị (*render*).

**Critical rendering path** được hình thành bởi đối tượng (như CSS và JavaScript) phải tải trước khi nội dung có thể hiển thị trên màn hình. Nếu nội dung này bị chặn, trang của bạn sẽ **render chậm** hoặc hoàn toàn **không render**.

Hãy chú ý đến điều này và giữ cho **rendering path không có chướng ngại vật**.

---

## XSS, CSRF

### XSS (*Cross Site Scripting*)

**XSS** là một trong những tấn công phổ biến và nguy hiểm nhất đối với ứng dụng web. Kẻ tấn công **chèn mã độc** thông qua các đoạn script để thực thi chúng ở phía client.

- **Mục đích:** Đánh cắp dữ liệu nhận dạng của người dùng (cookies, session tokens,...)
- **Ngôn ngữ tấn công phổ biến:** JavaScript, HTML

Ví dụ về một đoạn mã XSS:
```html
<script>alert('Hacked!');</script>
```

### CSRF (*Cross-Site Request Forgery*)

**CSRF** là tấn công giả mạo yêu cầu chéo trang, trong đó kẻ tấn công lừa người dùng thực hiện các hành động **trái ý muốn** trên một trang web mà họ đã đăng nhập.

---

## HTTP & SSL

### HTTP (*HyperText Transfer Protocol*)

HTTP là giao thức truyền tải siêu văn bản, cho phép tìm nạp tài nguyên như tài liệu HTML.

- Hoạt động theo mô hình **client-server**
- Không bảo mật (dữ liệu truyền tải có thể bị đánh cắp)

### SSL (*Secure Sockets Layer*)

**SSL** là một công nghệ mã hóa kết nối giữa trình duyệt và máy chủ web.

- Bảo vệ dữ liệu người dùng
- Được sử dụng trong các trang web có **HTTPS**
- Quan trọng đối với **các giao dịch trực tuyến**

---

## CSP (*Content Security Policy*)

CSP là một lớp bảo mật giúp **ngăn chặn tấn công XSS** và **data injection**.

### Cách hoạt động của CSP

- CSP được thiết lập qua **HTTP headers**:
```http
Content-Security-Policy: default-src 'self'; img-src https://*; child-src 'none';
```

- Hoặc sử dụng trong **thẻ `<meta>`**:
```html
<meta http-equiv="Content-Security-Policy" content="default-src 'self'; img-src https://*; child-src 'none';">
```

---

# HTML

## Semantic

**Semantics trong SEO** giúp công cụ tìm kiếm hiểu nội dung trang web dễ dàng hơn.

- **Tối ưu hóa nội dung** giúp trang web **tăng thứ hạng tìm kiếm**
- **Sử dụng từ khóa tự nhiên** thay vì nhồi nhét

Ví dụ về HTML Semantic:
```html
<article>
  <h1>Tiêu đề bài viết</h1>
  <p>Nội dung bài viết...</p>
</article>
```

---

## `<script>` & `<link>`

### 1. Thẻ `<script>`

Thẻ `<script>` dùng để nhúng JavaScript vào trang web.

#### Nhúng JavaScript trực tiếp:
```html
<script>
  console.log("Hello, world!");
</script>
```

#### Tải JavaScript từ file ngoài:
```html
<script src="script.js"></script>
```

#### Thuộc tính quan trọng của `<script>`:
| Thuộc tính | Mô tả |
|------------|-------------------------------------------------|
| `src` | Đường dẫn đến file JavaScript |
| `async` | Tải script không đồng bộ, không chặn HTML |
| `defer` | Tải script sau khi HTML tải xong, chạy theo thứ tự |

### 2. Thẻ `<link>`

Thẻ `<link>` dùng để liên kết với file CSS.

#### Liên kết file CSS ngoài:
```html
<link rel="stylesheet" href="style.css">
```

#### Liên kết favicon:
```html
<link rel="icon" href="favicon.ico" type="image/x-icon">
```

#### Thuộc tính quan trọng của `<link>`:
| Thuộc tính | Mô tả |
|------------|---------------------------------|
| `rel` | Loại tài nguyên liên kết (stylesheet, icon,...) |
| `href` | Đường dẫn đến file liên kết |
| `type` | Kiểu MIME của tài nguyên (vd: text/css) |
| `media` | Chỉ định kiểu thiết bị áp dụng CSS |

**Vị trí đặt `<link>`**: Trong `<head>` để trình duyệt tải CSS trước khi hiển thị nội dung trang.
