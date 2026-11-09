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

## Đưa file lên bằng trình duyệt (không cần script)

File trên 100 MB (như VIETMAP LIVE) không `git push` được, phải đưa vào **Releases**:

1. Vào https://github.com/letruclam/car_appstore/releases/new
2. **Tag**: đúng như trong `url` của app, ví dụ `vn.vietmap.live-3.4.4`
3. Kéo thả file vào, **đổi tên file** đúng như cuối `url`, ví dụ `vn.vietmap.live-3.4.4.apks`
4. Bấm **Publish release**

File phải trùng `sha256` trong `store_catalog.json`, nếu không xe sẽ từ chối và chuyển sang tìm trên USB.
Kiểm tra trên Mac: `shasum -a 256 <file>`.
