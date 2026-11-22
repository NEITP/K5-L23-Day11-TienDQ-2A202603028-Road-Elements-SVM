# Báo cáo cá nhân — Ngày 11
Họ tên: Đinh Quốc Tiến    Mã học viên: 2A202603028
Phiên bản CVAT: 2.81.0 (Help → About / API server)
Guideline: Road v1.0    Lần nộp: 1
Thời điểm export: front — 22/11/2026 12:25:27 +07; fisheye — 22/11/2026 12:29:09 +07 (thời gian tệp ZIP). Metadata CVAT ghi job 20 cập nhật lúc 12:18:59 +07 và job 21 lúc 12:28:53 +07.
Số lần nộp lại sau Rework: 0

## 1. Kiểm project
| Mục | Đúng như guideline Road v1.0? | Ghi chú |
| --- | --- | --- |
| 6 label, đúng kiểu | Có | Metadata trong hai export khớp taxonomy Road v1.0. |
| Thuộc tính và giá trị | Có | Label, kiểu hình và thuộc tính trong export khớp cấu hình taxonomy. |
| 4 tag ảnh | Có | Đủ camera, timeofday, weather, source trên 28/28 ảnh; camera khớp tên ảnh. |

## 2. Số lượng đã gán
| Task | Ảnh | lane | road_curb | crosswalk | drivable | traffic_light | traffic_sign |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| front | 12 | 26 | 8 | 7 | 27 | 26 | 9 |
| front-extra (đã làm 4 / 4) | 4 | 9 | 0 | 5 | 8 | 6 | 2 |
| fisheye | 8 | 5 | 2 | 7 | 8 | 5 | 1 |
| fisheye-extra (đã làm 4 / 4) | 4 | 0 | 0 | 3 | 1 | 2 | 0 |

## 3. Bảng ca khó
| Ảnh | Nhãn | Phân vân giữa | Đã chọn | Lý do |
| --- | --- | --- | --- | --- |
| A05 | lane (L1, R1) | Có / không có vạch nhìn thấy | Không gán | Coach xác nhận không thấy vạch. |
| A06 | lane (L1, R1) | Có / không có vạch nhìn thấy | Không gán | Coach xác nhận không thấy vạch. |
| A07 | lane (L1) | Có / không có vạch nhìn thấy | Không gán | Coach xác nhận không thấy vạch. |
| A08 | lane (L1) | Có / không có vạch nhìn thấy | Không gán | Coach xác nhận không thấy vạch. |
| A09 | lane (R1) | Có / không có vạch nhìn thấy | Không gán | Coach xác nhận không thấy vạch. |

Ghi chú: A14 thiếu R1 và B11 chưa có shape là ảnh thêm; không nằm trong 20 ảnh core được chấm tự động.

## 4. Phiếu QC 1 nhận được
Chưa nhận được Phiếu QC 1 từ bạn kiểm; sẽ cập nhật mục này sau.
Bạn kiểm lô của tôi: Chưa có    Quyết định nhận được: Chưa có
| Mã lỗi | Số lỗi | Đồng ý? | Đã sửa? |
| --- | ---: | --- | --- |
| Chưa có phiếu để ghi | — | — | — |

## 5. Kiểm file export
| File | Mở lại được? | Số shape ảnh 1 (job / file) | Số shape ảnh 2 (job / file) | Tag camera có trong XML? |
| --- | --- | --- | --- | --- |
| TienDQ-front.zip | Có | A01: 10 / 10 (job 20) | A02: 8 / 8 (job 20) | Có |
| TienDQ-fisheye.zip | Có | B01: 6 / 6 (job 21) | B02: 4 / 4 (job 21) | Có |

Kiểm tra lint: 28 ảnh, đủ tag và không kèm ảnh. Lint còn 8 cảnh báo QC1-02: A05 (L1, R1), A06 (L1, R1), A07 (L1), A08 (L1), A09 (R1), A14 (R1). Coach đã xác nhận không thấy các vạch được liệt kê ở A05–A09; A14 là ảnh thêm.

## 6. Ảnh chụp màn hình
CVAT cục bộ có hai task độc lập (front và fisheye); không có project Road chứa hai task này. Ảnh bằng chứng được lưu cùng thư mục submission:

1. [Task front và trạng thái job](screenshots/front-task-29.png).
2. [Job front, frame A01 có nhãn](screenshots/front-job-20.png).
3. [Job fisheye, frame B01 có nhãn](screenshots/fisheye-job-21.png).
4. Đoạn XML mẫu được lưu tại [TienDQ-lane-xml-excerpt.xml](TienDQ-lane-xml-excerpt.xml).

## 7. Tự đánh giá
Lỗi đáng chú ý khi rà bản trước là position các vạch ở A01 bị đảo giữa L1/L2 và R1/R2; bản export hiện tại đã sửa. Để tránh lặp lại ở Ngày 20, kiểm tra thứ tự trái–phải của các vạch và đối chiếu với vùng direct trước khi lưu thuộc tính position.
Nếu nhãn position bị đảo, mô hình học phân loại làn sẽ gắn nhầm vạch sát xe với vạch làn kế tiếp. Model hỗ trợ giữ làn có thể chọn sai ranh giới làm mục tiêu, dẫn đến hướng điều khiển không phù hợp.

## 8. (Tùy chọn, buffer) Từ polyline đến đích row-anchor
Không thực hiện hoạt động buffer.
