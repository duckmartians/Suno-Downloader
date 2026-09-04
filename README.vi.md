# Suno Downloader

[English](README.md) | **Tiếng Việt**

Ứng dụng desktop tải nhạc của bạn từ **suno.com** ở **chất lượng gốc** — một bài, cả playlist, một hồ sơ, hay trang khám phá. Ảnh bìa tải kèm, và mọi file đều được kiểm tra lại trước khi báo xong.

![Cửa sổ chính](docs/screenshots/01-main.png)

## Tính năng

- **Dán một link, ra hết**: bài lẻ · playlist · hồ sơ · trang khám phá — app tự quét rồi đưa danh sách cho bạn chọn
- **Chọn đúng bài muốn**: tìm trong danh sách vừa quét, chọn tất / bỏ chọn, và bài nào đã có sẵn thì gắn nhãn **Đã tải** để khỏi tải trùng
- **Thêm trước, tải sau**: link vào hàng đợi đã — **Bắt đầu / Tạm dừng / Dừng hẳn** là ba nút riêng, chưa bấm thì chưa tải gì
- **Định dạng & bitrate**: MP3 (320/256/192/128) · AAC `.m4a` (256/192/128) · **Opus `.opus`** (chỉ đổi hộp chứa, không mã hoá lại) · FLAC · WAV · **Gốc** MP4/Opus giữ nguyên từng byte
- **Tải song song**: 1–5 bài cùng lúc, mỗi dòng có ảnh bìa, phần trăm, dung lượng và thời lượng
- **Nghiệm thu từng file**: app đọc lại cấu trúc MP4 — đúng một đoạn khởi tạo, các mảnh nối liền không thủng, tổng thời lượng khớp metadata. Thiếu hay hỏng thì **báo lỗi**, không bao giờ lặng lẽ lưu nửa bài
- **Sập cũng không mất bài**: trình duyệt nền chết giữa chừng thì bài đó được chạy lại tự động (tối đa 3 lần) thay vì báo hỏng
- **Ảnh bìa** lưu cạnh file nhạc, cùng tên
- **Cookie cho bài riêng tư**: dán kiểu nào cũng nhận — `cookies.txt` chuẩn Netscape, JSON từ tiện ích trình duyệt, hay chuỗi header thô `a=1; b=2`. Bảng bên dưới cho biết cookie đó **đã đăng nhập** hay chưa
- **Kho proxy**: dán proxy kiểu nào cũng được (`host:port`, `user:pass@host:port`, `socks5://…`), lưu thành danh sách, tải bài nào xoay proxy bài đó. Nút kiểm tra lại sẽ thử từng con và đánh dấu con chết
- **Lịch sử**: mọi bài đã tải kèm dung lượng và ngày, có ô tìm — cũng chính là nguồn của nhãn *Đã tải*
- **Tự cập nhật**: kiểm tra GitHub Releases, tải và cài ngay trong app
- **6 ngôn ngữ**: English · Tiếng Việt · 简体中文 · Español · Русский · العربية (viết phải→trái)

## Ảnh màn hình

| Chọn bài sau khi quét link | Hàng đợi đang tải |
|---|---|
| ![Chọn bài](docs/screenshots/02-scan.png) | ![Hàng đợi](docs/screenshots/03-queue.png) |

| Cookie Suno (có trạng thái đăng nhập) | Kho proxy |
|---|---|
| ![Cookie](docs/screenshots/04-cookies.png) | ![Proxy](docs/screenshots/05-proxy.png) |

| Lịch sử tải | Giao diện phải→trái (العربية) |
|---|---|
| ![Lịch sử](docs/screenshots/06-history.png) | ![RTL](docs/screenshots/07-rtl-arabic.png) |

## Cài đặt

