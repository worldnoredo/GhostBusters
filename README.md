# GhostBusters

1. Question 1: Exact Inference Observation
- Xác định ước tính vị trí của Ghost qua noisyDistance, nếu không có (None) thì coi như ma đang bị nhốt ở phòng giam (jeil) với độ tin tưởng =1
- Trong trường hợp xác định được vị trí ước tính của Ghost:
  + Với mỗi vị trí khả thi của Ghost, ta sẽ tính toán lại độ tin tưởng Ghost ở đó bằng cách nhân thêm với xác suất mà ghost đi đến đó từ vị trí ta cảm nhận được
  + Cập nhật lại xác suất bằng hàm normalize()

  
2. Question 2: Exact Inference with Time Elapse
- Với mỗi vị trí khả thi của Ghost, tính xác suất Ghost di chuyển đến ô tiếp theo
- Cách tính:
  + Xét mỗi vị trí khả thi của Ghost
  + Lấy ra vị trí và xác suất đi đến vị trí đó của Ghost
  + Độ tin tưởng tại vị trí đó là tổng tất cả của tích độ tin tưởng khởi tạo ban đầu (1) nhân với xác suất trên
  + cập nhật lại xác suất với normalize()
3. Exact Inference Full Test
- 
