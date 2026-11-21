# Báo cáo cá nhân — Ngày 11

Họ tên: **Đoàn Thị Ánh Hậu**  Mã học viên: **2A202603282**  
Phiên bản CVAT (Help → About): **chưa ghi nhận**  
Guideline: **Road v1.0**  Lần nộp (`revision` trong manifest): **1**  
Thời điểm tạo manifest: **21/11/2026 11:55:55 (Asia/Bangkok)**  
Thời điểm export trên CVAT: **chưa ghi nhận**  Số lần nộp lại sau Rework: **0**

> Thống kê lấy từ `DoanThiAnhHau-manifest.json` và lint trên hai ZIP hiện có. Manifest ghi 28/28 ảnh đủ tag, 16 ảnh front và 12 ảnh fisheye. Lint hiện có 12 cảnh báo front và 0 cảnh báo fisheye. Lint không thay việc tự rà nhãn trên ảnh gốc; không cần đối chiếu GT cho báo cáo tự kiểm này.

## 1. Kiểm project

| Mục | Đúng như guideline Road v1.0? | Ghi chú |
| --- | --- | --- |
| 6 label, đúng kiểu | Có theo file export | Lint đọc được các label Road và hình dạng tương ứng trong CVAT for images 1.1. |
| Thuộc tính và giá trị | Không có cảnh báo cấu trúc | Dùng taxonomy Road v1.0; cần mở Project → Labels trong CVAT để xác nhận giao diện project. |
| 4 tag ảnh | Có | Manifest ghi 16/16 ảnh front và 12/12 ảnh fisheye có đủ tag; lint không báo lỗi tag. |

Cách kết thúc polyline trên bản CVAT này: **chưa ghi lại thao tác trên phiên bản CVAT cụ thể; thông thường kết thúc bằng nhấp đúp điểm cuối.**  
Cách đặt tag ảnh trên bản CVAT này: **mỗi ảnh có 4 tag kiểu Tag, mỗi tag có thuộc tính `value`; camera dùng `front` hoặc giá trị fisheye theo hướng camera.**

## 2. Số lượng đã gán

| Task | Ảnh | lane | road_curb | crosswalk | drivable | traffic_light | traffic_sign |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| front bắt buộc | 12 | 22 | 4 | 3 | 16 | 16 | 18 |
| front-extra (đã làm **4 / 4**) | 4 | 10 | 0 | 2 | 6 | 5 | 8 |
| fisheye bắt buộc | 8 | 1 | 4 | 7 | 8 | 2 | 1 |
| fisheye-extra (đã làm **4 / 4**) | 4 | 0 | 0 | 3 | 4 | 0 | 0 |

## 3. Bảng ca khó

| Ảnh | Nhãn | Phân vân giữa | Đã chọn | Lý do |
| --- | --- | --- | --- | --- |
| A03 | lane R1 | Thiếu vạch R1 hay vạch không nhìn thấy rõ | Chưa chốt từ lint; rà ảnh gốc và chỉ gán nếu thấy vạch | Lint báo thiếu R1; không nên tự vẽ một đường khi ảnh không có vạch nhận diện được. |
| A05, A06 | lane L1/R1 | Bỏ sót hay ảnh không có vạch dọc làn | Không ép thêm nếu ảnh gốc không có vạch nhìn thấy | Các cảnh báo lint cho phép bỏ qua khi thật sự không thấy vạch; A06 có vạch qua đường nhưng đó không phải vạch làn. |
| A07, A08, A09, A10, A12, A16 | lane L1/R1 | Thiếu vị trí hay không có đủ vạch nhìn thấy | Tự rà lần lượt trên ảnh gốc trước khi sửa | Lint báo các vị trí này; căn cứ quyết định là vạch thực tế trong ảnh và quy tắc Road v1.0. |
| B05–B08 | camera fisheye bên | Vị trí lane L1/R1 hay `other` | Không có lane trong export hiện tại; không phát sinh lỗi position trong lint | Với camera hai bên, nếu gán lane thì position phải là `other`; lint fisheye hiện không báo lỗi. |

## 4. Phiếu QC 1 nhận được

