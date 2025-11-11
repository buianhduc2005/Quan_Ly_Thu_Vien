# 📚 HỆ THỐNG QUẢN LÝ THƯ VIỆN ĐẠI HỌC (THUVIEN1)

Hệ thống Quản lý Thư viện được phát triển nhằm hỗ trợ công tác quản lý, theo dõi và đánh giá hoạt động của thư viện trong môi trường giáo dục đại học. Thay vì quản lý thủ công bằng giấy tờ hay các tệp Excel rời rạc, hệ thống mang đến một giải pháp tập trung, hiện đại và dễ sử dụng.

---

## 1. GIỚI THIỆU

<img width="2000" height="400" alt="image" src="https://github.com/user-attachments/assets/06473026-8df6-4baa-b305-8ff45b1c748f" />




## 2. CÁC CÔNG NGHỆ ĐƯỢC SỬ DỤNG

### Hệ điều hành

* Windows
* Ubuntu

### Công nghệ chính

* PHP
* HTML5
* CSS
* SCSS
* JavaScript
* Bootstrap

### Web Server & Database

* Apache
* MySQL
* XAMPP

### Database Management Tools

* MySQL Workbench
* phpMyAdmin

[CHÈN HÌNH ẢNH MINH HỌA CÁC CÔNG NGHỆ (TƯƠNG TỰ IMAGE 1, PHẦN CUỐI) TẠI ĐÂY]

---

## 3. HÌNH ẢNH CÁC CHỨC NĂNG

Đây là các giao diện chính của hệ thống, minh họa các tính năng cốt lõi.

### Trang Đăng nhập

<img width="1919" height="964" alt="image" src="https://github.com/user-attachments/assets/d4c26cd5-7d2a-41a9-9450-cc370cfeeace" />


### Trang Dashboard Admin

<img width="1914" height="910" alt="image" src="https://github.com/user-attachments/assets/2db1ab0a-e46b-43c7-9811-b00c7b4494f6" />


### Trang Dashboard Cán bộ/Người dùng

<img width="1919" height="844" alt="image" src="https://github.com/user-attachments/assets/b8e82f7c-882c-4d5d-a655-da0468ba39b4" />


---

## 4. CÀI ĐẶT VÀ TRIỂN KHAI HỆ THỐNG

### 4.1. Cài đặt công cụ, môi trường và các thư viện cần thiết

* Tải và cài đặt XAMPP: [https://www.apachefriends.org/download.html](https://www.apachefriends.org/download.html) (Khuyên nghị bản XAMPP với PHP 8.x)
* Cài đặt Visual Studio Code và các extension:
    * PHP Intelephense
    * MySQL
    * Prettier - Code Formatter

### 4.2. Tải project

Clone project về thư mục `htdocs` của XAMPP (ví dụ ổ C:):

```bash
cd C:\xampp\htdocs
git clone (https://github.com/buianhduc2005/Quan_Ly_Thu_Vien.git) thuvien1
```

Truy cập project qua đường dẫn: `http://localhost/thuvien1/index.php

### 4.3. Setup Database

Mở XAMPP Control Panel, Start Apache và MySQL.
Truy cập MySQL Workbench hoặc phpMyAdmin để tạo Database:

```sql
CREATE DATABASE IF NOT EXISTS ql_thuvien
CHARACTER SET utf8mb4
COLLATE utf8mb4_unicode_ci;
```





### 4.4. Setup tham số kết nối

Mở file `config/db.php` (hoặc tương tự) trong project, chỉnh thông tin Database:

```php
<?php
// config/db.php
function getDbConnection() {
    $servername = "localhost";
    $username = "root";
    $password = "";
    $dbname = "ql_thuvien"; // Tên database của bạn
    $port = 3306; // Mặc định của MySQL

    $conn = mysqli_connect($servername, $username, $password, $dbname, $port);
    if (!$conn) {
        die("Kết nối database thất bại: " . mysqli_connect_error());
    }
    mysqli_set_charset($conn, "utf8");
    return $conn;
}
?>
```



### 4.5. Chạy hệ thống

Mở XAMPP Control Panel – Start Apache và MySQL.
Truy cập hệ thống: `http://localhost/thuvien1/index.php

### 4.6. Đăng nhập lần đầu

Hệ thống có thể cấp tài khoản admin.
Sau khi đăng nhập Admin có thể:
* Tạo thông tin tổ chức (Khoa, Lớp, ... tùy thuộc vào cấu trúc thư viện)
* Thêm sách và quản lý danh mục sách
* Quản lý thông tin độc giả và phân quyền theo cấp

[CHÈN HÌNH ẢNH MINH HỌA QUY TRÌNH CHẠY HỆ THỐNG / ĐĂNG NHẬP LẦN ĐẦU (TƯƠNG TỰ IMAGE 4, PHẦN CUỐI) TẠI ĐÂY]

---

## 5. KẾT LUẬN

### 5.1. Ưu điểm Đạt được

Hệ thống quản lý thư viện đã triển khai đầy đủ các thao tác **CRUD** cho Sách, Độc giả, và Giao dịch Mượn/Trả. Giao diện thân thiện, dễ sử dụng và có phân quyền rõ ràng giữa Admin và người dùng. Mã nguồn được tổ chức module hóa và áp dụng Prepared Statements để tăng cường bảo mật.

### 5.2. Hạn chế và Định hướng Phát triển

Hệ thống vẫn còn một số điểm cần cải tiến trong tương lai:
* **Báo cáo chuyên sâu:** Cần phát triển thêm các báo cáo thống kê phức tạp với biểu đồ trực quan (ví dụ: thống kê sách mượn nhiều nhất, xu hướng mượn).
* **Tối ưu Mobile:** Giao diện cần được tối ưu hóa tốt hơn cho các thiết bị di động.
* **Tính năng Mở rộng:** Xây dựng hệ thống **Thông báo Tự động (Email/SMS)** để nhắc nhở độc giả về thời hạn trả sách hoặc khi có sách mới.

```
