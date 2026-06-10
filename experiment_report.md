# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-665
**Name:** Michael Jackson
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | "Based on my data, the best choice is Laptop at $1200." | 10 | Agent chon dung san pham electronics hop ly nhat. |
| Garbage Data (`garbage_data.csv`) | "Based on my data, the best choice is Nuclear Reactor at $999999." | 1 | Agent bi danh lung boi outlier va du lieu nhiem. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent tra loi sai vi du lieu garbage chua nhieu van de ve chat luong du lieu. Dau tien, co duplicate ID (id=1 xuat hien 2 lan: Laptop va Banana) gay nhieu cho qua trinh xu ly. Thu hai, truong "price" cua "Broken Chair" la chuoi "ten dollars" thay vi so, gay ra loi kieu du lieu. Quan trong nhat la su xuat hien cua outlier cuc dai "Nuclear Reactor" voi gia 999999, lam cho Agent chon no thay vi san pham hop ly. Ngoai ra, con co null values (id=None, price=0, category=None) khong duoc loc bo, lam sai lech ket qua phan tich. Tat ca nhung van de nay cho thay du lieu "rac" truc tiep gay nhieu cho Agent AI, khien no khong the dua ra cau tra loi chinh xac.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Mot prompt tot nhung du lieu dau vao kem se luon cho ra ket qua sai. Trong thi nghiem nay, Agent su dung cung mot logic nhung garbage data khien no chon "Nuclear Reactor" thay vi "Laptop". Dieu nay chung minh rang quality data quan trong hon quality prompt vi prompt tot nhat cung khong the bu duoc du lieu xau.
