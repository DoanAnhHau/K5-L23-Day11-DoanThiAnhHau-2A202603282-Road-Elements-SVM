# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): **Đoàn Thị Ánh Hậu - 2A202603282**  Người kiểm (tự kiểm): **Phạm Thị Lương - 2A202603302**  
Ngày: **20/11/2026**  Phiên bản guideline: **Road v1.0**  
File được kiểm: **`D:\Lab\DAY11\K5-L23-Day11-DoanThiAnhHau-2A202603282-Road-Elements-SVM\DoanThiAnhHau-manifest.json`**  
Số ảnh kiểm: **6 (A01–A06)** (+ **0** ảnh thêm)  Số nhãn trong phạm vi: **75 (51 shape + 24 tag)**

## Tổng hợp theo mã

Số mục là số nhãn thuộc phạm vi rà soát. Lỗi chính được tính trên 75 nhãn (shape + tag) trong sáu ảnh.

| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 6 ảnh | 0  | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 6 ảnh | 0  | nặng |
| QC1-03 position | sai thuộc tính / thừa | 16 lane | 0  | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 16 lane | 0  | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 16 lane | **3 lỗi**: A03 L2, A04 R2, A04 L1 có nhiều polyline cùng position | chính |
| QC1-06 style, color, kind | sai thuộc tính | 16 lane | 0  | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 6 ảnh | 0  | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 8 traffic light | 0  | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 9 traffic sign | 0  | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 9 traffic sign | 0 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | Không áp dụng | Không áp dụng — ảnh front | chính |
| QC1-12 file | lỗi file | 1 ZIP | 1 lỗi nhẹ: điểm lặp liên tiếp ở A06 drivable#8 | nhẹ / nặng |

## Danh sách lỗi (mỗi lỗi một dòng)

| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| ---: | --- | --- | --- | --- | --- |
| 1 | QC1-05 | A03 | lane, position L2 | chính | Có 2 polyline cùng position L2. Rà và gộp nếu là các đoạn của cùng vạch đứt. |
| 2 | QC1-05 | A04 | lane, position R2 | chính | Có 2 polyline cùng position R2. Rà và gộp nếu là các đoạn của cùng vạch đứt. |
| 3 | QC1-05 | A04 | lane, position L1 | chính | Có 2 polyline cùng position L1. Rà và gộp nếu là các đoạn của cùng vạch đứt. |
| 4 | QC1-12 | A06 | drivable#8, điểm (253,629) | nhẹ | Có một điểm lặp liền nhau; xóa điểm thừa. |

## Ca mơ hồ

| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| A05, A06 | Lint báo thiếu L1/R1. Ảnh có vạch dọc làn nhìn thấy để gán không? | Tự rà ảnh gốc: không thấy vạch dọc làn; bỏ qua cảnh báo QC1-02. |
| A03, A04 | Các polyline trùng position có phải các đoạn của cùng vạch đứt không? | Theo quy tắc Road v1.0, vạch đứt cần là một polyline; ghi nhận 3 mục QC1-05 để sửa. |

## Quyết định

Lỗi nặng: **0**  Lỗi chính: **3 / 75 nhãn = 4%**  Lỗi nhẹ: **1**  Ca chờ lead: **0**  
Quyết định (Release / Hold / Rework): **Release**  
Lý do (theo luật của phiếu): **Không có lỗi nặng; tỷ lệ lỗi chính 4%, không vượt ngưỡng 5%; cảnh báo thiếu L1/R1 ở A05/A06 được bỏ qua sau khi tự rà ảnh và không thấy vạch dọc làn. Điểm lặp A06 là lỗi nhẹ.**

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. Ba loại này theo cách chia lỗi gán nhãn của ISO/IEC 5259-4 (mục 8.4.2); “sai thuộc tính” và “lỗi file” là khóa học thêm. Cách xếp mức: [thang mức lỗi](docs/qc_severity_road_v1.0.md).
