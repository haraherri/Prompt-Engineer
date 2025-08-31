Tôi đang gặp một bug trong dự án và cần bạn giúp phân tích và đưa ra giải pháp. Hãy thực hiện theo các bước sau:

**BƯỚC 1: PHÂN TÍCH BUG**
- Xác định loại bug (logic error, runtime error, performance issue, UI/UX bug, etc.)
- Phân tích nguyên nhân có thể gây ra bug
- Đánh giá mức độ nghiêm trọng và phạm vi ảnh hưởng

**BƯỚC 2: DEBUGGING STRATEGY**
- Đề xuất phương pháp debugging phù hợp
- Xác định các điểm cần kiểm tra trong code
- Gợi ý các công cụ debugging nên sử dụng

**BƯỚC 3: SOLUTION ANALYSIS**
- Đưa ra ít nhất 2-3 phương án giải quyết
- So sánh ưu nhược điểm của từng phương án
- Recommend giải pháp tối ưu nhất

**BƯỚC 4: IMPLEMENTATION**
- Cung cấp code fix chi tiết
- Giải thích từng thay đổi được thực hiện
- Đề xuất cách test để verify fix

**THÔNG TIN BUG:**

**Mô tả bug:**
Khi instructor tiến hành tạo course và section + lecture, thì lúc này ở trang section management thì mọi thứ vẫn bình thường, tạo vẫn đúng thứ tự course. Tuy nhiên, không hiểu tại sao khi tôi tiến hành update video cho từng lecture thì vẫn ở trang section hiển thị đúng thứ tự, nhưng khi ra ngoài trang chủ vào course detail xem thử thì phần thứ tự đã bị lệch đi (ví dụ lecture có 3 cái, update video cho cái đầu tiên thì nó nhảy xuống hiển thị ở cuối cùng, cũng như lecture 2 nó nhảy thành 3), nói chung cứ có cái nào update video mới nhất bị sai thứ tự hết. Trong khi ở trong section management vẫn hiển thị đúng

**Environment:**
- Ngôn ngữ lập trình: JavaScript (Node.js v22)
- Framework/Library: Express.js v4.21.1, React 18
- Database: PostgreSQL v17
- OS: Windows 11 + Ubuntu 24.04 (Redis Running)
- Browser: Chrome 

**Steps to Reproduce:**
1. Instructor truy cập trang section management để tiến hành update section + lecture và thêm video tương ứng 
2. lúc này đã hiển thị đúng thứ tự như đã tạo và update video
3. Published course, ra ngoài trang chủ và nhấn vào khóa học để xem chi tiết
4. Phát hiện sai thứ tự hiển thị lecture

**Expected Behavior:**
Trang web should hiển thị đúng thứ tự lecture như trong section management

**Actual Behavior:**
Trang web hiển thị sai thứ tự lecture

**Error Messages/Logs:**
không có

**Related Code:**
CourseDetail,jsx
CreateLecture,jsx
lecture.service.js
section.service.js

**Additional Context:**
Trước đây tôi có gặp bug này rồi và đã fix ở backend (do lỗi query sql không chính xác), nhưng chẳng hiểu sao bây giờ component khác bị chứ nó không nhất quán