Tải bản mới nhất ở [Releases](https://github.com/duckmartians/Suno-Downloader/releases):

- **Windows**: `SunoDownloader-<phiên bản>-win-x64.exe`
- **macOS (Apple Silicon)**: `SunoDownloader-<phiên bản>-mac-arm64.dmg` — chưa ký; lần đầu mở hãy chuột phải → **Open**, hoặc chạy
  `xattr -dr com.apple.quarantine "/Applications/Suno Downloader.app"`

Cần **tài khoản G-Labs có gói Suno còn hạn**. Đăng nhập bằng Google ngay trong app; mua gói cũng ngay trong app (QR ngân hàng, PayPal hoặc USDT). Một tài khoản dùng **một máy tại một thời điểm** — đăng nhập máy khác là máy cũ bị đẩy ra.

## Hướng dẫn sử dụng

### 1. Đăng nhập

Mở app rồi đăng nhập bằng Google. Huy hiệu trên thanh tiêu đề hiện ngày hết hạn (`✓ 30/06/2027`). Bấm vào đó bất cứ lúc nào để kiểm tra hoặc gia hạn.

### 2. Dán link rồi quét

Dán một trong các dạng sau vào ô trên cùng bên trái, rồi bấm **Quét bài**:

| Link | Kết quả |
|---|---|
| `https://suno.com/song/<id>` | đúng bài đó |
| `https://suno.com/playlist/<id>` | mọi bài trong playlist |
| `https://suno.com/@<tên>` | các bài của hồ sơ đó |
| `https://suno.com/explore` | những bài trên trang khám phá |

Trang nhiều bài mất khoảng 30 giây — app tự cuộn trang để nạp hết. Bấm **Huỷ** nếu muốn dừng.

### 3. Chọn bài

![Chọn bài](docs/screenshots/02-scan.png)

Danh sách mở ra là đã tick sẵn tất cả. Gõ vào ô tìm để lọc, dùng **Chọn tất / Bỏ chọn**, và để ý nhãn xanh **Đã tải** — đó là những bài đã có trong lịch sử. Bấm **Tải N bài** để đẩy vào hàng đợi.

### 4. Xem lại cài đặt

Mở thẻ **Cài đặt** bên trái trước khi tải:

- **Thư mục lưu** — mặc định `Music/Suno Downloader`.
- **Số luồng song song** — 1 đến 5. Mỗi luồng chạy một cửa sổ trình duyệt ẩn riêng nên RAM tăng theo số luồng. 1–2 là đủ cho đa số máy.
- **Định dạng** và **Bitrate** — xem bảng bên dưới. Ô bitrate tự mờ với định dạng không có bitrate.
- **Lưu ảnh bìa cạnh file nhạc** — ghi `Nghệ sĩ — Tên bài.jpg` ngay cạnh file nhạc.

### 5. Bắt đầu tải

Chưa bấm **Bắt đầu tải** thì không có gì được tải. Đang chạy thì có **Tạm dừng** (không kéo bài mới, bài đang tải vẫn xong) và **Dừng hẳn** (huỷ tất cả). Mỗi dòng hiện thanh tiến độ, phần trăm, dung lượng và thời lượng; **Xoá bài đã xong** dọn các dòng đã hoàn tất.

![Hàng đợi](docs/screenshots/03-queue.png)

Bài nào xong thì bấm biểu tượng thư mục để mở ngay trong Finder / Explorer.

### 6. Bài riêng tư cần cookie

Bài không công khai của chính bạn cần phiên đăng nhập Suno. Mở **Cookie Suno**, dán vào rồi bấm **Nạp cookie đã dán**. Nhận cả ba kiểu:

- `cookies.txt` chuẩn Netscape (xuất từ tiện ích trình duyệt)
- JSON từ tiện ích kiểu Cookie-Editor
- Chuỗi header thô: `__session=abc; other=1`

Dòng bên dưới cho biết tên miền, đã lưu bao nhiêu cookie, và nhãn xanh **đã đăng nhập** khi có cookie phiên thật. Không có cookie phiên thì bài riêng tư sẽ tải lỗi.

### 7. Proxy (tuỳ chọn)

Mở **Proxy**, dán mỗi dòng một proxy rồi bấm **Thêm N proxy**. Các kiểu được nhận:

```
203.0.113.24:8080
user:pass@198.51.100.7:3128
socks5://user:pass@192.0.2.55:1080
```

Gạt công tắc để bật — mỗi bài dùng một proxy khác nhau, xoay vòng trong danh sách. **Kiểm tra lại** thử toàn bộ với `suno.com` (hoặc URL bạn tự đặt) và đánh dấu con chết để bấm một nút là xoá hết.

### 8. Lịch sử

Nút **Lịch sử** ở góc trên phải liệt kê mọi bài đã tải — ảnh bìa, nghệ sĩ, tên bài, dung lượng, ngày — kèm ô tìm. Đây cũng là nguồn của nhãn *Đã tải*, nên quét lại cùng một playlist sẽ không mất công tải trùng. **Xoá lịch sử** chỉ dọn danh sách, file nhạc vẫn còn nguyên.

## Định dạng

| Chọn | File | Có mã hoá lại? | Bitrate |
|---|---|---|---|
| **Gốc** | `.mp4` | không — đúng byte Suno gửi | — |
| Opus | `.opus` | không — chỉ đổi hộp chứa | — |
| **MP3** *(mặc định)* | `.mp3` | có | 320 / 256 / 192 / 128 |
| AAC | `.m4a` | có | 256 / 192 / 128 |
| FLAC | `.flac` | có (hộp không mất chất, nhưng nguồn đã nén) | — |
| WAV | `.wav` | có (không nén) | — |

Suno gửi audio Opus đặt trong hộp MP4. **Gốc** giữ nguyên từng byte; mọi lựa chọn khác đều là chuyển mã — tương thích rộng hơn, nhưng chất lượng không thể hơn bản gốc.

## Dữ liệu nằm ở đâu

| Thứ gì | macOS | Windows |
|---|---|---|
| Nhạc tải về | `~/Music/Suno Downloader` | `%USERPROFILE%\Music\Suno Downloader` |
| Cài đặt, lịch sử, cookie | `~/Library/Application Support/Suno Downloader` | `%APPDATA%\Suno Downloader` |

Mọi thứ bạn chỉnh — thư mục, số luồng, định dạng, bitrate, ảnh bìa, ngôn ngữ, danh sách proxy — đều được lưu và khôi phục ở lần mở sau.

## Gặp lỗi thì làm gì

**"Mới tải được 40% bài — hãy tải lại."**
Mạng rớt giữa chừng. File bị từ chối có chủ đích chứ không lưu nửa vời. Bấm **Tải lại** ở dòng đó.

**Một bài báo "không tải được dữ liệu âm thanh"**
Bài đó riêng tư mà app chưa có phiên đăng nhập — thêm cookie ở bước 6.

**Quét không ra bài nào**
Kiểm tra link có đúng là địa chỉ `suno.com` không, và mở bằng trình duyệt xem trang đó có bài thật không.

**Mọi thứ bị khoá, cứ hiện màn mua gói**
Gói Suno hết hạn, hoặc tài khoản vừa đăng nhập ở máy khác. Xem huy hiệu ngày trên thanh tiêu đề.

**macOS báo app bị hỏng / không mở được**
App chưa ký với Apple. Lần đầu hãy chuột phải → **Open**, hoặc chạy
`xattr -dr com.apple.quarantine "/Applications/Suno Downloader.app"`.

## Phát triển

```bash
npm run install:all
node scripts/build-kv.mjs      # sinh kv/out/
npm run dev                    # Vite + Electron
npm test
```

Build Windows: `setup.bat` rồi `build-exe.bat` — xem [BUILD-WIN.md](BUILD-WIN.md).
Build macOS: `./build_mac_arm64.sh`.

Thông số vận hành (selector, thời gian chờ, script chèn trang) **không nằm trong app** — worker license giao ra sau khi verify chữ ký RSA. Client không có giá trị dự phòng nào: không có cấu hình thì không tải được.
