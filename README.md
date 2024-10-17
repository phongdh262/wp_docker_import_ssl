# Cài đặt WordPress với Docker Compose và Nginx

## Cấu trúc dự án

```
wordpress-docker/
│
├── docker-compose.yml
├── .env
├── wordpress/
├── db/
├── nginx/
│   ├── nginx.conf
│   ├── fullchain.pem
│   └── privkey.pem
└── README.md
```

## Giới thiệu

Dự án này hướng dẫn cách cài đặt và cấu hình một trang WordPress sử dụng Docker Compose, kết hợp với Nginx làm reverse proxy và MariaDB làm cơ sở dữ liệu. Cấu hình này đảm bảo hiệu suất tốt và có thể mở rộng dễ dàng.

## Hướng dẫn cài đặt

### Bước 1: Chuẩn bị môi trường

1. Cài đặt Docker và Docker Compose trên máy chủ của bạn.
2. Tạo một thư mục mới cho dự án: `mkdir wordpress-docker && cd wordpress-docker`

### Bước 2: Tạo các file cấu hình

1. Tạo file `docker-compose.yml` với nội dung đã cung cấp.
2. Tạo thư mục `nginx`: `mkdir nginx`
3. Tạo file `nginx/nginx.conf` với nội dung đã cung cấp.
4. Đặt các file SSL của bạn (`fullchain.pem` và `privkey.pem`) vào thư mục `nginx/`.

### Bước 3: Tạo file .env

Tạo file `.env` trong thư mục gốc của dự án với nội dung sau:

```
MYSQL_ROOT_PASSWORD=Gwvq8RpjnsRpprM
MYSQL_DATABASE=phongdh_wordpress
MYSQL_USER=phongdh_wordpress
MYSQL_PASSWORD=UYXpdx35UYXpdx35
```

### Bước 4: Khởi động các container

Chạy lệnh sau để khởi động các container:

```
docker-compose up -d
```

### Bước 5: Cấu hình WordPress

1. Truy cập trang web của bạn qua trình duyệt (ví dụ: https://phongdinh.id.vn).
2. Làm theo hướng dẫn cài đặt WordPress.


## Bảo mật

1. Thay đổi các mật khẩu mặc định trong file `.env`.
2. Cập nhật WordPress, themes và plugins thường xuyên.
3. Sử dụng plugin bảo mật (ví dụ: Wordfence) để tăng cường bảo mật.
4. Giới hạn số lần đăng nhập thất bại.
5. Kích hoạt xác thực hai yếu tố cho tài khoản admin.

## Backup

1. Tạo lịch backup tự động cho cơ sở dữ liệu và files WordPress.
2. Lưu trữ backups ở vị trí an toàn, tốt nhất là off-site.

## Monitoring

Sử dụng các công cụ monitoring để theo dõi hiệu suất và sự cố của website:
- Uptime monitoring
- Performance monitoring
- Security scanning
