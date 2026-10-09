# Nhật ký thay đổi — Auto Link

## 8.2.0 — 08/10/2026
**Mới: PDF → Mã QR** (Bộ công cụ › Link & Mã QR) — file PDF trong máy thành mã QR quét là mở file
- Mã QR chỉ chứa ~3 KB nên app tải PDF lên Google Drive của người dùng (ai có link đều xem được, kể cả khi lần trước
  chọn Riêng tư) rồi tạo mã QR theo **Thiết kế mã QR** — 1 file hay cả thư mục (lấy cả thư mục con, giữ cây thư mục
  cho mã QR); kết quả vào thư mục mã QR + Lịch sử mã QR.
- Nhánh **File → Link Google Drive** / **Ảnh → Link Google Drive** có công tắc mới **Tạo mã QR cho mỗi file**.
- Chưa đăng nhập Google: đăng nhập xong app **tự tải tiếp** (không phải bấm lại).

- **Google Drive: chỉ cần đăng nhập Gmail.** Bản cài có sẵn kết nối Google → trang Cài đặt bỏ nút **Cấu hình**; hộp
  cấu hình chỉ còn nút lớn **Đăng nhập Google** và **không còn hiện Client ID / Client secret đóng sẵn** (trước đây
  điền sẵn cả secret, ai mở cũng xem được).
- Đơn vị muốn dùng ứng dụng Google riêng (hoặc bản chạy từ mã nguồn): 5 bước theo đúng giao diện Google Cloud hiện
  nay, mỗi bước 1 nút **Mở** tới đúng trang; bấm copy trên trang Google hoặc **Download JSON** → app **tự điền** Client
  ID / secret (ô secret che dấu chấm); đủ cả 2 mã là app **tự lưu và mở đăng nhập Google** (không phải bấm nút nào).

**Mới: gói combo** — trang thanh toán VietQR có 4 gói: **1 tháng 49.000đ · 3 tháng 139.000đ (tiết kiệm 5%) · 6 tháng
259.000đ (12%) · 12 tháng 490.000đ (17%)**; mã QR tự điền đúng số tiền gói đã chọn.

**Google Drive bền khi nhiều người cùng tải**
- Google báo bận (quá hạn mức / lỗi máy chủ tạm / mạng chập chờn): app **tự chờ rồi tải tiếp** (chờ tăng dần, tối đa
  ~1 phút / lần), dòng trạng thái ghi "Google Drive đang bận — tự tải tiếp sau N giây"; không bỏ file nào.
- Tải hàng nghìn file: app **tự điều tốc** (mặc định tối đa 60 file / phút / máy, chậm lại khi Google bận rồi tự nhanh lại).
- **Tải tiếp đúng chỗ dừng:** tắt app / mất mạng / Google bận lâu → mở lại app báo "Còn N file chưa tải lên", bấm
  **Tải lên** chỉ tải file chưa có link (không tải trùng); file đã lên Drive nhưng chưa chia sẻ được thì chỉ chia sẻ
  lại (không tạo bản sao). Nút **Bỏ danh sách** xoá danh sách + hàng đợi dở; file đã xoá khỏi máy tự bỏ khỏi hàng đợi.
- Công cụ **PDF → Mã QR** không còn đổi công tắc "Tạo mã QR" / quyền chia sẻ bạn đã chọn ở nhánh Link Google Drive.
- Sửa: lỡ đóng tab đăng nhập Google rồi bấm **Đăng nhập** lại thì không có gì xảy ra (app vẫn chờ tới 3 phút) — nay
  mở lại đúng trang đăng nhập, đăng nhập xong vẫn nhận.
- Nhận dạng chữ (OCR): 1 trang quá 5 phút thì dừng và báo lỗi rõ (trước đây có thể chờ mãi).
- App tự kiểm tra kết nối Google mỗi 24 giờ; nhà cung cấp đổi mã kết nối thì app tự nhận, không cần cài bản mới.
- Sửa: dùng lâu, mở nhiều hộp thoại → tài nguyên đồ hoạ Windows tăng dần (mỗi hộp thoại nạp lại icon) — nay nạp 1 lần.

## 8.1.1 — 08/10/2026
- **Thanh thông báo từ nhà cung cấp** nổi trên đầu nội dung (không đẩy trang xuống): màn nhỏ 1024×768, cửa sổ thu
  nhỏ vẫn hiện đủ nút; thông báo dài gộp còn ~2 dòng, bấm **Xem** đọc toàn văn.

