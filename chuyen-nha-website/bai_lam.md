# BÀI LÀM – HACKATHON 02

- **Mã đề:** 10
- **Họ tên:** Bùi Hải Đăng
- **Lớp:** CNTT2
- **Link repository:** 
- **Hệ điều hành (Windows/macOS):** Window

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
 pwd
 ls -Force
 mv .\checklist_chuyen_nha.txt .\docs\
  mkdir backup
  cp .\data\hop_dong_thang_10.xlsx .\backup\
  rm .\temp_010.tmp
  cd .\logs\
  ls -Force
  cd ..
  ls -Force


```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
  Directory: C:\Users\BUI HAI DANG\Downloads\starter-kit (8)\starter-kit\chuyen-nha-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026   1:37 PM                backup
d-----        11/11/2026   1:34 PM                data
d-----        11/11/2026   1:37 PM                docs
d-----        11/11/2026   1:33 PM                evidence
d-----        11/11/2026   1:34 PM                logs
d-----        11/11/2026   1:31 PM                web
------         11/3/2026   7:08 AM             70 .env
-a----        11/11/2026   1:35 PM           2514 bai_lam.md

```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```shell
 Get-Content .\logs\request.log | Select-String "status=500" > .\logs\loi_500.txt

```

### 2 dòng đầu tiên trong logs/loi_500.txt

```text
2026-10-28 08:09:39 POST /api/dat-xe status=500
2026-10-28 08:13:50 POST /api/thanh-toan status=500


```

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
 (Get-Content .\logs\request.log | Select-String "status=404"). count

```

```text
4

```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
 Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
 .\tong_hop.ps1

```

### Nội dung file logs/tong_hop.txt

```text
2026-10-28 08:28:45 GET /dat-xe-cu status=404
2026-10-28 08:41:29 GET /khuyen-mai-cu status=404
2026-10-28 08:50:02 GET /khuyen-mai-cu status=404
2026-10-28 09:05:46 GET /tin-tuc status=404




Count    : 6
Average  : 
Sum      : 
Maximum  : 
Minimum  : 
Property : 



```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x ] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [x ] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [x ] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 |network  |Failed to load resource: net::ERR_FILE_NOT_FOUND  |Thay logo.png -> logo-movefast.png  |
| 2 |console  |Uncaught ReferenceError: hienThiGoi is not defined  |Thay hienThiGoi -> hienThiGoiChuyen   |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:** Tôi là sinh viên năm nhất của PTIT chưa fix lỗi hiển thị dữ liệu của web bao giờ , tôi cần được bạn trưởng nhóm giúp đỡ tôi
- **Expected:** Bây giờ trang web của tôi muốn có đủ dữ liệu ở bảng hiển thị giao diện
- **Actual:** Dữ liệu trên trang web không có gì và tôi vào tab console thấy thông báo lỗi app.js:18 Uncaught ReferenceError: hienThiGoi is not defined 
- **Log:** app.js:18 Uncaught ReferenceError: hienThiGoi is not defined

### Câu tìm kiếm Google

```text
site:stackoverflow.com "Uncaught ReferenceError:  hienThiGoi is not defined"

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/hop_dong_thang_10.xlsx`, không cần ghi vào đây.
