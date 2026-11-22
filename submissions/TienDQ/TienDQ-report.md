# Báo cáo cá nhân — Ngày 11
Họ tên: Tien DQ (điền họ tên đầy đủ)    Mã học viên: [điền mã học viên]
Phiên bản CVAT (Help → About): [điền]
Guideline: Road v1.0    Lần nộp: 1
Thời điểm export trên CVAT: [điền]    Số lần nộp lại sau Rework: 0 (nếu đúng)

## 1. Kiểm project
| Mục | Đúng như guideline Road v1.0? | Ghi chú |
| --- | --- | --- |
| 6 label, đúng kiểu | [xác nhận trên CVAT] | File export có các label theo taxonomy. |
| Thuộc tính và giá trị | [xác nhận trên CVAT] | File export đọc được theo CVAT for images 1.1. |
| 4 tag ảnh | Có trong export | Checker đọc đủ tag trên 28/28 ảnh; camera khớp tên file. |
Cách kết thúc polyline trên bản CVAT này: [điền thao tác bạn dùng]
Cách đặt tag ảnh trên bản CVAT này: [điền thao tác bạn dùng]

## 2. Số lượng đã gán
| Task | Ảnh | lane | road_curb | crosswalk | drivable | traffic_light | traffic_sign |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| front | 12 | 26 | 8 | 7 | 27 | 26 | 9 |
| front-extra (đã làm 4 / 4) | 4 | 9 | 0 | 5 | 8 | 6 | 2 |
| fisheye | 8 | 5 | 2 | 7 | 9 | 1 | 1 |
| fisheye-extra (đã làm 4 / 4) | 4 | 0 | 0 | 3 | 1 | 0 | 0 |

## 3. Bảng ca khó
| Ảnh | Nhãn | Phân vân giữa | Đã chọn | Lý do |
| --- | --- | --- | --- | --- |
| A08 | lane (L1) | Có / không có vạch nhìn thấy | Không gán | Coach xác nhận không thấy vạch. |
| [bổ sung nếu có] | | | | |

## 4. Phiếu QC 1 nhận được
Bạn kiểm lô của tôi: [tên bạn kiểm]    Quyết định nhận được: [Release / Hold / Rework]
| Mã lỗi | Số lỗi | Đồng ý? | Đã sửa? |
| --- | --- | --- | --- |
| [điền theo phiếu QC nhận được] | | | |

## 5. Kiểm file export
| File | Mở lại được? | Số shape ảnh 1 (job / file) | Số shape ảnh 2 (job / file) | Tag camera có trong XML? |
| --- | --- | --- | --- | --- |
| TienDQ-front.zip | Có, lint đọc được | [điền job] / 10 (A01) | [điền job] / 8 (A02) | Có |
| TienDQ-fisheye.zip | Có, lint đọc được | [điền job] / 4 (B01) | [điền job] / 2 (B02) | Có |

Ghi chú lint: còn 8 cảnh báo thiếu L1/R1: A05 (L1, R1), A06 (L1, R1), A07 (L1), A08 (L1), A09 (R1), A14 (R1). Coach đã xác nhận ngoại lệ A08; A14 là ảnh thêm. Các cảnh báo ở A05, A06, A07 và A09 đang được bỏ qua theo trao đổi với học viên. B11 là ảnh thêm, hiện không có shape.

## 6. Ảnh chụp màn hình
Cần chèn ảnh chụp thật từ CVAT trước khi nộp:
1. Tab Labels của project.
2. Một ảnh camera trước đã gán đủ (làn, vùng lái, đèn / biển).
3. Một ảnh fisheye đã gán, phóng to đoạn polyline cong.
4. Đoạn XML có <polyline label="lane">.

## 7. Tự đánh giá
Lỗi bạn mắc nhiều nhất hôm nay (theo mã QC1-xx), và cách tránh ở Ngày 20: [tự điền theo Phiếu QC 1 nhận được]
Nhãn của bạn đi vào model ở đâu? Chọn một lỗi đã sửa và nói lỗi đó làm model học sai thế nào: [tự điền ví dụ thực tế]

## 8. (Tùy chọn, buffer) Từ polyline đến đích row-anchor
Bỏ qua nếu không làm hoạt động buffer.
