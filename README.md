
## I. Bài tập cơ bản  
**Các Test case:**  
* Thêm sinh viên, các sinh viên được thêm xắp sếp theo thứ tự của MSSV    
* Tìm và in ra các sinh viên có cùng ngày sinh.   
* Tìm và in ra danh sách không có ai trùng ngày sinh   
* Xóa các sinh viên có trùng ngày sinh ra khỏi ListSV  

## II. Bài tập nâng cao

### 1. Thiết kế giải thuật
* **Cấu trúc dữ liệu:** Sử dụng cấu trúc liên kết vòng, mỗi nút gồm STT người chơi và link (trỏ đến người kế tiếp).
* **Quy trình thực hiện:**
    * **B1:** Tạo danh sách liên kết đơn, truyền STT từ $1$ đến $n$ vào. Sau đó duyệt tìm node cuối cùng, nối với node đầu để tạo thành liên kết vòng.
    * **B2:** Khai báo 2 con trỏ liên tiếp để thực hiện dò tìm và xóa.
    * **B3:** Lặp danh sách đến khi chỉ còn 1 người. Trong đó, 2 con trỏ $q$ và $p$ được dịch chuyển lên trước liên tục để tìm vị trí thứ $M$. Thực hiện xóa nút $p$ bằng lệnh `q->link = p->link`, sau đó lặp lại với $p$ mới.

### 2. Phân tích độ phức tạp và Thời gian chạy

**A. Độ phức tạp thuật toán (Xét trường hợp $M = 1$)**
* Mỗi lượt loại bỏ cần thực hiện $M$ bước nhảy con trỏ, tổng cộng có $N-1$ người bị loại.
* **Tổng số thao tác:** $M(N - 1) = (N - 1)$.
* **Độ phức tạp thời gian:** $O(n-1)$ hay xấp xỉ $O(n)$.

**B. Tính toán thời gian chạy với $N > 100.000$**
* **Phương pháp:** Sử dụng thư viện `<chrono>` để lấy một mốc thời gian ngay trước khi gọi hàm xử lý và một mốc ngay sau khi chạy xong. Hiệu của hai mốc này chính là thời gian thực thi.
* **Kết quả:** Với $N > 100.000$, thời gian thực hiện dao động khoảng **0.0023s – 0.076s**.

### C. Test case
  * $N = 1, M = 0$
  * $N = 5, M = 0$
  * $N = 5, M = 1$
  * $N = 18, M = 3$
  * $N = 182.461, M = 1$
  * $N = 999.999, M = 1$

**Link Test case: https://docs.google.com/document/d/1wIAA6KjYC9aV1qpYsuO0M66i7h7J7uN1UdAE6WO_wpY/edit?tab=t.0** 


