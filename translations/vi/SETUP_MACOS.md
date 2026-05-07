# openplace — Hướng dẫn thiết lập với MacOS

Hướng dẫn này sẽ giúp bạn chuẩn bị một thiết bị **macOS** để chạy **openplace**.

---

## Bước 1: Cài đặt trước hết
Hãy chắc chắn rằng bạn có những thứ sau đây đã được cài đặt trên hệ thống của bạn:
- **Homebrew**
- **Node.js**
- **Git**

---

## Bước 2: Sao chép repo
```bash
git clone --recurse-submodules https://github.com/openplaceteam/openplace
cd openplace
```

---

## Bước 3: Cài đặt các phần phụ thuộc
```bash
npm i && brew install mariadb caddy nss
```
Nếu brew không tự động khởi tạo các dịch vụ, hãy chạy các lệnh sau:
```bash
brew services start mariadb
brew services start caddy
```

---

## Bước 4: Cấu hình và xây dựng cơ sở dữ liệu

Chạy lệnh cài đặt an toàn cho MySQL:
```bash
sudo mysql_secure_installation
```

Làm theo hướng dẫn sau:
1. Nhấn **Enter** cho mật khẩu gốc hiện tại.
2. Nhập **`n`** khi được yêu cầu đổi sang xác thực unix_socket.
3. Nhập **`y`** khi được yêu cầu đổi mật khẩu gốc.  
   ⚠️ Vui lòng **không** sử dụng "mật khẩu" được hiển thị trong bản demo này.
4. Nhập **`y`** để loại bỏ các người dùng ẩn danh.
5. Chọn xem có cho phép đăng nhập bằng tài khoản root từ xa hay không. (**khuyến khích: y**).
6. Nhập **`y`** để loại bỏ cơ sở dữ liệu thử nghiệm.
7. Nhập **`y`** để tải lại cấu hình.

Sau đó, cấu hình môi trường:
```bash
cp .env.example .env
```
Cập nhật tệp `.env` với mật khẩu MySQL mà bạn chọn.

---

## Bước 5: Thiết lập cơ sở dữ liệu

Chạy các lệnh Prisma sau:
```bash
npm run db:generate
npm run setup
```

---

## Bước 6: Chạy ứng dụng

Khởi chạy máy chủ dev:
```bash
npm run dev
```

Trong một terminal khác, chạy Caddy:
```bash
caddy run --config Caddyfile
```

---

## Lưu ý đối với SSL
openplace **yêu cầu HTTPS**.  
Nếu bạn đang thử nghiệm cục bộ, bạn có thể truy cập ứng dụng tại:
```
https://{IP}:8080
```
⚠️ Cố gắng sử dụng HTTP sẽ báo **lỗi HTTP 400**.

---

## Cập nhật cơ sở dữ liệu
Nếu sơ đồ cơ sở dữ liệu thay đổi, hãy cập nhật nó bằng:
```bash
npm run db:push
```
