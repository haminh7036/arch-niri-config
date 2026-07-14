# Cấu hình Niri

## Cấu trúc thư mục

* config.kdl: File cấu hình chính, liên kết các module con.
* noctalia.kdl: Cấu hình màu sắc giao diện được tự động cập nhật bởi Noctalia.
* config.d/:
  * config.d/startup.kdl: Ứng dụng tự khởi động và biến môi trường.
  * config.d/input.kdl: Thiết lập bàn phím, chuột, touchpad và con trỏ.
  * config.d/layout.kdl: Thiết lập khoảng cách (gaps), kích thước cột và hiệu ứng chuyển động.
  * config.d/rules.kdl: Luật hiển thị cửa sổ và tùy chọn gỡ lỗi.
  * config.d/binds.kdl: Phím tắt hệ thống và phím tắt của Noctalia.

## Hướng dẫn chỉnh sửa nhanh

* Thay đổi phím tắt: Sửa file config.d/binds.kdl.
* Thêm ứng dụng khởi động: Thêm dòng `spawn-at-startup "tên-app"` vào file config.d/startup.kdl.
* Thêm luật cửa sổ: Khai báo khối `window-rule` mới trong file config.d/rules.kdl.

## Kiểm tra lỗi cấu hình
Chạy lệnh sau trước khi áp dụng cấu hình mới:
```bash
niri validate
```
