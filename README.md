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
- Duyệt các action hợp lệ, lấy vị trí của trạng thái kế tiếp, duyệt vị trí của ma livingGhostPositionDistributions, lấy vị trí của ma có khả năng cao nhất, tính khoảng cách nếu vị trí đó khác 0, cập nhật giá trị value cho action đó.
4. Approximate Inference Observation
- Hàm initializeUniformly(self, gameState): liệt kê các vị trí của con ma có thể có
- Hàm observe(self, observation, gameState):
  + Nếu noisyDistance là none => cập nhật vị trí particle là vị trí ma bị ăn.
  + Nếu không => cập nhật belief giống như đã implement trong class exactInference.
5. Approximate Inference with Time Elapse
- Tương tự Q3. Lấy tất cả các vị trí của ma, lấy mẫu vị trí cho 1 số particle.
6. Joint Particle Filter Observation
- Hàm initializeParticles(self): liệt kê tất cả những vị trí hợp lệ rồi tráo.
- Hàm getBeliefDistribution(self): cộng tất cả giá trị giống nhau trong chuỗi particles thành chuỗi beliefs
- Hàm observeState(self, gameState): Xét trường hợp số noisyDistances < số ma: thực hiện vòng lặp với mỗi particleIndex trong range(self.numParticles), duyệt ma trong range(self.numGhosts):
  + Nếu noisyDistance là none, thì ma sẽ xuất hiện trong ô tù
  + Nếu không cập nhật lại belief cho mỗi ma.
7. Joint Particle Filter with Elapse Time
- Lấy phân bố vị trí cho, thêm newParticle mẫu lấy từ phân bố vị trí đó.
