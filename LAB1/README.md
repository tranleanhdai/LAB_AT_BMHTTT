# LAB 1 - Examining SSH & Telnet in Wireshark

## 1. Thông tin sinh viên
- Họ và tên: [Điền họ tên]
- Mã số sinh viên: [Điền MSSV]

## 2. Tên bài Lab
**Lab 1: Bắt gói tin Telnet - SSH / Examining SSH & Telnet in Wireshark**

## 3. Nội dung đã thực hiện
Trong bài Lab này, em đã thực hiện các nội dung sau:

- Thiết lập môi trường gồm Windows làm Client và Kali Linux chạy trên VMware làm Server.
- Kiểm tra kết nối giữa Client và Server bằng lệnh `ping`.
- Cài đặt và cấu hình Telnet Server trên Kali Linux.
- Tạo tài khoản thử nghiệm `uitlab`.
- Sử dụng PuTTY để kết nối Telnet đến Server qua TCP port 23.
- Sử dụng Wireshark để bắt và phân tích gói tin Telnet với bộ lọc:

  `tcp.port == 23`

- Sử dụng chức năng Follow TCP Stream để quan sát dữ liệu của phiên Telnet.
- Cấu hình và khởi động SSH Server trên Kali Linux.
- Sử dụng PuTTY để kết nối SSH đến Server qua TCP port 22.
- Sử dụng Wireshark để bắt và phân tích gói tin SSH với bộ lọc:

  `tcp.port == 22`

- So sánh mức độ bảo mật của Telnet và SSH dựa trên kết quả bắt gói thực tế.

## 4. Kết quả thực hiện
- Client Windows có thể kết nối thành công đến Kali Server.
- Telnet Server hoạt động trên TCP port 23.
- Đăng nhập Telnet thành công bằng PuTTY.
- Khi sử dụng Wireshark và Follow TCP Stream, dữ liệu của phiên Telnet có thể quan sát được ở dạng đọc được.
- SSH Server hoạt động trên TCP port 22.
- Đăng nhập SSH thành công bằng PuTTY.
- Khi phân tích lưu lượng SSH, Wireshark vẫn quan sát được các gói SSH và thông tin kết nối, nhưng nội dung phiên sau khi thiết lập mã hóa không thể đọc được như Telnet.
- Qua thực nghiệm có thể thấy SSH bảo vệ nội dung truyền tốt hơn Telnet.

## 5. Lưu ý
- Kali Server sử dụng địa chỉ IP trong mạng VMware NAT. Địa chỉ IP có thể thay đổi sau khi khởi động lại máy ảo.
- Wireshark được bắt trực tiếp trên máy Client thông qua `VMware Network Adapter VMnet8`.
- Telnet chỉ được sử dụng trong môi trường Lab nội bộ.
- Các ảnh minh chứng trong bài là ảnh chụp từ quá trình thực hành thực tế.
