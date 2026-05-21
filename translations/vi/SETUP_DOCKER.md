# openplace — Hướng dẫn thiết lập với Docker

Hướng dẫn này sẽ giúp bạn chạy **openplace** với Docker.

## Trước hết

Bạn cần phải có **Docker** và **Docker Compose** đã được cài đặt sẵn trên thiết bị của bạn.

### Cài đặt Docker

-   **Windows**: Tải Docker Desktop từ [docker.com](https://www.docker.com/products/docker-desktop/)
-   **macOS**: Tải Docker Desktop từ [docker.com](https://www.docker.com/products/docker-desktop/)
-   **Linux**: Làm theo hướng dẫn cho bản phân phối của bạn tại [docs.docker.com](https://docs.docker.com/engine/install/)

## 1. Sao chép repo

```bash
git clone --recurse-submodules https://github.com/openplaceteam/openplace
cd openplace
```

## 2. Cấu hình môi trường

1. Sao chép `.env.example` đến `.env`:

```bash
cp .env.example .env
```

2. Chỉnh sửa tệp `.env` và cấu hình cài đặt của bạn:
    - Thiết lập `JWT_SECRET` (tạo một chuỗi kí tự an toàn ngẫu nhiên)
    - Thiết lập `DATABASE_URL` đến `"mysql://root:password@db/openplace"`
    - Mật khẩu gốc MariaDB được đặt là `password` (thay đổi nếu cần thiết)

> [CẢNH BÁO ⚠️]
> Thay thế các kí tự đặc biệt được liệt kê trong bảng sau: [Percent-Encoding](https://developer.mozilla.org/en-US/docs/Glossary/Percent-encoding)

## 3. Khởi động ứng dụng

Chạy toàn bộ hệ thống với Docker Compose:

```bash
docker-compose up -d
```

Điều này sẽ bắt đầu:

-   **Cơ sở dữ liệu MariaDB** tại cổng 3306
-   **Ứng dụng Node.js** (backend)
-   **Proxy ngược Caddy** tại cổng 443

## 4. Truy cập ứng dụng

Một khi toàn bộ dịch vụ đều đang chạy, bạn có thể truy cập openplace tại:

```
http://localhost
https://localhost
```
