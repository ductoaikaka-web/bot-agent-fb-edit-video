---
name: auto-video-edit-hook-variants
description: >-
  Use this when auto-editing short product videos: cutting raw clips, generating
  non-repeating 3-second hook variants, adding policy-safe subtitles, music and
  cart CTA, and exporting 9:16 files for TikTok, Shopee Video, Reels and Shorts
  for owner review.
---
# Edit video tự động & biến thể hook

## Tham số
- THƯ_MỤC_NGUYÊN_LIỆU (clip gốc), SẢN_PHẨM, SỐ_BIẾN_THỂ (mặc định 3), FILE_LỊCH_SỬ_HOOK, KÊNH_ĐÍCH (TikTok/Shopee Video/Reels/Shorts).

## Các bước
1. Kiểm tra clip gốc bằng `ffprobe` (độ dài, khung hình, âm thanh).
2. Đọc FILE_LỊCH_SỬ_HOOK; viết SỐ_BIẾN_THỂ hook 3 giây đầu mới, không trùng hook đã dùng (nỗi đau, kết quả, so sánh, câu hỏi...). Ghi hook mới vào lịch sử.
3. Dựng bằng `ffmpeg`: cắt đoạn mạnh nhất lên đầu, nhịp nhanh (cảnh 1–3 giây), crop/scale 1080x1920 (9:16), chèn text hook 0–3s.
4. Phụ đề: tạo từ giọng nói hoặc kịch bản, lọc từ vi phạm sàn (cam kết tuyệt đối, chữa bệnh, so sánh hạ thấp, giá sốc sai sự thật), burn-in.
5. Nhạc nền: chỉ dùng nhạc có quyền hoặc thư viện miễn phí bản quyền; giảm âm nhạc dưới giọng nói.
6. CTA cuối: "Bấm giỏ hàng vàng" (TikTok) / "giỏ hàng cam" (Shopee) / link bình luận (Reels).
7. Xuất mỗi biến thể một file MP4 H.264, đặt tên `<sản-phẩm>_hook<N>_<kênh>.mp4`, kèm chú thích hook và caption gợi ý.
8. Gửi file cho chủ shop xem và chọn.

## Quy tắc an toàn
- Chỉ xuất nháp; không tự đăng, không chạy quảng cáo khi chưa "duyệt".
- Không dùng hình/nhạc vi phạm bản quyền; không bịa công dụng sản phẩm.
- Việc cấp mã Spark Ads/quảng cáo do agent quảng cáo xử lý.
