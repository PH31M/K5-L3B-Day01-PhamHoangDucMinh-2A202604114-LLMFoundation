# Báo cáo cá nhân — Day 01: Lọc tin nhắn rác bằng ML, DL, Embedding và LLM

- **MSSV: 2A202604114**
- **Họ và tên: Phạm Hoàng Đức Minh**
- **SEED: 1617**

## 1. Bằng chứng

| Tệp | Có? |
| --- | --- |
| [`day01_lab.ipynb`](day01_lab.ipynb) — notebook đã chạy, còn output | ☐ |
| [`lab1_report.json`](lab1_report.json) — do ô "Báo cáo cuối" sinh ra | ☐ |
| [`hand_calc.jpg`](hand_calc.jpg) — ảnh tính tay có các bước | ☐ |

## 2. Kết quả chính

                                 precision  recall  F1 (test)  F1 (SUB 40)  \
1. BoW + LogReg (tự code)            1.000   0.860      0.925        0.889   
2. BoW + MLP (deep learning)         0.972   0.972      0.972        0.974   
3a. Encoder (MiniLM) + kNN           0.874   0.972      0.920        1.000   
3b. Encoder (MiniLM) + LogReg        0.981   0.981      0.981        1.000   
3c. Encoder (MiniLM) + MLP head      0.972   0.981      0.977        1.000   
4a. LLM nhỏ zero-shot                1.000   1.000      1.000        1.000   

                                 train (s)  tin/s (cả lô)  p50 ms/tin  \
1. BoW + LogReg (tự code)            5.691      26967.579       0.054   
2. BoW + MLP (deep learning)        16.204      29324.917       0.309   
3a. Encoder (MiniLM) + kNN          72.032         31.647      41.863   
3b. Encoder (MiniLM) + LogReg       72.481         45.142      25.801   
3c. Encoder (MiniLM) + MLP head     72.976         48.752      25.938   
4a. LLM nhỏ zero-shot                0.000          0.976     678.717   

                                 p95 ms/tin  USD / 1k tin  
1. BoW + LogReg (tự code)             0.258         0.000  
2. BoW + MLP (deep learning)          0.546         0.000  
3a. Encoder (MiniLM) + kNN           66.028         0.000  
3b. Encoder (MiniLM) + LogReg        38.347         0.000  
3c. Encoder (MiniLM) + MLP head      34.795         0.000  
4a. LLM nhỏ zero-shot              2968.035         0.023  

## 3. Dự đoán và thực tế

*Chọn 3 dự đoán `predict(...)` lệch nhiều nhất so với kết quả. Mỗi cái: bạn đoán gì, ra gì, vì sao lệch.*

## 4. Phân tích 50 case khó

*Model nào tụt nhiều nhất, ở nhóm case nào? Nêu 2 case cụ thể và cơ chế khiến model sai.*

## 5. Thử thách cá nhân

*Đề theo SEED của bạn, cách làm, kết quả, giải thích.*

## 6. Phương án cho sản phẩm thật

*Với yêu cầu p95 < 50 ms/tin cho 10 triệu SMS/ngày: chọn phương án nào, dẫn số liệu nào, chấp nhận đánh đổi gì.*

## 7. AI log và điều đã học

*Mỗi lần dùng AI: hỏi gì, nhận gì, bạn sửa gì. Sau đó 2–3 câu: điều bạn hiểu ra hôm nay mà trước đó chưa hiểu.*
Lần 1 (Code & Toán): hỏi cách tính số lượng tham số của mạng MLP, hướng vòng lặp training PyTorch.

Lần 2 (Phân tích hiện tượng & Đánh giá): hỏi cách giải thích các hiện tượng trên biểu đồ (overfit, điểm dừng), đánh đổi Pareto, và điểm yếu của từng mô hình (BoW, Embedding, LLM) .

Lần 3 (Tính tay & Tạo case): Mình nhờ AI gợi ý 5 case bẫy mô hình và hướng dẫn giải các câu tính tay (F1, Cosine, chi phí API).
