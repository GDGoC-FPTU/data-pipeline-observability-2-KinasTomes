[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24113216&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** 2A202600665@vinuni.edu.vn
**Name:** Trinh Quang Hung

---

## Mo ta

Bai lab xay dung mot ETL pipeline co ban: doc du lieu tu raw_data.json, kiem tra va loai bo records khong hop le (gia <= 0, category rong), chuan hoa category thanh Title Case, tinh discounted_price (giam 10%), them timestamp, va xuat ra file processed_data.csv. Sau do thuc hien stress test voi agent_simulation.py de so sanh tac dong cua du lieu sach vs du lieu rac len AI Agent.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
# Buoc 1: Tao du lieu rac
python generate_garbage.py

# Buoc 2: Chay ETL de tao du lieu sach
python solution.py

# Buoc 3: Chay Agent Simulation voi ca 2 bo du lieu
python agent_simulation.py
```

---

## Cau truc thu muc

```
solution.py              # ETL Pipeline script
processed_data.csv       # Output cua pipeline (3 records hop le)
garbage_data.csv         # Du lieu rac cho stress test
experiment_report.md     # Bao cao thi nghiem
README.md                # File nay
```

---

## Ket qua

- Tong records doc duoc: 5 records tu raw_data.json
- So records hop le: 3 (Laptop, Chair, Monitor)
- So records bi loai: 2 (Mystery Box - gia am; Phone - category rong)
- Clean Data test: Agent tra loi dung, chon Laptop voi gia $1200
- Garbage Data test: Agent bi danh lung, chon Nuclear Reactor voi gia $999999 (outlier)
