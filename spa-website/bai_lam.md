# BÀI LÀM – HACKATHON 02

- **Mã đề:** 07
- **Họ tên:Trần Minh Quân**
- **Lớp:HNK26-CNTT3**
- **Link repository:https://github.com/thodantuna-lab/HN-KS26-CNTT3_Nhap-mon-CNTT_Hackathon02**
- **Hệ điều hành (Windows/macOS):Windows**

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
PS C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website> pwd
PS C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website> ls -Force
PS C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website> mv .\lich_lam_viec.txt .\docs\
PS C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website> mkdir backup
PS C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website> cp .\data\hoa_don_spa_thang_7.xlsx .\backup\
PS C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website> rm .\temp_707.tmp
PS C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website> cd .\logs\
PS C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website\logs> ls
PS C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website\logs> cd ..
PS C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website> Get-ChildItem -r -Force

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
   Directory: C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026  10:50 AM                backup
d-----        11/11/2026  10:47 AM                data
d-----        11/11/2026  10:49 AM                docs
d-----        11/11/2026  10:46 AM                evidence
d-----        11/11/2026  10:47 AM                logs
d-----        11/11/2026  10:44 AM                web
------         11/3/2026   7:07 AM             75 .env
-a----         11/3/2026   7:07 AM           2412 bai_lam.md


    Directory: C:\Users\admin\Downloads\starter-kit
    (1)\starter-kit\spa-website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM           6149 hoa_don_spa_thang_7.xlsx


    Directory: C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM           6149 hoa_don_spa_thang_7.xlsx


    Directory: C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM            149 lich_lam_viec.txt


    Directory: C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM            939 service.log


    Directory: C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website\web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026  10:44 AM                images
------         11/3/2026   7:07 AM            597 app.js
------         11/3/2026   7:07 AM            523 index.html
------         11/3/2026   7:07 AM            460 style.css


    Directory: C:\Users\admin\Downloads\starter-kit
    (1)\starter-kit\spa-website\web\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
------         11/3/2026   7:07 AM           3091 logo-lotuscare.png

```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```shell
PS C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website> gc .\logs\service.log | Select-String "status=500">.\logs\loi_500.txt

```

### 2 dòng đầu tiên trong logs/loi_500.txt

```text
2026-07-28 08:12:50 POST /api/dat-lich status=500
2026-07-28 08:19:23 POST /api/dat-lich status=500

```

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
PS C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website> (gc .\logs\service.log | Select-String "status=404").count

```

```text
4

```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
PS C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website> Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
PS C:\Users\admin\Downloads\starter-kit (1)\starter-kit\spa-website> .\tong_hop.ps1

```

### Nội dung file logs/tong_hop.txt

```text
 === BAO CAO SU CO WEBSITE === 

2026-07-28 08:16:12 GET /images/phong-spa-3.jpg status=404
2026-07-28 08:39:18 GET /uu-dai-cu status=404
2026-07-28 08:46:40 GET /tin-tuc status=404
2026-07-28 08:48:51 GET /tin-tuc status=404




Count    : 6
Average  : 
Sum      : 
Maximum  : 
Minimum  : 
Property : 




```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [x] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [x] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 | Network  | network.png | Sửa lại tên đúng của ảnh trong dòng thứ 10 file index.html  |
| 2 | Console | console.png | Sửa lại đúng tên bảng giá trong app.js |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:Tôi là sinh viên năm nhất chưa được học js nên không biết cách fix lỗi web** 
- **Expected:muốn bảng giá hiển thị ra màn hình** 
- **Actual:web báo lỗi không hiển thị bảng giá** 
- **Log:Uncaught ReferenceError: hienThiGoiDichVu is not defined** 

### Câu tìm kiếm Google

```text
site:w3schools.com "Uncaught ReferenceError"

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/hoa_don_spa_thang_7.xlsx`, không cần ghi vào đây.
