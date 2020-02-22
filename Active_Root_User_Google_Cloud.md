# Active Root User trên VPS Google
Cách dễ dàng để kích hoạt root user trên VPS của Google và một số VPS của hãng khác không mặc định cho sử dụng root user

Bước 1
------------
 Nếu chưa có thì cần tạo một VPS của Google trên trang https://console.cloud.google.com/
 Sử dụng thẻ VISA để có thể đăng ký chương trình dùng thử 300$/1 năm của Google.

Bước 2
------------
 Tạo một VPS của Google:
 - Nhấn vào Menu Google Cloud Platform góc trên bên phải.
 - Chọn Compute Engine.
 - Chọn VM instances
 - Chọn thông số và cấu hình của VPS muốn tạo.

Bước 3
------------
Khi đã tạo được một VPS Centos 7, tại giao diện danh sách VM instances:
- Nhấn vào chữ SSH trên cột Connect của VPS tương ứng vừa tạo.
- Cửa số command của Google sẽ loading và được mở ra. Nếu không mở ra cửa số mới có thể do popup của trình duyệt đang bị chặn.

Bước 4
------------
Chuyển sang quyền root, gọi command

###### Project Gradle
```groovy
sudo su
```

###### Module Gradle
```groovy
dependencies {
	implementation 'com.github.phihung1992:SimpleLoading:1.2'
}
```

Usage
--------
Impliment 2 methods: showLoading() and dismissLoading() to use easily.

```groovy
private SimpleLoadingDialog progressDialog;

private void showLoading() {
    if (progressDialog == null) {
       progressDialog = SimpleLoadingDialog.newInstance()
            .setMessage("Loading data. \nPlease wait for a few seconds or check your internet quality ...", "#327773")
            .setLoadingColor("#327773")
            .setCanceled(true, true);
       }

    if (progressDialog.isAdded()) {
       return;
    }
    progressDialog.show(this);
}

private void dismissLoading() {
    if (progressDialog != null) progressDialog.dismiss();
}
```

