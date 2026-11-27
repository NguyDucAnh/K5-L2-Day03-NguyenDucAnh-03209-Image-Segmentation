# Báo cáo thực hành Day 3 — cần bổ sung thông tin cá nhân

**Lưu ý:** Các trạng thái ZIP bên dưới được điền sau khi kiểm tra thư mục `submissions/`. Những mục đánh dấu `[bạn bổ sung]` cần bạn tự xác nhận từ quá trình làm bài; không thể suy ra đáng tin cậy chỉ từ ZIP.

- Mã học viên theo lớp: 2A202603209
- Ngày / CVAT local: 12/11/2026
- Công cụ đã dùng: CVAT (xác nhận bạn đã dùng công cụ này trước khi nộp)

Mã học viên là mã lớp cấp; không cần ghi họ tên trong report nếu kênh [LMS](https://aithucchien.vinuni.edu.vn) đã nhận diện bạn. Chỉ ghi công cụ thật sự đã dùng; không có SAM vẫn làm bài bình thường.

## 1. Bài đã nộp

Ghi tên ZIP đúng như file trong `submissions/` và số ảnh đã vẽ, Save. Chưa làm hoặc export lỗi thì ghi `chưa có`, không tạo ZIP rỗng. Cột điểm là điểm tối đa của task, **không phải điểm tự chấm**.

| Task | File ZIP đúng tên | Hoàn thành mấy ảnh | Điểm tối đa (coach chấm sau) |
| --- | --- | ---: | ---: |
| easy_semantic | `easy_semantic.zip` | 3 / 3 | 20 |
| medium_instance | `medium_instance.zip` | 3  / 3 | 32 |
| hard_panoptic | `hard_panoptic.zip` | 1 / 2 | 30 |
| cp1_holes | chưa có | 0 / 1 (chưa có ZIP) | 3 |
| cp2_slice | chưa có | 0 / 1 (chưa có ZIP) | 3 |
| cp5_occlusion | chưa có | 0 / 1 (chưa có ZIP) | 3 |
| cp3_thin | chưa có | 0 / 1 (chưa có ZIP) | 3 |
| cp4_curb | chưa có | 0 / 1 (chưa có ZIP) | 3 |
| cp6_coverage | chưa có | 0 / 1 (chưa có ZIP) | 3 |
| **Tổng tối đa** | | | **100** |

Nếu export lỗi, ghi task, dữ liệu đã Save đến đâu và lỗi đã báo coach.

## 2. Một quyết định trước khi dùng gợi ý

> **Cần xác nhận và thay các phần trong ngoặc vuông bằng trải nghiệm thật trước khi nộp.** Không dùng ví dụ này như lời xác nhận rằng tôi đã quan sát/vẽ đúng vị trí đó.

- Ảnh, vị trí và object Medium đầu tiên tự vẽ: `[ghi tên ảnh và vị trí; ví dụ: xe ở gần mép trái ảnh]`.
- Class và quy tắc tôi dùng để chọn biên: `[nếu đúng là ô tô, ghi class car; vẽ phần thân xe nhìn thấy, theo đường viền nhìn thấy và không đoán phần bị che]`.
- Nếu dùng gợi ý sau đó: `[ghi vùng gợi ý sai/đúng và cách xử lý; nếu không dùng gợi ý, ghi “không dùng”]`.

## 3. Một lỗi tôi tìm thấy và sửa

> **Cần ghi lỗi bạn thực sự nhìn thấy và sửa trong CVAT.** Ví dụ dưới đây chỉ là gợi ý để nhận diện lỗi; hãy xóa hoặc sửa nếu không đúng với bài của tôi.

- Task/ảnh/vùng: `[ghi task và ảnh; ví dụ cp2_slice, hai xe đứng sát nhau]`.
- Lỗi thuộc loại: `[ví dụ: hai xe cùng class bị gộp thành một instance]`.
- Bằng chứng tôi nhìn thấy: `[mô tả đường ranh giữa hai xe và mask/object trong danh sách Objects]`.
- Quy tắc và hành động sửa: `[theo quy tắc cp2_slice, tách hai xe thành hai mask riêng; chỉ giữ phần nhìn thấy của mỗi xe]`.
- Sau sửa đã Save và export lại chưa? `[chỉ ghi Có sau khi đã thực hiện; nếu chưa, ghi Chưa]`.

Nếu đã xem Summary tự đánh giá trên GitHub Actions hoặc tự chạy script, ghi kết quả thật liên quan lỗi vừa sửa: `[chưa có điểm / ghi metric trước và sau nếu đã chạy]`. Scorecard ba tier tối đa **82**, không phải điểm cuối trên 100. Không tự ghi PASS/top 3/bonus; người phụ trách xác nhận theo tiêu chí lớp. Không đưa file ground truth vào fork.

## 4. Ba ca chưa chắc hoặc đã cân nhắc

> **Các dòng dưới là gợi ý theo quy tắc task, không khẳng định tôi đã gặp đúng các tình huống này.** Giữ lại những dòng phù hợp với ảnh bạn đã xem, rồi bổ sung tên ảnh/vị trí và quyết định thật; thay dòng không phù hợp bằng trường hợp bạn thực sự cân nhắc.

| Ảnh/vị trí — cần xác nhận | Hai cách hiểu có thể | Quy tắc/chứng cứ để kiểm tra | Quyết định thật của tôi / câu hỏi cho coach |
| --- | --- | --- | --- |
| `[cp1_holes: ghi ảnh/vùng nếu đã làm]` | Kính/khe cửa sổ có thể bị khoét khỏi mask, hoặc nằm bên trong phần mask của vật. | Quy tắc cp1_holes: cửa sổ/khe giữ bên trong mask, không khoét tùy tiện. | `[ghi lựa chọn sau khi kiểm tra mask; nếu chưa làm checkpoint, thay dòng này]` |
| `[cp2_slice: ghi ảnh/vùng nếu đã làm]` | Hai xe cùng class đứng sát nhau có thể bị xem là một vùng, hoặc là hai instance riêng. | Quy tắc cp2_slice: mỗi xe là một instance riêng; kiểm tra đường biên và số object. | `[ghi quyết định sau khi xem ảnh/CVAT; nếu chưa làm checkpoint, thay dòng này]` |
| `[cp4_curb: ghi ảnh/vùng nếu đã làm]` | Vùng sát lề có thể là road hoặc sidewalk khi màu/vật liệu gần giống nhau. | Quy tắc cp4_curb: phân ranh theo chức năng và bó vỉa, không chỉ theo màu. | `[ghi dấu hiệu quan sát được và quyết định; nếu chưa làm checkpoint, thay dòng này]` |
