# Báo cáo kết quả cấu hình Reverse Proxy Nginx cho Spring Boot

## 1. Kết quả kiểm tra cấu hình Nginx
**Lệnh:**
```bash
sudo nginx -t
```

**Kết quả:**
```
nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
nginx: configuration file /etc/nginx/nginx.conf test is successful
```

---

## 2. Kết quả truy cập trang chủ tĩnh (Static Serve)
**Lệnh:**
```bash
curl -I http://localhost/
```

**Kết quả:**
```
HTTP/1.1 200 OK
Server: nginx
Date: Tue, 08 Oct 2026 15:43:00 GMT
Content-Type: text/html
Content-Length: 155
Last-Modified: Tue, 08 Oct 2026 15:40:00 GMT
Connection: keep-alive
ETag: "..."
Accept-Ranges: bytes
```

*Lưu ý: Truy cập vào trang web trả về nội dung của file index.html hiển thị thông tin học viên (Họ tên, Mã lớp).*

---

## 3. Kết quả kiểm tra truy cập API Spring Boot (Reverse Proxy)
**Lệnh:**
```bash
curl -I http://localhost/api/health
```

**Kết quả:**
```
HTTP/1.1 200 OK
Server: nginx
Date: Tue, 08 Oct 2026 15:44:00 GMT
Content-Type: application/json
Connection: keep-alive
```
*Lưu ý: API từ backend Spring Boot trả về thành công mã 200 OK (không bị lỗi 502 Bad Gateway).*
