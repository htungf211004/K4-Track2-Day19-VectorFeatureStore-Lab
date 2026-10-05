# Reflection — Lab 19

**Tên:** Trịnh Hoàng Tùng
**Cohort:** 4
**Path đã chạy:** Lite

---

## Câu hỏi (≤ 200 chữ)

> Trên golden set 50 queries, mode nào thắng ở loại query nào (`exact` /
> `paraphrase` / `mixed`), và tại sao? Khi nào bạn **không** dùng hybrid
> (i.e. khi nào pure BM25 hoặc pure vector là lựa chọn đúng)?

Trên 50 queries, Precision@10 trung bình của hybrid đạt 78,6%, cao hơn BM25 (77,8%) và vector (73,2%). Với `exact`, BM25 và hybrid cùng đạt 96,7% vì query chứa thuật ngữ khớp trực tiếp tài liệu. Với `mixed`, hybrid đạt 100%, so với vector 98,5% và BM25 97,0%: RRF kết hợp thứ hạng từ hai nguồn, tận dụng cả từ khóa và ngữ nghĩa.

Với `paraphrase`, BM25 đạt 33,3%, hybrid 32,0%, vector 24,0%. Kết quả cho thấy vector không mặc nhiên tốt hơn khi diễn đạt lại: mô hình bge-small thiên về tiếng Anh nên còn yếu với tiếng Việt. Tôi sẽ đánh giá thêm mô hình đa ngôn ngữ trước khi chọn cho dữ liệu thực tế.

Tôi chọn pure BM25 khi cần khớp mã lỗi, tên sản phẩm hoặc thuật ngữ chính xác và ưu tiên độ trễ thấp. Pure vector phù hợp khi query diễn đạt linh hoạt, mô hình embedding phù hợp ngôn ngữ và kiểm thử xác nhận chất lượng. Hybrid hữu ích cho query hỗn hợp, nhưng cần cân nhắc chi phí và độ trễ của hai bộ tìm kiếm.

---

## Điều ngạc nhiên nhất khi làm lab này

Ngưỡng cache 0,75 vẫn gây 36% trả lời sai; tôi cần đo cả false-hit thay vì chỉ nhìn tỷ lệ tiết kiệm.

---

## Bonus challenge

- [ ] Đã làm bonus (xem `bonus/`)
- [ ] Pair work với: _<tên đồng đội nếu có>_
