<h1 align="center">Suno Downloader</h1>

<p align="center"><b>App desktop tải nhạc từ suno.com ở chất lượng gốc - một bài, cả playlist, một hồ sơ hay trang khám phá, kèm ảnh bìa, và mọi file đều được kiểm tra trước khi báo xong.</b></p>

<p align="center">
  <a href="README.md">English</a> ·
  <b>Tiếng Việt</b>
</p>

<p align="center">
  <a href="https://github.com/duckmartians/Suno-Downloader/releases/latest"><img alt="Tải về cho Windows" src="https://img.shields.io/badge/T%E1%BA%A3i%20v%E1%BB%81-Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white"></a>&nbsp;
  <a href="https://github.com/duckmartians/Suno-Downloader/releases/latest"><img alt="Tải về cho macOS (Apple Silicon)" src="https://img.shields.io/badge/T%E1%BA%A3i%20v%E1%BB%81-macOS%20Apple%20Silicon-000000?style=for-the-badge&logo=apple&logoColor=white"></a>&nbsp;
  <a href="https://github.com/duckmartians/Suno-Downloader/releases/latest"><img alt="Tải về cho macOS (Intel)" src="https://img.shields.io/badge/T%E1%BA%A3i%20v%E1%BB%81-macOS%20Intel-555555?style=for-the-badge&logo=apple&logoColor=white"></a>
</p>

---

## Cài đặt

### Bước 1 - Chọn đúng bản cho máy của bạn

