
### BÀI TẬP: LỰA CHỌN GIẢI PHÁP ZERO-SHOT VS FEW-SHOT

#### 1. Thiết kế Prompt

  **Phương án 1 (Zero-shot - Chỉ nêu quy tắc):**
    
  - Phân loại tin nhắn sau thành: tích cực (khen ngon, rẻ), tiêu cực (chê giao chậm, thái độ tệ), cần hỗ trợ (hỏi địa chỉ, giá). Chỉ trả về tên nhóm. Tin nhắn: "Quán phục vụ chu đáo quá, bắt khách đợi hẳn 1 tiếng"
    
  **Phương án 2 (Few-shot - Có ví dụ mẫu):**
    
  - Phân loại tin nhắn thành 3 nhóm: tích cực, tiêu cực (bao gồm cả mỉa mai), cần hỗ trợ. _Ví dụ 1:_ "Trà sữa rất ngon, giá tốt" - tích cực_Ví dụ 2:_ "Quán phục vụ chu đáo quá, bắt khách đợi hẳn 1 tiếng" - tiêu cực _Ví dụ 3:_ "Shop cho mình xin địa chỉ nhé." -cần hỗ trợ Tin nhắn cần phân loại: "Quán phục vụ chu đáo quá, bắt khách đợi hẳn 1 tiếng"
    

#### 2. Bảng so sánh Trade-off
|Tiêu chí|Giải pháp 1 (Zero-shot)  |Giải pháp 2 (Few-shot)
|--|--|--|
|Độ dễ hiểu & Triển khai  |Cao, viết nhanh, đơn giản  |Trung bình, mất công soạn ví dụ
|Chi phí (Token) |Ít tốn token |Tốn nhiều token hơn
|Xử lý câu mỉa mai|Kém, dễ bị lừa bởi từ ngữ bề nổi|Tốt, AI học được ngữ cảnh qua mẫu
#### 3. Kết quả thử nghiệm thực tế

-   **Zero-shot:** Cho kết quả là **`tích cực`** (AI bị sập bẫy từ "chu đáo quá" do thiếu ví dụ hướng dẫn).
    
-   **Few-shot:** Cho kết quả chính xác là **`tiêu cực`** (AI nhận diện được ý mỉa mai nhờ có ví dụ mẫu tương tự).
