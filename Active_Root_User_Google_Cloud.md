# Active Root User trên VPS Google
Cách dễ dàng để kích hoạt root user trên VPS của Google và một số VPS khác không mặc định cho sử dụng root user. Theo các bước dưới đây

Tạo tài khoản dùng thử
------------
 Nếu chưa có thì cần tạo một VPS của Google trên trang https://console.cloud.google.com/
 . Sử dụng thẻ VISA để có thể đăng ký chương trình dùng thử 300$/1 năm của Google.

Tạo Google VPS
------------
 - Nhấn vào Menu Google Cloud Platform góc trên bên phải.
 - Chọn Compute Engine.
 - Chọn VM instances
 - Chọn thông số và cấu hình của VPS muốn tạo.

Mở Google Console
------------
Khi đã tạo được một VPS Centos 7, tại giao diện danh sách VM instances:
- Nhấn vào chữ SSH trên cột Connect của VPS tương ứng vừa tạo.
- Cửa số command của Google sẽ loading và được mở ra. Nếu không mở ra cửa số mới có thể do popup của trình duyệt đang bị chặn.

Chuyển sang quyền root
------------

###### Command
```groovy
sudo su
```

Đổi mật khẩu root user
------------
Đổi mật khẩu root user để truy cập bằng mật khẩu.

###### Command
```groovy
sudo passwd
```
Nhập password và sau đó xác nhận lại password mới. Xuất hiện message:
```groovy
passwd: all authentication tokens updated successfully
```
có nghĩa là đã đổi thành công.

Edit quyền truy cập SSH
------------
Thay đổi config để cho phép đăng nhập VPS bằng root user + password từ các SSH client bên thứ 3.
- Mở file cài đặt config bằng lệnh
```groovy
vi /etc/ssh/sshd_config
```
- Tìm đến dòng PermitRootLogin no và gõ sửa lại thành yes
- Tìm đến dòng Authenication no và gõ sửa lại thành yes
- Sửa xong, nhấn phím ESC để thoát chức năng chỉnh sửa.
- Nhấn :x để lưu nội dung đã chỉnh sửa và thoát ra.

Khởi động lại
------------
Sau khi sửa config cần khởi động lại service để cập nhật cấu hình mới. Sử dụng lệnh:
```groovy
service sshd restart
```

Như vậy là đã cấu hình xong và có thể sử dụng SSH Client như Bitvise hay Putty để truy cập vào VPS, sử dụng root user + mật khẩu.