Mở bản phát hành mới nhất ở **[Releases](https://github.com/duckmartians/Suno-Downloader/releases/latest)** rồi tải tệp đúng với máy (`<phiên bản>` là số phiên bản, ví dụ `1.0.1`):

| Máy của bạn | Tải tệp | Ghi chú |
|---|---|---|
| 🪟 **Windows (64-bit)** | [`SunoDownloader-<phiên bản>-win-x64.exe`](https://github.com/duckmartians/Suno-Downloader/releases/latest) | Bộ cài |
| 🍎 **Mac chip Apple (M1/M2/M3/M4)** | [`SunoDownloader-<phiên bản>-mac-arm64.dmg`](https://github.com/duckmartians/Suno-Downloader/releases/latest) | Mac từ khoảng cuối 2020 về sau |
| 🍎 **Mac chip Intel** | [`SunoDownloader-<phiên bản>-mac-intel.dmg`](https://github.com/duckmartians/Suno-Downloader/releases/latest) | Mac đời cũ (trước 2020) |

**Không chắc Mac của bạn chip gì?** Bấm biểu tượng  ở góc trên bên trái → **About This Mac**:
- Có dòng **Chip** ghi "Apple M1 / M2 / M3…" → tải bản **arm64**.
- Có dòng **Processor** ghi "Intel…" → tải bản **intel**.

> Tải nhầm bản **Intel** cho máy Apple thì vẫn chạy được nhưng chậm hơn; còn tải nhầm bản **arm64** cho máy Intel sẽ **không mở được**. Nên chọn đúng.

Không cần cài thêm gì: FFmpeg và trình duyệt nền đã đi kèm trong app - không cần Chrome.

### Bước 2 - Cài đặt

<details open>
<summary><b>🪟 Trên Windows</b></summary>

1. Mở tệp **`SunoDownloader-<phiên bản>-win-x64.exe`** vừa tải.
2. Nếu hiện bảng **"Windows protected your PC"** (SmartScreen): bấm **More info** → **Run anyway**. *(App chưa ký chứng chỉ của Microsoft nên bị cảnh báo - không phải virus.)*
3. Chờ trình cài đặt chạy xong, rồi mở **Suno Downloader** từ **Start Menu**.

</details>

<details open>
<summary><b>🍎 Trên macOS</b></summary>

1. Mở tệp **`.dmg`** vừa tải, rồi **kéo Suno Downloader vào thư mục Applications**.
2. Vào **Applications**, **chuột phải** (hoặc Control-click) vào **Suno Downloader** → **Open** → bấm **Open** lần nữa trong hộp thoại. *(App chỉ ký ad-hoc, không có Apple Developer ID, nên **lần đầu** phải mở theo cách này; từ lần sau mở bình thường.)*
3. Nếu macOS báo app **"bị hỏng / không mở được"**, hoặc không có nút Open, mở **Terminal** và dán:
   ```bash
   xattr -dr com.apple.quarantine "/Applications/Suno Downloader.app"
   ```
   Rồi mở lại app.

</details>

### Bước 3 - Đăng nhập &amp; mua gói Suno

**Cần tài khoản có gói Suno còn hạn - không có bản miễn phí.** Mở app và đăng nhập bằng Google; chưa có gói thì app mở màn hình mua gói. Gói Suno là gói riêng, tách khỏi các gói của G-Labs Studio, tính theo thời hạn và không tự gia hạn:

| Thời hạn | Chuyển khoản QR (VietQR) | PayPal / USDT |
|---|---|---|
| 1 tháng | 50.000₫ | $3 |
| 6 tháng | 250.000₫ | $15 |
| 1 năm | 500.000₫ | $30 |

Gói nào cũng mở toàn bộ tính năng. Thanh toán ngay trong app bằng **QR ngân hàng (VietQR)**, **PayPal** hoặc **USDT** (USDT được kích hoạt thủ công - trả xong hãy nhắn cho nhà phát triển, như màn mua gói hướng dẫn). Một tài khoản dùng **một máy tại một thời điểm** - đăng nhập máy khác là máy cũ bị đẩy ra. Huy hiệu trên thanh tiêu đề hiện ngày hết hạn gói; bấm vào để kiểm tra hoặc gia hạn.

App **tự cập nhật**: huy hiệu phiên bản trên thanh tiêu đề kiểm tra GitHub Releases. Trên Windows app tải bộ cài mới rồi chạy luôn; trên macOS app tải và mở tệp `.dmg` mới để bạn kéo app vào Applications lần nữa.

---

## Lần chạy đầu tiên

1. **Mở app và đăng nhập bằng Google.** Huy hiệu ngày trên thanh tiêu đề cho biết gói Suno của bạn.
2. **Dán link Suno** vào ô trên cùng bên trái - một bài, playlist, hồ sơ hay trang khám phá - rồi bấm **Quét bài**. Trang nhiều bài mất khoảng 30 giây vì app tự cuộn để nạp hết.
3. **Chọn bài** trong danh sách hiện ra (đã tick sẵn tất cả) rồi bấm **Tải N bài** để đưa vào hàng đợi.
4. **Xem lại Cài đặt** bên trái: thư mục lưu, số luồng song song, định dạng và bitrate, ảnh bìa.
5. **Bấm Bắt đầu tải.** Chưa bấm thì chưa tải gì. Bài nào xong thì bấm biểu tượng thư mục để mở trong Finder / Explorer.

Bài riêng tư (không công khai) của chính bạn cần thêm phiên đăng nhập Suno - nạp ở thẻ **Cookie Suno** trước.

---

## Tính năng

![Suno Downloader](docs/screenshots/01-main.png)

- **Một link, cả loạt bài** - bài lẻ · playlist · hồ sơ · trang khám phá; app tự quét rồi đưa danh sách cho bạn chọn.
- **Chọn đúng bài muốn** - tìm trong danh sách vừa quét, chọn tất / bỏ chọn, bài đã có được gắn nhãn **Đã tải** để khỏi tải trùng.
- **Thêm trước, tải sau** - link vào hàng đợi; **Bắt đầu / Tạm dừng / Dừng hẳn** là ba nút riêng.
- **Định dạng &amp; bitrate** - **Gốc** MP4 giữ nguyên từng byte, Opus (chỉ đổi hộp chứa, không mã hoá lại), MP3, AAC, FLAC, WAV - xem [Định dạng](#định-dạng).
- **Tải song song** - 1-5 bài cùng lúc, mỗi dòng có ảnh bìa, phần trăm, dung lượng và thời lượng.
- **Kiểm tra từng file** - app đọc lại cấu trúc MP4 (đúng một đoạn khởi tạo, các mảnh nối liền không thủng, tổng thời lượng khớp metadata). Thiếu hay hỏng thì **báo lỗi**, không bao giờ lặng lẽ lưu nửa bài.
- **Sập cũng không mất bài** - trình duyệt nền chết giữa chừng thì bài đó tự chạy lại (tối đa 3 lần).
- **Ảnh bìa** lưu cạnh file nhạc, cùng tên.
- **Cookie cho bài riêng tư** - dán `cookies.txt` chuẩn Netscape, JSON từ tiện ích trình duyệt hay chuỗi header thô `a=1; b=2`; app cho biết cookie đó **đã đăng nhập** hay chưa. App không tự đọc kho cookie của trình duyệt.
- **Kho proxy** - dán proxy kiểu nào cũng được, tải xoay vòng qua danh sách, kiểm tra lại để đánh dấu proxy chết.
- **Lịch sử** - mọi bài đã tải, có ô tìm; cũng là nguồn của nhãn *Đã tải*.
- **6 ngôn ngữ** - English · Tiếng Việt · 简体中文 · Español · Русский · العربية (viết phải→trái).

---

## Các trang

### 🔗 Dán link &amp; quét

![Cửa sổ chính](docs/screenshots/01-main.png)

Dán một trong các dạng sau vào ô trên cùng bên trái rồi bấm **Quét bài** (**Huỷ quét** để dừng):

| Link | Kết quả |
|---|---|
| `https://suno.com/song/<id>` | đúng bài đó |
| `https://suno.com/playlist/<id>` | mọi bài trong playlist |
| `https://suno.com/@<tên>` | các bài của hồ sơ đó |
| `https://suno.com/explore` | những bài trên trang khám phá |

### ✅ Chọn bài để tải

![Chọn bài](docs/screenshots/02-scan.png)

Danh sách mở ra là đã tick sẵn tất cả. Gõ vào ô tìm để lọc, dùng **Chọn tất cả / Bỏ chọn**, và để ý nhãn xanh **Đã tải** - đó là những bài đã có trong lịch sử. **Tải N bài** đẩy các bài đã chọn vào hàng đợi.

### ⬇️ Hàng đợi tải

![Hàng đợi](docs/screenshots/03-queue.png)

**Bắt đầu tải** để chạy; **Tạm dừng** không kéo bài mới nhưng bài đang tải vẫn xong; **Dừng hẳn** huỷ tất cả. Mỗi dòng có thanh tiến độ, phần trăm, dung lượng và thời lượng, cùng các nút **Nghe thử**, **Mở thư mục**, và **Tải lại** cho dòng lỗi (**Thử lại bài lỗi** làm hết một lượt). **Xoá bài đã xong** dọn các dòng đã hoàn tất.

### ⚙️ Cài đặt

Ở cột bên trái, nên xem trước khi tải:

- **Thư mục lưu** - mặc định `Music/Suno Downloader`.
- **Số luồng song song** - 1 đến 5. Mỗi luồng chạy một cửa sổ trình duyệt ẩn riêng nên RAM tăng theo số luồng; 1-2 là đủ cho đa số máy.
- **Định dạng** và **Bitrate** - xem [Định dạng](#định-dạng). Ô bitrate tự mờ với định dạng không có bitrate.
- **Lưu ảnh bìa cạnh file nhạc** - ghi `Nghệ sĩ - Tên bài.jpg` ngay cạnh file nhạc.

### 🍪 Cookie Suno

![Cookie](docs/screenshots/04-cookies.png)

Bài không công khai của chính bạn cần phiên đăng nhập Suno. Mở **Cookie Suno**, dán vào rồi bấm **Nạp cookie đã dán**. Nhận `cookies.txt` chuẩn Netscape (xuất từ tiện ích trình duyệt), JSON từ tiện ích kiểu Cookie-Editor, hoặc chuỗi header thô như `__session=abc; other=1`. Dòng bên dưới cho biết tên miền, đã lưu bao nhiêu cookie, và nhãn xanh **đã đăng nhập** khi có cookie phiên thật - không có thì bài riêng tư sẽ tải lỗi.

### 🌐 Proxy

![Proxy](docs/screenshots/05-proxy.png)

Tuỳ chọn. Dán mỗi dòng một proxy rồi bấm **Thêm N proxy**:

```
203.0.113.24:8080
user:pass@198.51.100.7:3128
socks5://user:pass@192.0.2.55:1080
```

Gạt công tắc để bật - mỗi bài dùng một proxy khác, xoay vòng trong danh sách. **Kiểm tra lại** thử toàn bộ với `suno.com` (hoặc URL bạn tự đặt) và đánh dấu proxy chết để xoá bằng một nút.

### 🕘 Lịch sử

![Lịch sử](docs/screenshots/06-history.png)

Nút **Lịch sử** ở góc trên phải liệt kê mọi bài đã tải - ảnh bìa, nghệ sĩ, tên bài, dung lượng, ngày - kèm ô tìm. Đây cũng là nguồn của nhãn *Đã tải*, nên quét lại cùng một playlist sẽ không mất công tải trùng. **Xoá lịch sử** chỉ dọn danh sách, file nhạc vẫn còn nguyên.

### 🌍 Ngôn ngữ

![Giao diện phải→trái (العربية)](docs/screenshots/07-rtl-arabic.png)

Giao diện có English, Tiếng Việt, 简体中文, Español, Русский và العربية; chọn tiếng Ả Rập thì toàn bộ bố cục chuyển sang viết phải→trái.

---

## Định dạng

| Chọn | File | Có mã hoá lại? | Bitrate |
|---|---|---|---|
| **Gốc** | `.mp4` | không - đúng byte Suno gửi | - |
| Opus | `.opus` | không - chỉ đổi hộp chứa | - |
| **MP3** *(mặc định)* | `.mp3` | có | 320 / 256 / 192 / 128 |
| AAC | `.m4a` | có | 256 / 192 / 128 |
| FLAC | `.flac` | có (hộp không mất chất, nhưng nguồn đã nén) | - |
| WAV | `.wav` | có (không nén) | - |

Suno gửi audio Opus đặt trong hộp MP4. **Gốc** giữ nguyên từng byte; mọi lựa chọn khác đều là chuyển mã - tương thích rộng hơn, nhưng chất lượng không thể hơn bản gốc.

---

## Nơi lưu dữ liệu

| Thứ gì | macOS | Windows |
|---|---|---|
| Nhạc tải về (đổi được trong Cài đặt) | `~/Music/Suno Downloader` | `%USERPROFILE%\Music\Suno Downloader` |
| Cài đặt, lịch sử, cookie, danh sách proxy | `~/Library/Application Support/Suno Downloader` | `%APPDATA%\Suno Downloader` |

Mọi thứ bạn chỉnh - thư mục, số luồng, định dạng, bitrate, ảnh bìa, ngôn ngữ, danh sách proxy - đều được lưu và khôi phục ở lần mở sau.

---

## Khắc phục sự cố

**"Mới tải được 40% bài - hãy tải lại."** - mạng rớt giữa chừng. File bị từ chối có chủ đích chứ không lưu nửa vời. Bấm **Tải lại** ở dòng đó.

**Một bài báo "không tải được dữ liệu âm thanh"** - bài đó riêng tư mà app chưa có phiên đăng nhập. Thêm cookie ở thẻ **Cookie Suno**.

**Quét không ra bài nào** - kiểm tra link có đúng là địa chỉ `suno.com` không, và mở bằng trình duyệt xem trang đó có bài thật không.

**Mọi thứ bị khoá, cứ hiện màn mua gói** - gói Suno hết hạn, hoặc tài khoản vừa đăng nhập ở máy khác. Xem huy hiệu ngày trên thanh tiêu đề và gia hạn.

**App chậm hoặc ngốn nhiều RAM** - mỗi luồng tải song song là một cửa sổ trình duyệt ẩn. Hạ **Số luồng song song** xuống 1-2 trong Cài đặt.

**Windows chặn ở bảng "Windows protected your PC"** - bấm **More info → Run anyway**. App chưa ký chứng chỉ của Microsoft nên bị cảnh báo - không phải virus.

**macOS báo app bị hỏng / không mở được** - app không ký bằng Apple Developer ID. Lần đầu hãy chuột phải → **Open**, hoặc chạy `xattr -dr com.apple.quarantine "/Applications/Suno Downloader.app"`.

**Cập nhật không cài được** - tải bản mới nhất thủ công ở [Releases](https://github.com/duckmartians/Suno-Downloader/releases/latest).

---

<sub>Suno Downloader là công cụ độc lập, không liên kết hay được Suno, Inc. bảo trợ. Chỉ tải nội dung bạn có quyền sử dụng và tuân thủ điều khoản của Suno.</sub>
