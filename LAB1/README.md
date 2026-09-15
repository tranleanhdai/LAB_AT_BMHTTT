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
  <img width="1227" height="729" alt="{502046DD-F035-4FC8-8958-00F8602E006D}" src="https://github.com/user-attachments/assets/89649040-6869-419c-96ba-9f3485c3903a" />
- Đăng nhập Telnet thành công bằng PuTTY.
  <img width="649" height="399" alt="{5692AFF6-0B13-4F31-96FA-D3B26091B3B7}" src="https://github.com/user-attachments/assets/1ac25799-68ae-4a8a-86f2-1b20641f424c" />

- Khi sử dụng Wireshark và Follow TCP Stream, dữ liệu của phiên Telnet có thể quan sát được ở dạng đọc được.
  <img width="810" height="721" alt="{4B3E1100-5C43-4E79-B460-8448F6E51DE0}" src="https://github.com/user-attachments/assets/4ac84957-f666-4cd9-be63-b505a42e1b6b" />

- SSH Server hoạt động trên TCP port 22.
  <img width="1259" height="721" alt="{37E6B57E-321F-4302-A7CF-D45BAD219240}" src="https://github.com/user-attachments/assets/0fb278a4-4b0f-4258-b334-43bb8dff0512" />

- Đăng nhập SSH thành công bằng PuTTY.
  <img width="1100" height="685" alt="{909CADA4-5528-4DDC-A4E6-17CED9663C0C}" src="https://github.com/user-attachments/assets/c9f31e2b-cab4-4f4f-b8fd-2f8b9cc4e5d9" />

- Khi phân tích lưu lượng SSH, Wireshark vẫn quan sát được các gói SSH và thông tin kết nối, nhưng nội dung phiên sau khi thiết lập mã hóa không thể đọc được như Telnet.
  <img width="737" height="740" alt="{49EA876F-1754-4318-BDD2-DE293218590D}" src="https://github.com/user-attachments/assets/988bbd90-2877-4671-97f2-e59faa933b17" />

- Qua thực nghiệm có thể thấy SSH bảo vệ nội dung truyền tốt hơn Telnet.

## 5. Lưu ý
- Kali Server sử dụng địa chỉ IP trong mạng VMware NAT. Địa chỉ IP có thể thay đổi sau khi khởi động lại máy ảo.
- Wireshark được bắt trực tiếp trên máy Client thông qua `VMware Network Adapter VMnet8`.
- Telnet chỉ được sử dụng trong môi trường Lab nội bộ.
- Các ảnh minh chứng trong bài là ảnh chụp từ quá trình thực hành thực tế.
