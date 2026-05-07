# openplace — Hướng dẫn thiết lập với Windows

Hướng dẫn này sẽ giúp bạn chuẩn bị một thiết bị **Windows** để chạy **openplace**.

---

## 1. Cài đặt trước hết

Bạn cần **Node.js**, **Git**, **MariaDB**, **Caddy**.

- Sử dụng **winget** (Windows 10/11 PowerShell với quyền Quản trị):

```powershell
winget install Git.Git
winget install OpenJS.NodeJS.LTS
winget install CaddyServer.Caddy
winget install nssm
```

- Sử dụng **Chocolatey** (cmd với quyền Quản trị):

```cmd
choco install git nodejs-lts caddy nssm -y
```

- Tải MariaDB Server theo liên kết sau: [MariaDB Server](https://mirror.mva-n.net/mariadb///mariadb-12.0.2/winx64-packages/mariadb-12.0.2-winx64.msi)
- Chạy Trình cài đặt
- Đặt một mật khẩu gốc và giữ mọi thứ theo mặc định
  
---

## 2. Sao chép repo

```powershell
git clone --recurse-submodules https://github.com/openplaceteam/openplace
cd openplace
```

---

## 3. Cài đặt các phần phụ thuộc của Node

```powershell
npm install
npm install -g pm2
```

---

## 4 Dừng các dịch vụ Caddy (cần thiết nếu được cài đặt dưới dạng dịch vụ)

- Nếu Caddy được cài đặt dưới dạng dịch vụ, dừng nó bằng **Services.msc**  
- Hoặc tự làm:

```powershell
net stop caddy
```

---

## 5. Cấu hình và xây dựng cơ sở dữ liệu

1. Sao chép `.env.example` đến `.env`:

```powershell
Copy-Item .env.example .env
```

Chỉnh sửa tệp `.env` và thay thế `root:password` với mật khẩu gốc MariaDB của bạn và thay đổi `JWT_SECRET`.

> [CẢNH BÁO ⚠️]
> Thay thế các kí tự đặc biệt được liệt kê trong bảng sau: [Percent-Encoding](https://developer.mozilla.org/en-US/docs/Glossary/Percent-encoding)

---

## 6. Thiết lập Prisma và cơ sở dữ liệu

```powershell
npm run db:generate
npm run setup
```

---

## 7.A Chạy riêng đối với mỗi máy chủ

chạy frontend trong một terminal: 
```powershell
npm run dev
```
chạy caddy trong terminal thứ hai:
```powershell
caddy run --config .\Caddyfile
```

---

## 7.B Chạy cả hai trong một terminal

```cmd
npm run exec
```

## 7.C Chạy Caddy trong nền và node ra trước

```
pm2 start ecosystem.config.cjs
pm2 save
```


---

## Khởi động máy chủ của bạn

- Đối với production, thiết lập một chứng chỉ SSL.  
- Đối với sử dụng cục bộ/riêng tư, truy cập đến:

```
https://{your-local-IP}:8080
```

> [CẢNH BÁO ⚠️]
> ⚠️ **Quan trọng:** openplace chỉ hoạt động đối với HTTPS. nếu bạn truy cập qua HTTP, bạn sẽ bị **400 Bad Request**.


---

## Cập nhật cơ sở dữ liệu

Nếu sơ đồi có sự thay đổi, hãy chạy:

```powershell
npm run db:push
```
