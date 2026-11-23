# Báo cáo pha 2: trước và sau

Khung của P2-05. Mỗi con số dẫn về một lượt chạy Kaggle cụ thể, mỗi cải tiến dẫn về một ADR đã duyệt. Ô nào chưa có thì ghi "chưa đo" hoặc "chưa có" và lý do.

## 1. Cách đo

- Phần cứng, phần mềm, cấu hình: theo [giao-thuc-do.md](giao-thuc-do.md), protocol `sa-bank-phase2-kaggle-v2`.
- k6, Node và Postgres chạy chung 4 vCPU trên một notebook. Số tuyệt đối thấp hơn khi tách máy, nhưng trước và sau so sánh được vì cùng cách chạy.
- Các lượt đo:

| Lượt | Commit | Ngày | Notebook Kaggle | Bảng |
| --- | --- | --- | --- | --- |
| Baseline v2 | chưa đo | | | [phase2-baseline.md](../performance/phase2-baseline.md) |
| Sau P2-02 | chưa đo, chờ P2-02 | | | |
| Sau P2-03 | chưa đo, chờ P2-03 | | | |
| `main` có cả hai | chưa đo, chờ P2-02 và P2-03 merge | | | |

## 2. Vấn đề 1: tranh chấp ghi trên tài khoản nóng (P2-02)

- Vấn đề và số trước: chưa có, lấy ô `debit` và `debit_spread` từ baseline v2.
- Phương án và ADR: chưa có.
- Số sau: chưa đo.
- Vì sao khác biệt: chưa có.
- Đánh đổi chấp nhận: chưa có.

## 3. Vấn đề 2: tải đăng nhập (P2-03)

- Vấn đề và số trước: chưa có, lấy ô `login` và `mixed` từ baseline v2.
- Phương án và ADR: chưa có.
- Số sau: chưa đo.
- Vì sao khác biệt: chưa có.
- Đánh đổi chấp nhận: chưa có.

## 4. Giám sát (P2-04)

Không đổi hiệu năng. Ghi endpoint `live` và `ready`, healthcheck của Dockerfile, bằng chứng CI. Chưa có.

## 5. Khi có cả hai cải tiến

Hai cải tiến cùng tranh 4 vCPU nên có thể ảnh hưởng nhau. So `main` có cả hai với từng nhánh riêng. Chưa đo.

## 6. Tính đúng của tiền

Đối soát số dư và sổ cái, bài rút vượt số dư, ở mọi lượt trên. Chưa đo.

## 7. Còn lại và hướng tiếp

Chưa có.
