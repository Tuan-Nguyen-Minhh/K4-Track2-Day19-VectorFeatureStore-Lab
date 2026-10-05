# Reflection — Lab 19

**Tên:** _<Họ Tên — ĐIỀN TÊN TRƯỚC KHI PUSH>_
**Cohort:** _A20-K4_
**Path đã chạy:** _lite_

---

## Câu hỏi (≤ 200 chữ)

> Trên golden set 50 queries, mode nào thắng ở loại query nào (`exact` /
> `paraphrase` / `mixed`), và tại sao? Khi nào bạn **không** dùng hybrid
> (i.e. khi nào pure BM25 hoặc pure vector là lựa chọn đúng)?

_Answer here._
Đo được trên golden set 50 queries: exact kw 96.7/sem 88.7/hyb 96.7; paraphrase kw 33.3/sem 24.0/hyb 32.0; mixed kw 97.0/sem 98.5/hyb 100.0. Exact: BM25 thắng nhờ khớp từ kỹ thuật nguyên văn, hybrid ngang bằng vì tín hiệu keyword áp đảo trong RRF. Paraphrase: cả hai đều yếu do bge-small-en huấn luyện tiếng Anh kém với diễn đạt lại tiếng Việt — hybrid không cứu được khi cả hai nguồn đều yếu. Mixed: hybrid thắng rõ vì RRF cộng hưởng tài liệu đứng cao ở cả hai danh sách. Không dùng hybrid khi: tra cứu mã/ID cần khớp chính xác tuyệt đối (BM25 rẻ hơn, P99 ~2ms so với ~16ms); query thuần ngôn ngữ tự nhiên và có model embedding đúng ngôn ngữ; corpus nhỏ hoặc ngân sách latency chặt mà lợi hybrid không đáng chi phí depth-50.

---

## Điều ngạc nhiên nhất khi làm lab này

_(Optional, 1–2 câu)_
Ngạc nhiên nhất: cell NB3 tự spawn một uvicorn mồ côi tranh CPU với server chính làm P99 phồng từ 16ms lên ~76ms; và WSL ghi qua /mnt/c khiến setup mất ~40 phút thay vì ~60 giây như tài liệu.

---

## Bonus challenge

- [ ] Đã làm bonus (xem `bonus/`)
- [ ] Pair work với: _<tên đồng đội nếu có>_
