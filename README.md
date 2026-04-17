# Hướng dẫn quản lý tài liệu Hoa Sen Home

## Cấu trúc file

- `index.html` - Giao diện web chính
- `documents.json` - Danh sách tài liệu (dễ dàng thêm/xóa/sửa)
- `logo.jpg` - Logo công ty

## Cách thêm tài liệu mới

### Cách 1: Thêm vào file `documents.json` (Khuyến nghị)

1. Mở file `documents.json`
2. Thêm object mới vào mảng `documents`:

```json
{
  "name": "Ten_tai_lieu.pdf",
  "displayName": "Tên hiển thị ngắn gọn",
  "category": "chinh-sach", // chinh-sach, quy-dinh, tai-lieu, video, bang-gia, linh-hoat
  "type": "pdf", // pdf, word, video
  "size": "2.5 MB",
  "driveUrl": "https://drive.google.com/file/d/FILE_ID/view",
  "startDate": "2026-01-01",
  "endDate": "",
  "note": "Ghi chú tùy chọn"
}
```

3. Upload file lên Google Drive
4. Copy link và paste vào `driveUrl`
5. Deploy lại lên Vercel/Netlify

### Cách 2: Dùng giao diện Admin

1. Đăng nhập với admin/admin123
2. Click "Thêm từ Drive"
3. Điền thông tin và submit

## Các danh mục

- `chinh-sach` - Chính sách (xanh lá)
- `quy-dinh` - Quy định (đỏ) 
- `tai-lieu` - Tài liệu đào tạo (tím)
- `video` - Video (hồng)
- `bang-gia` - Bảng giá (vàng)
- `linh-hoat` - Linh hoạt (xanh dương)

## Hướng dẫn upload lên Google Drive

1. Vào Google Drive
2. Upload file (PDF, Word, Video)
3. Click chuột phải vào file → Share
4. Chọn "Anyone with the link" → "Viewer"
5. Click "Copy link"
6. Paste vào `driveUrl` trong JSON

## Deploy lên Vercel/Netlify

### Vercel:
1. Push code lên GitHub
2. Vào vercel.com → Import Git Repository
3. Framework Preset: Other
4. Deploy

### Netlify:
1. Kéo thả folder vào netlify.com
2. Xong!

## Lưu ý quan trọng

- **Bắt buộc**: File Drive phải để chế độ public ("Anyone with link can view")
- **Tên file**: Không chứa ký tự đặc biệt
- **Link Drive**: Phải là link chia sẻ, không phải link edit
- **Backup**: Export CSV từ admin panel để backup data

## Xóa tài liệu

Chỉ cần xóa object tương ứng trong `documents.json` và deploy lại.

## Sửa thông tin

Sửa trực tiếp trong `documents.json`:
- `displayName`: Tên hiển thị
- `driveUrl`: Link Drive mới
- `startDate/endDate`: Ngày áp dụng
- `note`: Ghi chú

Sau khi sửa xong, deploy lại để cập nhật.
