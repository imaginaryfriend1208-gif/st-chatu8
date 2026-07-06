# SillyTavern Tạo ảnh từ văn bản (st-chatu8)

**Tác giả:** 从前跟你一样
**Phiên bản:** 1.0.0
**Bản dịch tiếng Việt** bởi imaginaryfriend1208-gif

Đây là phần mở rộng bên thứ ba dành cho [SillyTavern](https://github.com/SillyTavern/SillyTavern), tích hợp liền mạch tính năng tạo ảnh từ văn bản mạnh mẽ vào trải nghiệm trò chuyện của bạn. Chỉ với các dấu đánh dấu đơn giản, bạn có thể gọi Stable Diffusion, NovelAI hoặc ComfyUI ngay trong hội thoại, biến mô tả chữ thành hình ảnh sống động.

## ✨ Tính năng

- **Hỗ trợ nhiều backend**:
    - **Stable Diffusion**: Kết nối qua A1111/Forge WebUI API.
    - **NovelAI**: Hỗ trợ API NovelAI chính thức và bên thứ ba.
    - **ComfyUI**: Tạo ảnh tùy chỉnh cao bằng cách nhập workflow.
- **Cách kích hoạt đơn giản**: Trong trò chuyện, dùng dấu bắt đầu và kết thúc tùy chỉnh (như `[prompt]`) để bọc prompt, ảnh sẽ tự sinh.
- **Cấu hình linh hoạt**:
    - **Cài đặt toàn cục**: Dễ dàng chuyển giữa các backend và cấu hình dấu đánh dấu toàn cục.
    - **Tham số chi tiết**: Cho từng backend (SD, NovelAI, ComfyUI) thiết lập riêng model, sampler, kích thước, số bước, CFG v.v.
    - **Tính năng nâng cao**: Hỗ trợ sửa HD (Hires. fix), ADetailer của SD; tham chiếu không khí (Vibe Transfer), tham chiếu nhân vật (Character Reference) của NovelAI; LORA và workflow tùy chỉnh của ComfyUI.
- **Quản lý prompt**:
    - **Prompt cố định**: Thiết lập prompt cố định phía trước và negative cho từng backend.
    - **Preset prompt**: Lưu và tải nhiều bộ cấu hình prompt, tiện chuyển đổi phong cách.
    - **Thay thế động**: Thiết lập quy tắc, tự thay thế từ cụ thể trong trò chuyện bằng prompt phù hợp hơn để vẽ.
- **Tối ưu trải nghiệm**:
    - **Bộ nhớ ảnh**: Hệ thống cache ảnh tích hợp, có thể xem trước, quản lý và tải ảnh đã sinh, đồng thời đặt thời hạn cache.
    - **Thao tác tiện lợi**: Hỗ trợ nhấn giữ ảnh để sửa prompt, nhấp đúp ảnh để tạo lại.
    - **Tích hợp giao diện**: Thêm lối vào cài đặt ở giao diện chính, cung cấp nút nổi tùy chỉnh.
    - **Tự cập nhật**: Tự kiểm tra và nhắc cập nhật plugin khi khởi động.

## 🚀 Cài đặt

1.  Trong menu extension của SillyTavern, cài plugin từ URL sau:
    ```
    https://github.com/imaginaryfriend1208-gif/st-chatu8
    ```
2.  Khởi động lại SillyTavern.
3.  Bật "st-chatu8" trong menu extension.

## 📖 Cách dùng

Quy trình cốt lõi rất đơn giản:

### 1. Mở bảng cài đặt

Nhấn nút **"Mở cài đặt tạo ảnh"** ở thanh bên, hoặc vào bảng cài đặt plugin qua nút nổi.

### 2. Cấu hình backend

-   Trong tab **"Cài đặt chính"**, chọn **Chế độ** (SD / NovelAI / ComfyUI) bạn muốn dùng.
-   Chuyển sang tab backend tương ứng (VD: "SD"), nhập địa chỉ API (như `http://127.0.0.1:7860`), nhấn **"Kết nối & làm mới dữ liệu"** để đảm bảo plugin giao tiếp bình thường.
-   Theo nhu cầu, cấu hình model, sampler, kích thước mặc định v.v.

### 3. Tạo ảnh trong trò chuyện

Trong bất kỳ tin nhắn nào, dùng **Dấu bắt đầu** và **Dấu kết thúc** đã định nghĩa trong **"Cài đặt chính" -> "Đánh dấu"** (mặc định là `[` và `]`) để bọc prompt vẽ ảnh.

**Ví dụ:**

```
[1girl, solo, beautiful detailed eyes, looking at viewer]
```

Plugin sẽ tự phát hiện đoạn này, gọi backend bạn chọn và hiển thị ảnh sinh ra trong giao diện trò chuyện.

## ⚙️ Tùy chọn cài đặt

Plugin cung cấp nhiều tùy chọn,分布在 các tab:

### Cài đặt chính

-   **Bật plugin**: Công tắc tổng của plugin.
-   **Chế độ**: Chọn backend tạo ảnh mặc định (SD, NovelAI, ComfyUI).
-   **Đánh dấu**: Tùy chỉnh ký hiệu bắt đầu và kết thúc để kích hoạt tạo ảnh.
-   **Quản lý cache**: Thiết lập thời hạn cache ảnh, hoặc xóa toàn bộ cache bằng một cú nhấp.

### Tab SD / NovelAI / ComfyUI

Mỗi backend có trang cấu hình độc lập, thường gồm:

-   **Địa chỉ API**: URL kết nối dịch vụ backend.
-   **Prompt cố định**: Thiết lập prompt cố định phía trước và negative toàn cục, hỗ trợ quản lý preset.
-   **Thay thế prompt**: Định nghĩa quy tắc, thay văn bản cụ thể bằng nội dung khác (VD: `ngựa` -> `horse`).
-   **Preset chất lượng**: Bật/tắt nhanh prompt chất lượng cao/thấp thông dụng.
-   **Tham số tạo**:
    -   Model, VAE, Sampler, Scheduler
    -   Chiều rộng (Width) và chiều cao (Height) ảnh
    -   Số bước lấy mẫu (Steps), CFG scale
    -   Seed
-   **Tùy chọn nâng cao**:
    -   **SD**: Sửa HD, sửa khuôn mặt (Restore Faces), ADetailer.
    -   **NovelAI**: SMEA, Vibe Transfer, Character Reference v.v.
    -   **ComfyUI**: Quản lý workflow, cho phép dán API JSON xuất từ ComfyUI.

### Tab khác

-   **Giao diện**: Tùy chỉnh màu sắc giao diện bảng cài đặt.
-   **Nút nổi**: Cấu hình bật/tắt, kiểu dáng và kích thước nút nổi.
-   **Bộ nhớ ảnh**: Xem và quản lý toàn bộ ảnh đã sinh.
-   **Giới thiệu**: Xem thông tin plugin, kiểm tra cập nhật và lấy trợ giúp.

---
Chúc bạn sáng tạo tự do trong SillyTavern!

## Trợ giúp & Hỗ trợ

-   [Tài liệu Feishu](https://gxcgf4l6b2y.feishu.cn/docx/XDo7dLpvhov6AexuLu3c8mpynSC?from=from_copylink)
-   [Ủng hộ tác giả](https://afdian.com/a/cqgnyy)

## Giấy phép

-   [Aladdin](LICENSE)
