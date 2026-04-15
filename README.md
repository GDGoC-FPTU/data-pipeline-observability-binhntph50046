# Day 10 Lab: Data Pipeline & Data Observability

**Student ID:** 2A202600484
**Name:** Nguyễn Thanh Bình

---

## Mo ta

Bài lab này xây dựng một ETL Pipeline hoàn chỉnh để xử lý dữ liệu từ tệp JSON, thực hiện validation, transform dữ liệu thành CSV. Ngoài ra, thực hiện stress test để đánh giá tác động của dữ liệu không sạch đến kết quả của AI Agent.

**Công việc đã hoàn thành:**
- ✅ Extract: Đọc dữ liệu từ raw_data.json
- ✅ Validate: Loại bỏ records có giá <= 0 hoặc category rỗng
- ✅ Transform: Tính discounted_price (giảm 10%), chuẩn hóa category (Title Case), thêm timestamp
- ✅ Load: Lưu kết quả vào processed_data.csv
- ✅ Stress Test: So sánh kết quả agent với clean data vs garbage data

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas pytest
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
python generate_garbage.py   # Create garbage data
python agent_simulation.py   # Run agent with clean and garbage data
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

### ETL Pipeline:
- **Input:** 5 records từ raw_data.json
- **Valid Records:** 3 records (loại bỏ 2 records lỗi)
- **Output:** processed_data.csv với các cột: id, product, price, category, discounted_price, processed_at

### Stress Test Results:
- **Clean Data Query:** "What is the best electronic product?"
  - **Agent Response:** "Based on my data, the best choice is Laptop at $1200."
  - **Accuracy:** 9/10 (Chính xác - Laptop là sản phẩm electronics tốt nhất)

- **Garbage Data Query:** "What is the best electronic product?"
  - **Agent Response:** "Based on my data, the best choice is Nuclear Reactor at $999999."
  - **Accuracy:** 2/10 (Sai - Nuclear Reactor là outlier, không phải lựa chọn tốt)
# Day 10 Lab: Data Pipeline & Data Observability

**Student ID:** 2A202600484
**Name:** Nguyễn Thanh Bình

---

## Mo ta

Bài lab này xây dựng một ETL Pipeline hoàn chỉnh để xử lý dữ liệu từ tệp JSON, thực hiện validation, transform dữ liệu thành CSV. Ngoài ra, thực hiện stress test để đánh giá tác động của dữ liệu không sạch đến kết quả của AI Agent.

**Công việc đã hoàn thành:**
- ✅ Extract: Đọc dữ liệu từ raw_data.json
- ✅ Validate: Loại bỏ records có giá <= 0 hoặc category rỗng
- ✅ Transform: Tính discounted_price (giảm 10%), chuẩn hóa category (Title Case), thêm timestamp
- ✅ Load: Lưu kết quả vào processed_data.csv
- ✅ Stress Test: So sánh kết quả agent với clean data vs garbage data

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

python generate_garbage.py   # Tạo garbage data
python agent_simulation.py   # Chạy agent với clean và g
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
# Mo ta cach ban chay thi nghiem Clean vs Garbage data
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua
### ETL Pipeline:
- **Input:** 5 records từ raw_data.json
- **Valid Records:** 3 records (loại bỏ 2 records lỗi)
- **Output:** processed_data.csv với các cột: id, product, price, category, discounted_price, processed_at

### Stress Test Results:
- **Clean Data Query:** "What is the best electronic product?"
  - **Agent Response:** "Based on my data, the best choice is Laptop at $1200."
  - **Accuracy:** 9/10 (Chính xác - Laptop là sản phẩm electronics tốt nhất)

- **Garbage Data Query:** "What is the best electronic product?"
  - **Agent Response:** "Based on my data, the best choice is Nuclear Reactor at $999999."
  - **Accuracy:** 2/10 (Sai - Nuclear Reactor là outlier, không phải lựa chọn tốt
(Tom tat ket qua: bao nhieu records da xu ly, bao nhieu bi loai, v.v.)
