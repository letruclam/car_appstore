# car_appstore

Danh sách app cho **Kho ứng dụng** của Geely Connect.

- `store_catalog.json`: danh sách app. Geely Connect đọc file này mỗi lần mở kho.
- File cài (`.apk` / `.apks`) nằm ở mục **Releases**, không nằm trong code của repo (GitHub chặn file trên 100 MB).

## Đăng bản mới

Trên máy Mac, trong repo `geely_connect`:

```sh
./tools/publish-app.sh ~/Downloads/vietmap.apks
```

Script tự đọc tên gói và phiên bản từ file, tính SHA-256, đưa file lên Releases rồi cập nhật `store_catalog.json`.
Thêm app mới: `./tools/publish-app.sh file.apk --name "Tên app" --desc "Mô tả ngắn"`.