Bạn kiểm lô của tôi: **chưa ghi nhận phiếu từ bạn kiểm**  Quyết định nhận được: **chưa có**  
Tự kiểm hiện tại: front **12 cảnh báo lint** (đều QC1-02); fisheye **0 cảnh báo lint**. Đây là cảnh báo để tự rà, không tự động đồng nghĩa với lỗi đã xác nhận.

| Mã lỗi | Số cảnh báo | Đồng ý là lỗi? | Đã sửa? |
| --- | ---: | --- | --- |
| QC1-02 thiếu L1/R1 | 12 | Cần rà từng ảnh; chỉ tính lỗi nếu vạch nhìn thấy mà chưa gán | Chưa có revision sửa được ghi nhận |

## 5. Kiểm file export

| File | Mở lại được? | Số shape ảnh 1 (job / file) | Số shape ảnh 2 (job / file) | Tag camera có trong XML? |
| --- | --- | --- | --- | --- |
| `DoanThiAnhHau-front.zip` | Có, lint đọc được | A01: chưa ghi nhận / 9 | A02: chưa ghi nhận / 5 | Có; 16 ảnh đều có đủ bốn tag theo manifest |
| `DoanThiAnhHau-fisheye.zip` | Có, lint đọc được | B01: chưa ghi nhận / 2 | B02: chưa ghi nhận / 3 | Có; 12 ảnh đều có đủ bốn tag theo manifest |

## 6. Ảnh chụp màn hình

Chưa có ảnh chụp CVAT trong workspace. Cần đính kèm các ảnh sau vào bản nộp báo cáo:

1. Tab Labels của project.
2. Một ảnh front đã gán đủ lane, vùng lái, đèn/biển.
3. Một ảnh fisheye đã gán, phóng to đoạn polyline cong.
4. Một đoạn XML có `<polyline label="lane">`.

## 7. Tự đánh giá

Lỗi/cảnh báo xuất hiện nhiều nhất là **QC1-02 — thiếu L1/R1**. Để tránh ở Ngày 20, em sẽ rà mỗi ảnh theo thứ tự L1, R1, rồi mới đến L2/R2; chỉ gán vạch nhìn thấy trên ảnh và phân biệt vạch làn với vạch qua đường. Lint có thể báo thiếu ở ảnh không có vạch, nên cần đọc ảnh trước khi quyết định.

Chưa có lần sửa/revision mới được ghi nhận trong manifest. Nếu bỏ sót một vạch L1/R1 nhìn thấy, model sẽ học rằng ranh giới làn đó không tồn tại; với model hỗ trợ giữ làn, dự đoán ranh giới sai có thể làm vùng làn hoặc quỹ đạo mục tiêu bị lệch. Khi xác nhận và sửa một cảnh báo, em sẽ ghi lại ảnh và revision đã sửa để so sánh.

## 8. (Tùy chọn, buffer) Từ polyline đến đích row-anchor

Đã chạy `rowanchor` trên `DoanThiAnhHau-front.zip`, ảnh A01, position R1.

| y | 720 | 680 | 640 | 600 | 560 |
| --- | ---: | ---: | ---: | ---: | ---: |
| x của em | không có làn | 658.0 | 598.6 | 540.9 | 484.8 |
| x của bạn kia | chưa có số liệu | chưa có số liệu | chưa có số liệu | chưa có số liệu | chưa có số liệu |

1. Nếu điểm cuối gần xe dời lên 40 px (từ khoảng y=719 lên y=679), hàng **y=680** sẽ chuyển thành “không có làn”; y=720 vốn đã ngoài polyline trong kết quả hiện tại.
2. Chưa có số row-anchor của bạn kiểm nên chưa tính được độ lệch tại y=720 và y=560. Khi có hai polyline cùng ảnh/vị trí, lấy trị tuyệt đối hiệu hai giá trị x ở mỗi hàng. Hàng gần xe (y=720) thường quan trọng hơn cho phản hồi LKA theo slide 25.
3. Đảo thứ tự điểm không làm đổi phép nội suy x tại một hàng, nhưng vi phạm quy tắc vẽ gần ra xa. `road_check` có thể bắt lỗi chiều polyline (QC1-04), còn model/tiền xử lý phụ thuộc thứ tự điểm có thể diễn giải sai điểm đầu và điểm cuối.
