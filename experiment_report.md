# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600484
**Name:** Nguyễn Thanh Bình
**Date:** 15/04/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | "Based on my data, the best choice is Laptop at $1200." | 9 | Chính xác - Laptop là sản phẩm electronics có giá hợp lý nhất |
| Garbage Data (`garbage_data.csv`) | "Based on my data, the best choice is Nuclear Reactor at $999999." | 2 | Sai - Agent chọn extreme outlier thay vì sản phẩm thực tế |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent trả lời sai vì garbage_data.csv chứa nhiều lỗi dữ liệu:

1. **Duplicate IDs (ID=1):** Có 2 sản phẩm với ID giống nhau (Laptop và Banana) gây nhầm lẫn
2. **Wrong Data Types ("ten dollars"):** Cột price chứa text thay vì số, khiến agent không thể so sánh giá chính xác
3. **Extreme Outliers (Nuclear Reactor - $999999):** Giá cao kỳ lạ này được chọn vì logic max price, nhưng không phải sản phẩm hợp lý
4. **Null Values (None):** Có records không đầy đủ thông tin gây lỗi xử lý
5. **Invalid Categories (None):** Thiếu thông tin phân loại dữ liệu

Các lỗi này khiến agent không thể trích xuất thông tin chính xác, dẫn đến đưa ra đề xuất sai lệch hoàn toàn không có giá trị kinh tế.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** ✅ **Đồng ý hoàn toàn**

Bài thí nghiệm này chứng minh rằng **chất lượng dữ liệu** là yếu tố quan trọng hơn **chất lượng prompt**. Ngay cả với cùng một câu hỏi, khi dữ liệu bị "nhiễm bẩn", agent sẽ đưa ra quyết định sai hoàn toàn. Vì vậy, trong việc xây dựng hệ thống AI/RAG, **data validation và data cleaning là bước không thể bỏ qua**. Pipeline ETL tốt giúp đảm bảo agent nhận được dữ liệu sạch, từ đó có khả năng đưa ra quyết định chính xác và đáng tin cậy.
