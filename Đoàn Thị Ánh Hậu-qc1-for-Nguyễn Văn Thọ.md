# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): Nguyễn Văn Thọ 2A202603299     
Người kiểm (học viên): Đoàn Thị Ánh Hậu 2A202603282
Ngày: 2026-11-21                          Phiên bản guideline: Road v1.0
File được kiểm (tên + `revision` trong manifest): NguyenVanTho-front.zip, NguyenVanTho-fisheye.zip, revision 1
Số ảnh kiểm: 6 (+ 22 ảnh thêm, ghi riêng)   Số nhãn đã kiểm (shape + tag): 306

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 28 | 0 | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 16 | 0 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 48 | 2 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 48 | 1 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 48 | 1 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 48 | 1 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 52 | 8 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 30 | 2 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 24 | 3 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 24 | 1 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 56 | 1 | chính |
| QC1-12 file | lỗi file | 2 | 0 | nhẹ / nặng |

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
| 1 | QC1-03 | A04 | lane L2 @(1280,537) | nặng | Vạch trắng mép phải đang để L2, phải là R2 |
| 2 | QC1-03 | A09 | lane R1 @(523,666) | nặng | Vạch đứt sát trái làn phải là L1, hiện đang R1 |
| 3 | QC1-06 | A03 | lane L1 | chính | Vạch vàng đôi, kind đang single, phải là double |
| 4 | QC1-09 | A06 | traffic_sign @(659,211) | chính | Biển ONE WAY để information, phải là mandatory |
| 5 | QC1-09 | A06 | traffic_sign @(853,320) | chính | Biển thoi vàng để prohibitory, phải là warning |
| 6 | QC1-09 | A08 | traffic_sign @(752,60) | chính | Biển xanh để prohibitory, phải là information |
| 7 | QC1-07 | A09 | drivable alternative | chính | Làn xanh có xe đi ngược, không phải cùng chiều |
| 8 | QC1-07 | A13 | drivable direct | chính | Vùng lái cụt ở đuôi xe, phía xa chưa phủ |
| 9 | QC1-05 | A13 | lane L1, R1 | chính | Vạch dừng trước xe, không nối qua chỗ che, thiếu occluded |
| 10 | QC1-07 | A14 | drivable direct | chính | Chỉ có dải sát capo, phần đường xa chưa gán |
| 11 | QC1-07 | A16 | drivable direct | chính | Direct nằm ở làn trái, làn đang đi không có vùng lái |
| 12 | QC1-04 | A16 | lane R1 @(983,547) | chính | Polyline cắt chéo làn, không nằm trên vạch trắng |
| 13 | QC1-07 | B01 | drivable direct | chính | Chỉ một dải ngắn sau vạch ngựa, đường trước chưa phủ |
| 14 | QC1-08 | B02 | traffic_light | chính | Cụm đèn bên phải (xe + người đi bộ) chưa có hộp |
| 15 | QC1-10 | B04 | traffic_sign | chính | Biển cấm đi vào sát mép phải chưa gán |
| 16 | QC1-08 | B04 | traffic_light | chính | Đèn đỏ trên cùng cột với biển chưa gán |
| 17 | QC1-07 | B09 | drivable direct | chính | Direct không phủ làn phía trước |
| 18 | QC1-07 | B10 | drivable | chính | Vùng xanh tràn lên vỉa hè gạch |
| 19 | QC1-11 | B10 | crosswalk | chính | Nền gạch xương cá không phải vạch người đi bộ, xóa |
| 20 | QC1-07 | B12 | drivable | chính | Khoảng mặt đường giữa các vạch ngựa bị bỏ trống |

## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| A05 | Không có vạch sơn, chỉ có drivable. Thiếu L1/R1 được miễn? | Được miễn (QC1-02 waiver) |
| B11 | Không gán vạch ô đỗ thành lane. Đúng bẫy QC1-03? | Đúng, không tính lỗi |

## Quyết định
Lỗi nặng: **2**   Lỗi chính: **18** / 306 nhãn = **5,9%**   Lỗi nhẹ: **7**   Ca chờ lead: 0
Quyết định (Release / Hold / Rework): **Rework**
Lý do (theo luật của phiếu): Một lỗi nặng là đủ để trả về. Tỉ lệ lỗi chính cũng vượt ngưỡng 5%.

### Lỗi nhẹ (không đổi quyết định)
- A10: một biển và một đèn bị vẽ trùng đúng cùng hộp. Mặt đường ướt, weather đang overcast — đổi rain.
- A11: crosswalk và drivable bị nhân đôi từng cái.
- A14, B05, B08, B10: trời quang nhưng weather=other. Đổi clear. other chỉ dùng cho tuyết hoặc ca không xếp được.
