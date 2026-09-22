# LAB 3 - Phân tích mã độc và các hình thức tấn công hệ thống thông tin

## 1. Thông tin sinh viên
- Họ và tên: Trần Lê Anh Đại
- Mã số sinh viên: 1150080007

## 2. Tên bài Lab
**Lab 3: Phân tích mã độc và các hình thức tấn công hệ thống thông tin**

## 3. Nội dung đã thực hiện
Trong bài Lab này, em đã thực hiện các nội dung sau:

- Thiết lập môi trường thực hành trên Windows Server 2025 chạy bằng VMware Workstation.
- Tạo thư mục `C:\LAB3` và thư mục `Evidence` để lưu các bằng chứng trong quá trình thực hành.
- Thu thập thông tin baseline của hệ thống trước khi tiến hành các tình huống kiểm thử.
- Kiểm tra trạng thái Windows Defender và Windows Firewall.
- Thực hiện kiểm thử khả năng phát hiện mã độc bằng chuỗi kiểm thử EICAR trong môi trường Lab.
- Kiểm tra Protection History của Windows Security sau khi thực hiện kiểm thử.
- Tạo tài khoản cục bộ `lab3user` phục vụ cho việc kiểm thử xác thực.
- Cấu hình Audit Logon để ghi nhận cả các sự kiện đăng nhập thành công và thất bại.
- Thực hiện đăng nhập sai có kiểm soát đối với tài khoản `lab3user`.
- Sử dụng Windows Security Log và PowerShell để kiểm tra Event ID 4625.
- Quan sát và xác định tài khoản liên quan đến sự kiện đăng nhập thất bại.
- Chuẩn bị Wireshark để thực hiện phân tích lưu lượng mạng HTTP/HTTPS trên giao diện loopback.

## 4. Kết quả thực hiện

### 4.1. Thu thập baseline hệ thống
Các thông tin cơ bản của hệ thống như hệ điều hành, tiến trình đang chạy, cấu hình mạng, trạng thái Windows Defender và Windows Firewall đã được thu thập và lưu lại trong thư mục:

`C:\LAB3\Evidence`

Các dữ liệu baseline này có thể được sử dụng để so sánh trạng thái hệ thống trước và sau quá trình kiểm thử.
<img width="975" height="702" alt="image" src="https://github.com/user-attachments/assets/d205c77e-5f9a-4f48-a82a-ca0b1e535165" />

### 4.2. Kiểm thử phát hiện mã độc bằng EICAR
Chuỗi kiểm thử EICAR được sử dụng để kiểm tra khả năng phát hiện của Windows Defender trong môi trường Lab.

Sau khi thực hiện kiểm thử, Windows Security đã phát hiện mối đe dọa và thực hiện hành động bảo vệ. Kết quả có thể được quan sát trong mục Protection History.

<!-- DÁN ẢNH WINDOWS SECURITY / THREAT QUARANTINED Ở ĐÂY -->


Qua kết quả trên có thể thấy Windows Defender đang hoạt động và có khả năng phát hiện mẫu kiểm thử EICAR.


### 4.3. Kiểm thử và phân tích sự kiện đăng nhập thất bại
Tài khoản cục bộ `lab3user` được tạo nhằm phục vụ quá trình kiểm thử xác thực.

Audit Logon được cấu hình ở trạng thái:

`Success and Failure`

nhằm cho phép Windows ghi nhận các sự kiện xác thực trong Security Log.

<img width="975" height="770" alt="image" src="https://github.com/user-attachments/assets/1571bce7-6591-4f19-b876-9e63e6ef8856" />
<img width="975" height="687" alt="image" src="https://github.com/user-attachments/assets/dc470955-b990-485b-bdfc-bc9866d37de1" />

