# bai_lam

# BÀI LÀM – THI THỬ HACKATHON 02 (GAMEZONE)

- **Họ tên: vũ mạnh hùng**
- **Lớp: CNTT04**
- **Link repository:**
- **Hệ điều hành (Windows/macOS): WINDOWS**

## 4.2. Thao tác CLI

### Các lệnh đã chạy

```bash
6.	Hiển thị đường dẫn tuyệt đối thư mục hiện tại
- pwd
7.	Liệt kê nội dung, gồm cả file ẩn.
- gci -recurse -force
8.	Di chuyển cap_nhat.txt vào docs, file logo vào media
- mv ./cap_nhat.txt ./docs
- mv ./logo_game_zone.pnj ./media
9.	Sao chép logo từ media vào backup.
- cp ./media/logo_game_zone.pnj ./backup
10.	Xoá file .tmp ở gốc; không xoá file khác.
- rm ./temp_207.tmp
11.	Dùng đường dẫn tương đối vào logs, liệt kê nội dung rồi quay lại gốc.
- cd ./logs
- gci
- cd .. 
```

### Kết quả liệt kê toàn bộ dự án

```
Directory: C:\Users\h\OneDrive\Documents\hello
    luyentap\luyen_tap\starter-kit\gamezone-website

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/29/2026   8:16 AM                backup
d-----        10/29/2026   8:16 AM                data
d-----        10/29/2026   8:16 AM                docs
d-----        10/29/2026   8:16 AM                logs
d-----        10/29/2026   8:16 AM                media
-a----        10/29/2026   8:16 AM             70 .env
-a----        10/29/2026   8:16 AM            225 auto_report.ps1
-a----        10/29/2026   8:16 AM           1437 bai_lam.md

    Directory: C:\Users\h\OneDrive\Documents\hello
    luyentap\luyen_tap\starter-kit\gamezone-website\backup

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/29/2026   8:16 AM           8542 logo_game_zone.png

    Directory: C:\Users\h\OneDrive\Documents\hello
    luyentap\luyen_tap\starter-kit\gamezone-website\data

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/29/2026   8:16 AM          10951 giao_dich_thang_11.xls
                                                  x

    Directory: C:\Users\h\OneDrive\Documents\hello
    luyentap\luyen_tap\starter-kit\gamezone-website\docs

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/29/2026   8:16 AM             61 cap _nhat.txt

    Directory: C:\Users\h\OneDrive\Documents\hello
    luyentap\luyen_tap\starter-kit\gamezone-website\logs

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/29/2026   8:16 AM            720 auto_report.txt
-a----        10/29/2026   8:16 AM            660 daily_report.txt
-a----        10/29/2026   8:16 AM            986 game.log
-a----        10/29/2026   8:16 AM            192 tong_hop.txt

    Directory: C:\Users\h\OneDrive\Documents\hello
    luyentap\luyen_tap\starter-kit\gamezone-website\media

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/29/2026   8:16 AM           8542 logo_game_zone.png

```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```bash
12.	Lọc các dòng chứa ERROR trong logs/game.log, ghi vào logs/daily_report.txt.
- sls "ERROR" .\logs\game.log > .\logs\daily_report.txt
13.	Đọc file báo cáo để kiểm tra; ghi lệnh và dán 2 dòng lỗi đầu tiên vào bai_lam.md.
- .\logs\daily_report.txt

```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```
logs\game.log:2:2025-11-05 08:03:15 [ERROR] Mat ket noi may chu game
logs\game.log:4:2025-11-05 08:09:15 [ERROR] Mat ket noi may chu game

```

## 4.4. README.md

> Chấm trực tiếp trên `README.md` ở gốc dự án.
> 
- [x]  Heading 1
- [x]  Mô tả in đậm + in nghiêng
- [x]  Bảng `Thư mục | Nội dung` (≥3 dòng)
- [x]  Code block lệnh liệt kê
- [x]  Task list (≥2 việc, ≥1 đã xong)
- [x]  Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report

### Lệnh chạy

```bash
- Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
- .\auto_report.ps1

```

### Nội dung file logs/auto_report.txt

```
=== BAO CAO LOI GAMEZONE ===

2025-11-05 08:03:15 [ERROR] Mat ket noi may chu game
2025-11-05 08:09:15 [ERROR] Mat ket noi may chu game
2025-11-05 08:12:15 [ERROR] Mat ket noi may chu game
2025-11-05 08:39:15 [ERROR] Mat ket noi may chu game
2025-11-05 08:42:15 [ERROR] Mat ket noi may chu game
2025-11-05 08:51:15 [ERROR] Loi luu tien trinh choi

```

## 4.6. Đếm số dòng lỗi

### Lệnh

```bash
 - sls "ERROR" .\logs\game.log | measure-object -line
```

### Kết quả đếm

```
Lines Words Characters Property
----- ----- ---------- --------
    6
```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```bash
- echo "=== TONG HOP LOG GAMEZONE ===" > .\logs\tong_hop.txt
- sls "WARNING" .\logs\game.log >> .\logs\tong_hop.txt
- (sls "ERROR" .\logs\game.log).count >> .\logs\tong_hop.txt
```

### Nội dung file logs/tong_hop.txt

```
=== TONG HOP LOG GAMEZONE ===

logs\game.log:19:2025-11-05 08:54:15 [WARNING] May chu qua tai CPU 90%

6

```

## 4.8. Excel

> Chấm trực tiếp trên file `data/giao_dich_thang_11.xlsx`.
>