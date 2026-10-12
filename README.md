## 1. Mục tiêu
- Sử dụng Docker Compose V2 để điều phối nhiều container.
- Quản lý cấu hình bằng file `.env`.
- Tạo Custom Network và Named Volume.
- Kiểm tra kết nối giữa Backend và PostgreSQL.

## 2. Các thành phần
- `backend`: Container Alpine dùng để kiểm thử kết nối PostgreSQL.
- `database`: PostgreSQL 15 Alpine.
- `backend-net`: Network cho phép hai service giao tiếp nội bộ.
- `pgdata`: Named Volume lưu dữ liệu database.
- `.env`: Chứa cấu hình thực tế, không đưa lên GitHub.
- `.env.example`: File mẫu cấu hình.

## 3. Cách chạy
1. Sao chép `.env.example` thành `.env`.
2. Cập nhật các biến môi trường trong `.env`.
3. Khởi chạy: `docker compose up -d`.
4. Kiểm tra: `docker compose ps`.
5. Xem log: `docker compose logs -f`.
6. Dừng và xóa container, network: `docker compose down`.

## 4. Kết quả mong đợi
- Hai service được khởi chạy thành công.
- Backend phân giải được hostname `database`.
- PostgreSQL sử dụng volume `pgdata` để lưu dữ liệu.
- Các biến cấu hình được quản lý qua `.env`.

(2 file .env.example và .gitignore nộp lên github thì nó bị ẩn ạ)
