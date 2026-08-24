# PixelQuest — Lộ trình tự học làm game pixel (0 → 1)

Một trang web cá nhân để theo dõi lộ trình tự học vẽ pixel art + lập trình game,
có checklist theo giai đoạn, thanh XP tổng, và nhật ký giờ học so với lịch của bạn
(T2–T6: 2h/ngày, T7 & CN: 10h/ngày).

Toàn bộ là 1 file `index.html` tĩnh — không cần build, không cần backend,
tiến độ được lưu ngay trong trình duyệt (localStorage). Có nút xuất/nhập JSON
để backup hoặc chuyển sang máy khác.

## Chạy thử ở máy bạn

Chỉ cần mở thẳng file `index.html` bằng trình duyệt là dùng được. Muốn có local
server (khuyến khích để tránh vài giới hạn của trình duyệt với file local):

```bash
cd pixelquest
python3 -m http.server 8000
# rồi mở http://localhost:8000
```

## Deploy lên GitHub Pages

1. Tạo repo mới trên GitHub, ví dụ tên `pixelquest`.
2. Trong thư mục này, chạy:
   ```bash
   git init
   git add .
   git commit -m "PixelQuest: lộ trình tự học game pixel"
   git branch -M main
   git remote add origin https://github.com/<username>/pixelquest.git
   git push -u origin main
   ```
3. Vào repo trên GitHub → **Settings → Pages**.
4. Ở mục **Build and deployment**, chọn **Source: Deploy from a branch**,
   branch `main`, thư mục `/ (root)` → **Save**.
5. Đợi 1–2 phút, GitHub sẽ cấp cho bạn link dạng:
   `https://<username>.github.io/pixelquest/`

Mỗi lần bạn sửa `index.html` và `git push`, trang sẽ tự cập nhật sau vài phút.

## Lưu ý về dữ liệu

- Tiến độ lưu trong `localStorage` của **trình duyệt hiện tại** — nếu đổi máy/trình
  duyệt, tiến độ sẽ không tự đồng bộ. Dùng nút **"Xuất tiến độ (JSON)"** để tải file
  backup, và **"Nhập tiến độ (JSON)"** để khôi phục ở nơi khác.
- Muốn sửa nội dung lộ trình (thêm/bớt task, đổi số giờ ước tính), sửa trực tiếp
  mảng `PHASES` ở đầu phần `<script>` trong `index.html`.

## Cấu trúc lộ trình (154h ước tính)

| Giai đoạn | Nội dung | Giờ |
|---|---|---|
| 0 | Khởi động: cài công cụ, dựng repo | 6h |
| 1 | **Nền tảng pixel art** — canvas, màu, shading | 24h |
| 2 | **Thiết kế nhân vật** — sprite, animation | 30h |
| 3 | **Background & môi trường** — tileset, parallax | 24h |
| 4 | Lập trình game (Phaser 3) | 30h |
| 5 | Ghép nối thành level chơi được | 30h |
| 6 | Deploy & public | 10h |

Với 30h/tuần: tốc độ lý tưởng ≈ 5–6 tuần, thực tế nên tính buffer ≈ 8–10 tuần.