## 8.1.0 — 07/10/2026
**Mới: Tự cập nhật 1 chạm — nút "Cập nhật lên vX" cuối menu trái**
- App tự hỏi GitHub lúc mở và 3 giờ / lần khi đang mở (máy để cả ngày ở bộ phận một cửa vẫn được báo); có bản mới →
  thanh "Có phiên bản mới" + nút cuối menu trái đổi thành **Cập nhật lên vX** (nổi bật; bình thường là "Kiểm tra cập
  nhật").
- Bấm nút → hỏi lại bản mới nhất → **tải ngay** (thanh tiến độ, nút **Huỷ tải**), kiểm SHA-256 + chữ ký số của tác giả
  → đóng app, **thay đúng file đang dùng** (không cài thêm bản thứ 2), mở lại bản mới. Không còn bước cài thủ công.
- Dọn bộ nhớ: mở app tự xoá bản cũ (`.old`) và bản tải dở / bị huỷ (`.new`, `.new.part`) — máy chỉ giữ 1 bản.

**Mới: Đối chiếu dữ liệu** (mục mới ở menu trái) — phân loại thông minh, đối chiếu chính xác, xem lại trước khi ghi
- **2 hoặc nhiều nguồn cố định** (thêm / xoá được): mỗi nguồn = link Google Sheet công khai hoặc file Excel (.xlsx,
  .xls) + từ khoá "Cơ quan thực hiện" để nhận thủ tục mới (mặc định: Danh mục cấp Phường = "cấp xã; cấp phường…", Danh
  mục Phi địa giới = nhận phần còn lại).
- **Văn bản / danh mục cần cập nhật nhiều loại, chọn nhiều file một lúc**: Quyết định công bố PDF (đọc bảng theo đường
  kẻ ô, ô gộp, dòng ngắt trang) / Word .docx / .doc → mục A mới ban hành · B sửa đổi, bổ sung · C bãi bỏ; danh mục đầy
  đủ Excel / CSV / link Google Sheet → so trọn với nguồn trùng nhiều mã nhất.
- So **chính xác theo mã TTHC** (không có mã: theo đúng tên; bỏ qua chữ "Thủ tục" đầu tên): mã có ở nhiều nguồn → cập
  nhật mọi nguồn đó; thủ tục mới → nguồn có từ khoá khớp cơ quan thực hiện. Mục đã có người cập nhật trước (đã có / đã
  đúng / đã bỏ) → báo và bỏ qua.
- Bảng xem lại: tích chọn từng thay đổi, lọc theo nguồn, chọn dòng thấy đủ mục trong văn bản, cơ quan thực hiện, lý do
  xếp nguồn, cũ → mới.
- **Duyệt cập nhật**: hộp xem lại lần cuối liệt kê đúng những gì sẽ ghi → tải lại nguồn, **có người vừa sửa → không ghi,
  phân tích lại + cảnh báo** → ghi: file Excel ghi thẳng (sao lưu bản cũ vào `SaoLuu_AutoLink`, giữ định dạng + cột
  khác, ô vừa đổi tô vàng, ghi số quyết định vào cột "Quyết định công bố"; .xls qua Excel); Google Sheet của người khác
  → bản Excel đã cập nhật + Google Sheet cố định trên Drive của mình (ghi đè cùng link) → báo cáo
  `DoiChieu_TTHC_<giờ>.xlsx`.

**Đối chiếu dữ liệu — ghi thẳng lên link Google Drive, kiểm từng thay đổi trước khi ghi**
- Nguồn cố định / văn bản cần cập nhật nhận **link Google Drive** (file Excel, PDF, Word trên Drive, link "Mở bằng
  Google Sheets") ngoài file máy và Google Sheet công khai; link thuộc tài khoản Drive đang đăng nhập → tải đúng bản
  gốc qua Drive API.
- Sửa lỗi lặp "vừa có người cập nhật — phân tích lại": trước so byte bản xuất Google Sheet (gắn giờ xuất → đổi mỗi lần
  tải); nay so **md5 + phiên bản do Google cấp** (file trên Drive) / **nội dung từng ô** (link công khai, file máy).
- Duyệt cập nhật 2 pha: **thử ghi mọi nguồn trên bản sao → đọc lại, kiểm đúng từng thêm / sửa / bỏ** (lệch 1 chỗ →
  dừng, không ghi gì) → mới ghi. Link Drive của tài khoản đang đăng nhập → ghi phiên bản mới vào **đúng link** (link giữ
  nguyên), kiểm Drive đã lưu đúng nội dung, giữ vĩnh viễn phiên bản trước trong Lịch sử phiên bản + bản sao lưu cục bộ;
  có người sửa ngay trước khi ghi → không ghi, phân tích lại.
- Số quyết định văn thư cho bằng ô ký số (ảnh) → đọc ô đó bằng OCR, 4 cách đọc phải trùng nhau mới điền (không đoán).

**File → Link** (đổi tên từ Word → Hyperlink): nhánh Google Drive nhận **mọi loại file**; **nhiều tài khoản Google
Drive** (Đổi / thêm tài khoản, đăng xuất từng tài khoản); **chọn / tạo thư mục đích trên Drive**; hiện **dung lượng
Drive** của tài khoản; link mở bằng **đúng tài khoản** đang dùng trong app (Chrome đăng nhập nhiều tài khoản).

**Thông báo từ nhà cung cấp:** thanh trên đầu app hiện thông báo đã ký số (bảo trì, khuyến mãi, hướng dẫn) — bấm
**Xem** mở link, **✕** ẩn trên máy đó; hết hạn tự ẩn. **Mở app nhanh hơn:** giao diện dựng nhanh ~2 lần (thẻ vẽ 1 lần khi
cửa sổ hiện), file chạy bỏ thư viện video / AVIF không dùng (~36 MB).

**Cài đặt:** **Cỡ chữ** A− / A+ (85–150 %, cả giao diện co giãn theo, áp dụng khi mở lại app); **Âm báo khi xong
việc** cho mọi chức năng (tiếng khác khi có lỗi), bật / tắt.

**Mới: PDF → Word, PDF → Excel chuyển thật** (Bộ công cụ › Chuyển đổi & Office)
- PDF → Word: máy có Word → bộ chuyển PDF của Word (giữ phông, cỡ chữ, bảng, ảnh, khổ giấy); bản Word thiếu chữ so với
  PDF (Word biến trang thành ảnh) hoặc máy không có Word → tự dựng đoạn văn + bảng theo đường kẻ ô. PDF scan đã có lớp
  chữ ẩn (OCR) → lấy đúng lớp chữ đó (Word bỏ lớp chữ ẩn, tự nhận dạng lại → sai dấu).
- PDF → Excel: bảng dựng theo đường kẻ ô — đúng ô, ô gộp, độ rộng cột + chiều cao dòng như PDF, viền, tiêu đề đậm; chữ
  ngoài bảng giữ thứ tự; bảng sang trang nối liền, bỏ dòng tiêu đề lặp lại.

**Mới: Thiết kế mã QR — logo bất kỳ + 13 kiểu khung viền**
- Logo: **Tự động bỏ nền đồng màu ở 4 góc** (logo tròn trên nền đen / trắng, ảnh JPG không trong suốt — hết 4 góc đen),
  Cắt tròn, Bo góc, Giữ nguyên; logo tròn → phần khoét trong mã cũng tròn; **Nền biểu trưng** (đĩa nền sau logo).
- Khung thêm 7 kiểu: 4 góc ngắm, Viền đôi, Viền nét đứt, Viền + nhãn, Ruy băng, Điện thoại, Huy hiệu tròn (tổng 13).
- Sửa: lưu PNG nền không trong suốt — vùng ngoài khung bo góc không còn bị đen.

**Mới: Nút số bước 01 · 02 · 03 bấm được** (Word / Ảnh và Link → Mã QR): đi thẳng tới bước đó để sửa rồi chạy lại;
nút Khôi phục (hoàn tác) đổi biểu tượng cho khỏi nhầm với quay lại bước.

**Link Google Drive:** chọn quyền chia sẻ (chỉ xem / nhận xét / chỉnh sửa / riêng tư), tải cả thư mục giữ nguyên cây
thư mục trên Drive, đăng nhập xong tự mở My Drive, phiên đăng nhập tự làm mới mỗi 24 giờ (hết hạn → báo đăng nhập lại).

**Mới: Word → Hyperlink và Ảnh → PDF có link chia 2 nhánh rõ ràng** (thanh chọn ở đầu trang)
- Nhánh 1 như cũ: quét mã QR → hyperlink / PDF có link.
- Nhánh 2 **→ Link Google Drive**: đăng nhập Google Drive thủ công 1 lần (dùng chung phiên với Cài đặt), chọn file hoặc
  cả thư mục (gồm thư mục con) Word (.docx, .doc, .rtf, .odt) / ảnh mọi định dạng (jpg, png, gif, webp, heic, tiff…) →
  tải hàng loạt, mỗi file 1 link xem công khai; bảng link, chép tất cả, bấm đúp chép 1 link, xuất Excel (link bấm được),
  nút Dừng giữa chừng.

**Mới: Bộ cài `Auto-Link-Setup.exe` đủ bước** (Chào mừng → thư mục cài → ☑ lối tắt Desktop → Cài đặt → ☑ Mở Auto
Link ngay), tiếng Việt, không cần quyền quản trị, cài đè đúng thư mục cũ (không để 2 bản), tự đóng app đang mở; gỡ được
trong Settings › Apps.

**Dự án:** sắp xếp lại cây thư mục (ghi chú kỹ thuật → `docs\kien_thuc\`, logo gốc + mẫu QR tham khảo →
`docs\tham_khao\`, nháp cũ → `_luu_tru_tam\`); `CLAUDE.md` nhập chung `AGENTS.md` (hết lệch đường dẫn `src\`).

**Mới: Danh mục TTHC → Kiosk đọc thêm file `.xls` (Excel đời cũ) và `.csv`**
- `.xls`: Excel lưu bản sao tạm thành `.xlsx` rồi đọc như cũ (không thêm thư viện, file gốc không đổi; cần máy có
  Microsoft Excel).
- `.csv`: tự nhận mã hoá UTF-8 / Windows-1258 và dấu phân cách `;` `,` tab (Excel tiếng Việt hay lưu `;`); bộ phận
  = tên file.
- File `.xlsx` đọc y như bản 8.0.1.

**Mới: Tải kết quả lên Google Drive + link chia sẻ công khai** (Word → Hyperlink › Bước 02, dòng "Tải lên Google
Drive")
- Viết lại bằng Google Drive API v3 chính thức, chỉ thư viện chuẩn (`src/ggdrive.py`) — bỏ Selenium /
  webdriver-manager / chromedriver tải từ mạng, không cần Chrome, EXE không nặng thêm.
- Đăng nhập Google qua trình duyệt (PKCE, dùng chung client của đăng nhập bản quyền), quyền `drive.file`: app chỉ thấy
  file do chính nó tải lên. Phiên đăng nhập lưu `%APPDATA%\AutoLink\google_drive.json`, mã hoá DPAPI theo tài khoản
  Windows. Nút Đăng nhập ↔ Đăng xuất (đăng xuất thu hồi quyền trên Google).
- File kết quả (Word, PDF, ảnh → PDF) vào thư mục "Auto Link" trên Drive, đặt quyền "bất kỳ ai có link đều xem được"
  (bản cũ chưa chia sẻ → người khác không mở được link); bảng `GoogleDrive_Links.csv` cạnh kết quả; tải resumable (file
  lớn không nạp hết vào RAM), mã hết hạn giữa lượt tự làm mới; lỗi báo rõ (chưa bật Drive API, hết dung lượng, tổ chức
  chặn chia sẻ công khai…).
- Sửa: chọn "chỉ Word" / Ảnh → PDF trước đây bỏ qua bước tải Drive; file link ghi chữ `\n` thay vì xuống dòng.
- Chủ sản phẩm cần bật Google Drive API + quyền `drive.file` + Publish app (xem Sổ tay quản trị mục 5).

**Sửa lỗi**
- Thiếu trạng thái `scan_qr` trong bộ theo dõi tác vụ nền (có thể báo `KeyError` khi quét mã QR).
- Thêm bản dịch tiếng Anh còn thiếu.
- Mã QR tuỳ chọn màu: màu có kênh trong suốt (`#RRGGBBAA`) trước đây bị bỏ qua âm thầm (mã ra màu đen); tô màu
  không còn dùng `Image.getdata` (Pillow 14 gỡ bỏ, 10/2027).
- Dọn lỗi tiềm ẩn: đọc CSV luôn có nội dung dù mọi mã hoá đều sai, `except:` trần, closure dùng biến vòng lặp, file
  khoá của công cụ quản trị không được đóng.
- IDE (Pyrefly) báo "Cannot find module auto_link / banquyen…" từ khi chuyển mã vào `src/`: thêm `pyrefly.toml`.

## 8.0.1 — 02/10/2026
**Mới: Danh mục TTHC (Excel) → mã QR + trang tra cứu cho máy kiosk cảm ứng** (trang Link → Mã QR, nút "Danh mục TTHC
(Excel) → QR + Kiosk"; Bộ công cụ › Link & Mã QR)
- Đọc mọi sheet của file danh mục (sheet = bộ phận), cột Mã TTHC / Tên thủ tục / Lĩnh vực / Link theo tên cột; mã ghi
  lệch ("2.002.400", "2002638", số Excel bỏ số 0) tự chuẩn hoá.
- Đối chiếu toàn bộ CSDL thủ tục Cổng DVC Quốc gia (~6.500, thường + liên thông): theo mã, không mã thì theo nguyên
  tên (không đoán gần đúng). Có trên Cổng → link trang thủ tục + mã QR; không có → "Nộp trực tiếp". Thử với danh mục
  371 thủ tục cấp phường: 321 có trên Cổng, 50 nộp trực tiếp (~80 giây).
- Kết quả: trang kiosk `index.html` 1 tệp (tìm theo tên gõ không dấu, bàn phím ảo, lọc theo bộ phận, mã QR + nút mở
  trang, tự về màn đầu sau 2 phút) + `Mo_kiosk.cmd` (Edge chế độ kiosk); Excel kết quả có link; Word danh mục có mã QR
  theo từng bộ phận.

**Sửa lỗi**
- **Đổi giá ở công cụ quản trị làm trang thanh toán của khách lỗi "'name'", không hiện mã QR:** công cụ chỉ đăng giá,
  app gộp cấu hình nông nên mất tên + số ngày gói. Công cụ nay đăng đủ tên + số ngày + giá (sửa luôn cho app 8.0.0 đang
  chạy); app gộp cấu hình sâu (cấu hình chỉ có giá vẫn giữ tên / số ngày).
- **Tự cập nhật / kiểm chữ ký số khi app được mở từ PowerShell 7:** trước đây PowerShell nạp nhầm module của bản 7
  (biến `PSModulePath` thừa hưởng) → không thay được file và không tự mở lại app. Mọi tiến trình PowerShell con của app
  nay dùng môi trường sạch.
- **Hộp "Chọn link vừa cào":** dòng tiêu đề dài tự xuống dòng trên màn nhỏ phóng chữ to (trước đây bị cắt chữ).
- **Kiểm tra tự động trên GitHub (CI) chạy được trọn vẹn:** sửa lỗi bảng mã khi in ra màn hình (máy CI dùng cp1252),
  test PowerPoint tự bỏ qua khi máy không có Office; lint thêm `banquyen.py`, `ngonngu.py`.
- **Quản trị:** công cụ quản trị có lệnh `--cap` (cấp với số ngày tuỳ chọn: gia hạn sớm, chuyển máy, tặng ngày) và
  `--thu-hoi` (thu hồi chỉ bằng Gmail + mã máy); tab Cấu hình cửa hàng điền đúng cấu hình đang chạy (đăng lại không vô
  tình đổi giá / tắt đăng nhập Google). Sổ tay quản trị `docs/SO_TAY_QUAN_TRI.md`; script đóng gói phát hành
  `scripts/dong_goi_phat_hanh.py`. Bảng Sổ đã cấp chia cột theo nội dung, cửa sổ công cụ to theo DPI màn hình.
- **Công cụ quản trị "kích hoạt từ xa" 1 màn hình** (biểu tượng **Auto Link Quản trị** trên Desktop / Start, tạo bằng
  `--tao-loi-tat`): dán tin nhắn khách (mã kích hoạt hoặc Gmail + mã máy, nhập tay — không nhận dạng ảnh) → tự điền
  Gmail / mã máy / gói, hiện nội dung CK + số tiền để đối chiếu sao kê; khách cũ chỉ gửi Gmail hoặc mã máy → tra sổ;
  gia hạn sớm tự cộng ngày còn lại (đọc giấy phép đang chạy trên GitHub); bắt buộc tích "Đã thấy tiền vào tài khoản";
  lưu ảnh minh chứng (cột Minh chứng); đăng rồi đọc lại GitHub; chép sẵn tin nhắn trả lời khách. Sổ đã cấp: tìm, lọc
  sắp hết hạn 7 ngày, bấm đúp để gia hạn / thu hồi. Sổ tay quản trị riêng `Auto_Link_So_tay_quan_tri.docx`.
- **Công cụ quản trị dạng EXE** (`scripts/dong_goi_quan_tri.py` → `dist\AutoLink_QuanTri.exe`, không chứa khoá): máy mới
  mở lần đầu chọn `owner_key.txt` từ USB (chỉ nhận đúng khoá chủ sản phẩm), tự tạo biểu tượng Desktop; gọi GitHub CLI
  không bật cửa sổ đen, máy chưa cài `gh` thì báo cách cài. Ô "Mã bản quyền (key) gửi khách" hiện mã vừa cấp.
- **Sổ tay Word / PDF có ảnh minh hoạ:** hướng dẫn khách hàng `docs/HUONG_DAN_KHACH_HANG.md` (17 mục) +
  `scripts/tao_so_tay.py` tạo `Auto_Link_Huong_dan_khach_hang.docx` (gửi khách) và `Auto_Link_So_tay_day_du.docx`
  (khách hàng + quản trị, nội bộ) kèm PDF, có mục lục, số trang.

## 8.0.0 — 01/10/2026
**Đảo tính năng: có mã + tên thủ tục, chọn định dạng báo cáo**
- Trích xuất link, PDF → Ảnh + link, Mã QR → Link: thêm cột **Mã thủ tục** và **Tên thủ tục / Nội dung** (lấy từ chữ
  quanh link trong Word / PDF, sổ Theo dõi TTHC, lịch sử mã QR, danh sách link đang mở).
- Chọn định dạng báo cáo: **Excel, Word, PDF, TXT, CSV** hoặc **Theo file gốc** (Word → Word, PDF → PDF…); app nhớ
  lựa chọn lần sau.

**Bộ công cụ dạng accordion**: các nhóm thu gọn sẵn; bấm 1 nhóm thì nhóm đó mở, nhóm khác tự đóng (trượt mượt); ô tìm
nhanh tự mở nhóm có kết quả.

**Giao diện**
- 8 chủ đề (thêm 4): **Neumorphism sáng / tối**, **Glass · Aurora**, **Next-Gen · Holo**. Cài đặt có bảng ô màu xem
  trước, bấm là đổi.
- 5 bộ icon đổi tại chỗ: Fluent, Fluent màu, Cổ điển, Emoji, Nét mảnh.
- Hiệu ứng chuyển động (tắt được): nhóm trượt mở, thông báo trượt vào, gợn sóng khi bấm nút, vạch sáng khi chuyển trang.
- Nút **EN / VI** trên thanh đầu: đổi toàn bộ giao diện Tiếng Việt ⇄ English ngay (dữ liệu, tên file giữ nguyên).
- Thanh đầu có nút **Thanh toán** (mã VietQR ngân hàng), **Zalo** 0788962643 (mã QR), **Website** mechamike.vercel.app.

**Bản quyền & thanh toán** (chỉ áp dụng ở bản `Auto_Link.exe`)
- Đăng nhập Gmail (có thể thêm đăng nhập Google qua trình duyệt — OAuth PKCE — khi chủ sản phẩm cấu hình).
- Dùng thử **3 ngày / máy**: chống xoá file / sửa tay / lùi đồng hồ (lưu kèm mã kiểm tra + registry).
- **Gói Pro 49.000đ / tháng** (đủ mọi chức năng; gói 12 tháng 490.000đ = giá 10 tháng): mã VietQR có sẵn số tiền + nội
  dung chuyển khoản riêng từng khách → gửi mã kích hoạt + ảnh giao dịch qua Zalo.
- Hết 3 ngày dùng thử → app hiện thông báo **yêu cầu nâng cấp gói Pro** (lúc mở app, khi bấm bất kỳ chức năng nào, và tự
  hiện nếu app đang mở đúng lúc hết hạn); đang dùng thử thì nhắc trước giá gói Pro. Thư mục tự động tạm dừng khi hết hạn
  (không xử lý miễn phí), có bản quyền là tự chạy lại.
- Chủ sản phẩm duyệt bằng công cụ quản trị (`admin\autolink_admin.py`, không đóng gói vào EXE) → giấy phép ký số
  Ed25519 gắn Gmail + máy, đưa lên GitHub → app **tự kích hoạt** (kiểm tra mỗi 30 phút, mỗi phút khi đang mở trang
  thanh toán); hoặc dán mã bản quyền `AL1.…` để kích hoạt ngay. Thu hồi được; giá, số ngày dùng thử, tài khoản nhận tiền
  đổi được qua cấu hình cửa hàng đã ký (không cần phát hành bản mới).
- App chỉ gửi **mã băm tài khoản** lên GitHub để kiểm tra — tài liệu luôn xử lý trên máy. Giấy phép đăng công khai chỉ
  chứa mã băm (Gmail + máy), không chứa Gmail.
- **Điều khoản sử dụng & Chính sách quyền riêng tư** (NĐ 13/2023, hoàn tiền, không tự gia hạn): hộp đăng nhập báo
  "Tiếp tục nghĩa là bạn đồng ý…" + nút **Điều khoản**; trang thanh toán cũng có nút Điều khoản.

**Cập nhật tự động qua GitHub**: mở app (tối đa 12 giờ / lần) kiểm tra bản phát hành mới → thanh thông báo kèm ghi chú
phiên bản → bấm **Cập nhật ngay**: tải (có tiến độ), kiểm chữ ký số + SHA-256, thay file khi app đóng rồi tự mở lại.
Bản tải về bị sửa → không cập nhật. Thư mục cập nhật nội bộ của IT vẫn dùng được.

**Khác**
- Hướng dẫn trong app thêm mục Giao diện & ngôn ngữ, Bản quyền & thanh toán.
- Hộp đăng nhập hiện khi đã vừa nội dung (không chớp hàng nút bị ép trên màn nhỏ).
- Tự kiểm tra EXE thêm mục "Bản quyền (chữ ký số, VietQR) + báo cáo Word / PDF / TXT / CSV".

## 7.1.1 — 01/10/2026 (bản sửa lỗi)
- **"Mở file" ở màn hình kết quả không mở được** (`[WinError -2147221003] Application not found`): máy đặt ứng dụng
  khác (vd WPS) mở PDF nhưng thiếu liên kết hệ thống `.pdf`. Mọi nút mở file / thư mục dùng `open_path`: chuẩn hoá
  đường dẫn (`/` → `\`), Windows báo lỗi thì mở bằng đúng ứng dụng người dùng đã chọn (UserChoice), không có thì hộp
  "Mở bằng…" của Windows.
- **Thông báo "Có lỗi: RoundedButton.__init__.<locals>.<lambda>() missing 1 required positional argument: 'e'"** khi
  màn hình kết quả hiện ra: nút cũ bị huỷ lúc hiệu ứng rê chuột còn chờ → Tcl gọi nhầm lệnh của nút mới cùng tên.
  Sửa tận gốc cho mọi widget: tên lệnh hẹn giờ (`after`) không bao giờ trùng, widget bị huỷ thì huỷ việc chờ của nó.

## 7.1.0 — 01/10/2026
**Mới — "Đảo tính năng"**: nút ⇄ bên phải tiêu đề mỗi chức năng chính mở chức năng chiều ngược
- Word → Hyperlink ⇄ **Trích xuất link**: mọi link trong Word / PDF (hyperlink, cả trường HYPERLINK Word tự tạo khi
  dán link; link dạng chữ, cả trong bảng; mã QR trong ảnh) → Excel 2 sheet: "Tất cả link" (file, vị trí, chữ hiển thị,
  nguồn) và "Link duy nhất" (gộp trùng, đếm số lần). Tuỳ chọn gỡ hyperlink: lưu bản Word `_khong_link`, giữ nguyên chữ.
- Ảnh → PDF có link ⇄ **PDF → Ảnh + link**: mỗi trang PDF 1 ảnh JPG (100–300 dpi, mỗi PDF 1 thư mục) + Excel link
  của từng trang (link bấm được và link dạng chữ).
- Link → Mã QR ⇄ **Mã QR → Link**: đọc mọi mã QR (cả nhiều mã / trang) trong ảnh, PDF (cả bản scan), Word → Excel
  (link / văn bản, kể cả nội dung tiếng Việt).
- Trích / đọc được link → nút **"Tạo mã QR từ các link này"** đưa thẳng sang Link → Mã QR (giữ nhãn, bỏ link trùng).

**Sắp xếp chức năng khoa học hơn**
- Menu trái theo nhóm: XỬ LÝ (Word → Hyperlink, Ảnh → PDF có link, Link → Mã QR, Bộ công cụ) · THEO DÕI (Lịch sử mã
  QR, Nhật ký xử lý) · HỆ THỐNG (Cài đặt).
- Bộ công cụ (35) xếp 5 nhóm việc: Văn thư & Dịch vụ công · Link & Mã QR · Chuyển đổi & Office · Sắp xếp & chỉnh sửa
  PDF · Bảo mật, tối ưu & lưu trữ; ô **tìm nhanh** (gõ không dấu vẫn ra, dán cũng lọc ngay).

**Hiển thị đầy đủ trên mọi màn hình / thiết bị** (màn cũ 1024×768, laptop HD 100–125 %, Full HD 150–175 %, máy tính
bảng 1280×800, 2K, 4K; cửa sổ thu nhỏ, Snap nửa màn hình)
- Cửa sổ hẹp: menu trái thu thành cột icon (rê chuột / Tab hiện tên); cửa sổ thấp: ẩn tiêu đề nhóm, chân menu.
- Hàng nút tự xuống dòng (Nhật ký, Lịch sử, trang Link, bảng chọn link, chân trang) thay vì bị ép, cắt chữ; dòng tuỳ
  chọn (Cài đặt, Bước 2) đưa nút / lựa chọn xuống dưới chữ khi hẹp; đường dẫn, mô tả dài tự xuống dòng.
- Mọi trang cuộn được khi màn thấp, bảng / ô nhật ký không bị ép dẹt; nút chính luôn ghim đáy trang.
- Hộp thoại không cao / rộng quá màn hình (phần thân cuộn được), không lọt xuống dưới thanh tác vụ.
- Cửa sổ nhỏ nhất 760 × 520 px logic (trước: bằng cỡ mặc định).
- Test tự động giả lập 8 loại màn hình × 4 cỡ cửa sổ (phóng to, mặc định, nửa màn hình, nhỏ nhất); tự kiểm tra EXE thêm
  mục "Đảo tính năng".

## 7.0.1 — 30/09/2026
**Sửa lỗi hiển thị thiếu thành phần trên laptop 14 inch** (Full HD phóng chữ 150 %, HD 1366×768, màn 2K 200 %)
- Menu trái rộng cố định 232 px → máy phóng chữ 150 % bị cắt "Auto Lin", "Dịch vụ công s", "Word → Hyperlin". Nay
  menu tự nới theo chữ (tối thiểu vẫn 232 px); icon, chữ, vòng bước 01–02–03 phóng theo tỉ lệ màn hình.
- Nút tự nới cả chiều cao theo chữ (màn 200 % chữ tràn mép nút) và khi đổi chữ (vd "Thêm vào danh sách (1.234)").
- Màn 1366×768: nút "Tiếp tục" bị ép còn 2 px, hàng "Quay lại / Bắt đầu xử lý" bị ẩn → không sang được bước sau. Nay
  nút ghim đáy trang như bước 3, nội dung bước 1 – 2 cuộn được khi màn thấp.
- Cửa sổ mặc định tính theo vùng làm việc (trừ thanh tác vụ, thanh tiêu đề theo tỉ lệ phóng): trước đây ở 150 % đáy
  cửa sổ (thanh trạng thái, nút cuối trang) nằm dưới thanh tác vụ. Cỡ nhỏ nhất đủ chỗ cho hàng 6 nút (Nhật ký,
  Lịch sử) thay vì ép nút.
- Dòng "Đã chọn x/y link" không còn bị ẩn khi cửa sổ thấp; đường dẫn sổ lịch sử dài tự xuống dòng.
- Test tự động giả lập 3 loại màn hình: mọi trang, 32 hộp thoại công cụ, ở cửa sổ phóng to / mặc định / nhỏ nhất.

## 7.0 — 09/2026
**Sửa lỗi người dùng báo trên bản 6.2**
- Cào link: Cổng DVC lấy đúng danh sách của trang đã dán (trước đây link nào cũng ra toàn bộ 6.472 thủ tục) —
  Dịch vụ công trực tuyến (Công dân + Doanh nghiệp), Tra cứu thủ tục (theo từ khoá, lĩnh vực, cấp, tỉnh/bộ),
  Thủ tục liên thông; trang web khác chỉ lấy link ở nội dung chính (bỏ menu, đầu/chân trang).
- Phân loại link như trên Cổng: tự chèn [Thư mục] theo lĩnh vực / cơ quan ban hành / cơ quan thực hiện / đối
  tượng (chọn được), thư mục lồng nhau.
- Word → PDF "treo": file có mật khẩu mở làm Office hiện hộp thoại ẩn và chờ hết 5 phút → nay báo ngay; tiến độ
  đếm giây khi Word xuất tài liệu lớn; thanh trạng thái không còn giữ chữ "Hoàn tất" của lượt trước.
- PowerPoint → PDF lỗi "SaveCopyAs: An error occurred…": xảy ra khi PDF đích đang mở trong trình xem PDF → nay
  lưu tên mới. Chuyển PDF không còn đóng mất bài trình chiếu người dùng đang mở (làm trên bản sao).
- PDF → Word mất dấu (DE NGHỊ LAM THÊM GIO): OCR nay chỉ dùng mô hình tiếng Việt; thêm tuỳ chọn nhận dạng lại
  PDF có lớp chữ hỏng.
- Xoay PDF báo "y1 must be greater than or equal to y0" dù đã xoay xong → hết.
- Nhật ký xử lý ghi cả thao tác của Bộ công cụ (thành công / lỗi, kèm giờ).
- Cào link vẫn "cào hết" (dán trang chủ Cổng DVC ra 6.513 thủ tục) → nay bám đúng trang đã dán: trang chủ (3 nút
  dịch vụ, tin tức, 22 nhóm Công dân / Doanh nghiệp), trang nhóm sự kiện (các mục + thủ tục), Dịch vụ công trực tuyến /
  nổi bật, Tra cứu thủ tục, Thủ tục liên thông; danh sách không lọc chỉ lấy trang đang hiển thị (tích "Lấy mọi trang"
  để lấy hết). Trang web khác phân loại thông minh theo chính trang đó: tiêu đề mục, cột Lĩnh vực / Chuyên mục của
  bảng (hoặc chọn theo đường dẫn / tên miền); trang dựng bằng JavaScript được dựng bằng Edge có sẵn; trang chặn trình
  duyệt tự động → lưu trang (Ctrl+S) rồi "Mở trang đã lưu".
- PowerPoint → PDF lỗi "SaveCopyAs: An error occurred…" với bài nhúng phông chỉ-xem/in (UTM, UVN…) → xuất PDF từ ảnh
  slide, báo rõ phông gây khoá; .ppt có mật khẩu báo ngay thay vì treo; nhận thêm .pptm .ppsx .pps .potx .odp.
- Tích chọn từng link: sau khi cào có hộp thoại chọn link, trang Phân loại tích từng link hoặc cả thư mục, tìm kiếm
  (gõ không dấu vẫn ra), lọc theo thư mục; chỉ tạo mã QR cho link đã chọn, danh sách > 500 link không tự chọn hết.
- Cài đặt: dải chọn giao diện bị cắt mất lựa chọn cuối ở cửa sổ mặc định → hiện đủ; trang Cài đặt cuộn được
  khi màn hình nhỏ / phóng chữ 125–200 %.
- Dùng được bằng bàn phím: Tab / Shift+Tab tới mọi nút, mục menu trái, thẻ công cụ, công tắc (có viền focus),
  Enter / Space để bấm, Esc đóng hộp thoại; lưới công cụ và trang Cài đặt tự cuộn tới chỗ đang chọn.

**Mới**
- Khôi phục (hoàn tác lượt vừa làm) ở mọi chức năng: Bộ công cụ — file vừa tạo vào Thùng rác, file bị lưu đè trả
  bản cũ, Đổi tên hàng loạt trả tên cũ; Word → Hyperlink / Ảnh → PDF / Link → QR — cả lượt (Link → QR bỏ luôn các
  dòng của lượt đó khỏi sổ lịch sử). Nút "Xử lý tiếp" mở lại công cụ để làm file khác ngay.
- Ô tích chọn trong Nhật ký xử lý và Lịch sử mã QR: sao chép, xuất, xoá mục đã chọn; khôi phục mục vừa xoá. Nhật ký
  không còn bị xoá mỗi lượt xử lý mới.
- PDF → JPG chọn 150 / 200 / 300 / 400 / 600 dpi. Đổi tên hàng loạt: đổi đuôi file, lọc theo đuôi.
- Nối Word / Excel / PowerPoint (giữ định dạng); Excel có thêm cách nối dòng dữ liệu vào 1 sheet.
- Xử lý hàng loạt + công thức (đề xuất 5): nhiều file / cả thư mục, chuỗi OCR · sửa · xoay · cắt lề · đánh số ·
  dấu bản quyền · nén, lưu công thức dùng lại.
- Trộn văn bản (đề xuất 4): mẫu Word ({{Tên cột}}, «…», MERGEFIELD) + Excel/CSV → Word, PDF, file gộp để in,
  {{QR:cột}} chèn mã QR.
- Số hóa hồ sơ (đề xuất 1): thư mục scan → PDF tìm kiếm được, tên theo mã hồ sơ (chữ hoặc mã QR), nén dưới giới
  hạn MB, sổ danh mục Excel.
- Văn bản đến (đề xuất 2): trích số ký hiệu, ngày, cơ quan ban hành, tên loại, trích yếu → sổ đăng ký văn bản
  đến theo NĐ 30/2020, số đến nối tiếp trong năm, ô chưa chắc chắn tô vàng.
- Kiểm tra thể thức (đề xuất 3): soát file Word theo NĐ 30/2020 Phụ lục I (khổ giấy, lề, phông, cỡ chữ, quốc
  hiệu, tiêu ngữ, số ký hiệu, ngày tháng, nơi nhận), tự sửa phần an toàn ra bản …_DaSua.docx, báo cáo .txt có
  tỷ lệ văn bản đúng thể thức lần đầu; quy tắc ghi đè được bằng `%APPDATA%\AutoLink\the_thuc.json`.
- Xuất PDF/A lưu trữ (đề xuất 9): PDF / scan / Word / Excel / PowerPoint → PDF/A-2b (XMP pdfaid, OutputIntent
  sRGB, Info khớp XMP, /ID, bỏ JavaScript/file đính kèm; trang dùng phông không nhúng được vẽ lại + OCR để vẫn
  tìm kiếm được) và "Chỉ kiểm tra" các yêu cầu chính của PDF/A; có bước "Chuyển PDF/A" trong công thức hàng loạt.
- Che thông tin cá nhân (đề xuất 8): tự dò CCCD, CMND, hộ chiếu, điện thoại, email, số tài khoản (+ cụm từ tự nhập)
  trên lớp chữ hoặc bằng OCR; trang có thông tin được vẽ lại, tô đen rồi nhận dạng chữ lại → xoá hẳn, không còn chữ
  ẩn chép ra được; trang khác giữ nguyên; báo cáo chỉ ghi giá trị đã che bớt; bỏ siêu dữ liệu tác giả.
- Thư mục tự động (đề xuất 10): máy scan / phần mềm khác lưu file vào thư mục theo dõi → tự chạy công thức và lưu
  PDF vào thư mục kết quả; chỉ nhận file đã ghi xong, file gốc chuyển vào `DaXuLy\` (lỗi → `Loi\`), kết quả ghi
  Nhật ký xử lý; đang bật mà đóng app thì lần mở sau tự bật lại.
- So sánh văn bản (đề xuất 13): 2 bản dự thảo Word / PDF / scan → file Word đánh dấu chữ thêm (xanh, gạch dưới),
  chữ bỏ (đỏ, gạch ngang), đếm số đoạn thêm / bỏ / sửa.
- Theo dõi TTHC (đề xuất 13): mỗi lần cào 1 trang Cổng DVC, app so với lần cào trước của đúng trang đó → báo thủ
  tục mới, không còn (bãi bỏ / chuyển), đổi tên hoặc lĩnh vực vào Nhật ký xử lý.
- Bộ cài + cập nhật qua mạng nội bộ (đề xuất 11): `Cai_dat.cmd` cài cho người dùng hiện tại, không cần quyền quản
  trị (lối tắt Start / Desktop, mục gỡ trong Settings › Apps, cấu hình mẫu `AutoLink_CauHinh.zip` cho máy mới);
  mở app tự kiểm tra thư mục mạng của IT, hỏi rồi thay bản mới (kiểm SHA-256; nếu bản đang dùng đã ký số thì bản
  mới phải cùng chứng thư) và tự mở lại. Cài đặt › Cập nhật phần mềm để kiểm tra / đổi nguồn.

**Nền tảng (đề xuất 6, 12)**
- Git + CI (GitHub/Gitea Actions chạy lint + test trên Windows), hook pre-commit.
- Ký mã EXE tự động khi có chứng thư (`scripts/sign.ps1`, PFX hoặc chứng thư trong kho / USB token).
- Module `vanban.py`: lõi văn bản hành chính tách khỏi giao diện.
- Bỏ fpdf2 (LGPL) cùng fontTools, defusedxml: thư viện Python đóng gói đều dùng giấy phép BSD / MIT / Apache / PSF.
  Ảnh → PDF có link vẽ bằng ReportLab, ảnh JPEG nhúng nguyên bản (ảnh chụp 4 MB → PDF ~4 MB, trước đây 34 MB).
- Cài đặt › Sao lưu / khôi phục: cài đặt, công thức, thư mục tự động, quy tắc thể thức, sổ lịch sử mã QR → 1 file
  .zip; khôi phục tự sao lưu bản đang dùng trước, sổ lịch sử được gộp (không mất, không nhân đôi mã).

**Kiểm thử:** 143 test tự động (từ 71), có test tái hiện từng lỗi người dùng báo; test bộ cài, cập nhật chạy trên
tiến trình thật; test dùng hoàn toàn bằng bàn phím.

**Chưa làm (chờ đơn vị):** ký mã EXE (cần chứng thư — build đã tự ký khi có), đề xuất 7 ký số PDF (cần USB token mẫu),
đề xuất 14 trợ lý AI (cần chính sách), gói MSI (cần cho phép tải WiX Toolset).

## 6.2 — 09/2026
**Mới**
- OCR tiếng Việt tích hợp sẵn (Tesseract 5.4 + tessdata_best `vie`): *PDF scan → PDF tìm kiếm / chép chữ được*
  (trang đã có chữ giữ nguyên, chỉ nhận dạng trang ảnh) hoặc → văn bản `.txt`; báo tiến độ từng trang.
  Độ chính xác đo trên trang văn bản hành chính giả lập scan: 99,8 %, ~1,3 giây/trang A4.
- PDF → Word tự nhận dạng chữ các trang scan (trước đây ra trang trắng).
- Cài đặt › **Kiểm tra hệ thống** (13 mục, gồm OCR và Word → PDF) và **Nhật ký lỗi**.
- Tài liệu: `README.md` (triển khai, dữ liệu, xử lý sự cố, build), `THIRD_PARTY_NOTICES.txt`.

**Sửa lỗi**
- Sửa tệp PDF: cứu được file bị cắt đuôi / mất bảng xref (dùng PDFium dựng lại), trước đây báo lỗi.
- Lớp chữ PDF OCR không còn mất dấu tiếng Việt (thứ tự tham số `-l` của Tesseract).

**Kiểm thử:** 71 test tự động, phủ đủ 22/22 công cụ qua đúng hộp thoại giao diện.

## 6.1 — 09/2026
- Sửa 16 lỗi rà soát (B01–B16): bỏ sót URL trong bảng; mất ảnh / định dạng khi chuyển hyperlink; dấu chấm dính link;
  header/footer & bảng lồng; ghi đè cột dữ liệu khi điền link QR; bề rộng cột âm; Ảnh → PDF lỗi chữ tiếng Việt;
  lịch sử QR không mở được mã đã phân loại; thẻ thư mục ghi ra ngoài; nút Xoá lịch sử crash; đánh số trang che
  trắng nội dung; Nén PDF luôn lỗi; watermark mất dấu; đổi tên hàng loạt dở dang; im lặng khi không xuất được PDF.
- Office → PDF: không còn treo khi máy in mặc định là máy in mạng đang tắt; luôn đóng Office; có giới hạn thời gian.
- Công cụ chạy nền (không treo giao diện), lưu an toàn (ghi tạm rồi thay), đóng app khi đang tạm dừng không treo ngầm.
- Giao diện: lưới công cụ cuộn & tự co giãn, hộp thoại vừa nội dung theo DPI, icon 18 cỡ nét ở mọi mức phóng.
- Đóng gói: `.venv` sạch, phiên bản ghim, 1 file EXE có icon, ảnh chờ, thông tin phiên bản, không UPX, selftest.

## 6.0
- Bản gốc trước rà soát.
