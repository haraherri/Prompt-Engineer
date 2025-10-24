# Bug-Fixing Analysis Framework

## ⚠️ RÀNG BUỘC QUAN TRỌNG
**TRONG PHẢN HỒI NÀY, CHỈ ĐƯỢC PHÉP:**
1. ✅ Phân tích lỗi chi tiết
2. ✅ Lập plan giải pháp
3. ✅ Viết pseudocode (nếu cần)
4. ❌ **KHÔNG ĐƯỢC CODE** (code sẽ do user request sau)
5. ❌ **KHÔNG ĐƯỢC cung cấp full solution**

**Sau khi user review plan, nếu approve thì user sẽ request: "Code solution này"**

---

# 🎯 DEVELOPMENT WORKFLOW PROTOCOL

## 🛑 MANDATORY CONSTRAINTS:
- **NEVER CODE WITHOUT PLAN APPROVAL**
- **STOP AFTER EACH COMPONENT**
- **WAIT FOR "done" CONFIRMATION**
- **NO BATCH IMPLEMENTATIONS**

## 📝 EXECUTION PATTERN:

### **Phase 1: Analysis & Planning**
- 🔍 Analyze existing codebase thoroughly
- 📋 Create detailed implementation plan
- 🎯 List all files to create/modify
- 📊 Present plan with clear deliverables
- **→ STOP → Wait for "done" confirmation**

### **Phase 2: Step-by-Step Implementation**
```
Step 1: [Component/Feature Name]
  → Code implementation
  → STOP → Wait for "done" confirmation

Step 2: [Component/Feature Name]
  → Code implementation
  → STOP → Wait for "done" confirmation

Step 3: [Component/Feature Name]
  → Code implementation
  → STOP → Wait for "done" confirmation

... Continue pattern until completion ...
```

### **Phase 3: Testing & Documentation**
- 🧪 Testing guidelines
- 📚 Usage documentation
- **→ STOP → Wait for final approval**

## ✅ USER CONFIRMATION COMMANDS:
- **"done"** → Continue to next step
- **"issues: [description]"** → Fix issues first, then re-submit same step
- **"test"** → Provide testing guidelines for current step
- **"skip"** → Move ahead (with warnings noted)
- **"back"** → Go back to previous step for revision

## 🎯 QUALITY STANDARDS:
- Clean, documented code (comments for complex logic)
- Error handling & loading states
- Mobile responsive (if UI component)
- Performance optimized
- No breaking changes to existing functionality

## 🚀 WHEN USER SAYS "Code solution...":
**START WITH: Analysis & Planning Phase**

---

## BƯỚC 0: PHÂN LOẠI & CONTEXT
**LLM TỰ PHÂN TÍCH VÀ ĐỀ XUẤT:**

- **Loại bug:** Logic / Runtime / Performance / UX / Architecture Pattern?
- **Mức độ ưu tiên:** CRITICAL / HIGH / MEDIUM / LOW
- **Timeline đề xuất:** Quick fix (< 1 ngày) / Medium (1-3 ngày) / Long-term refactor

### 🔍 PHÂN TÍCH RÀNG BUỘC (LLM TỰ ĐÁNH GIÁ):
Dựa trên bug description, LLM phải:

1. **Xác định Impact Scope:**
   - Database có bị ảnh hưởng không?
   - API contract có thay đổi không?
   - Performance có degradation risk không?
   - Data integrity có nguy cơ không?
   - Backward compatibility cần thiết không?

2. **Đề xuất Constraints tương ứng:**
   
   **✅ ĐƯỢC PHÉP:**
   - [ ] Modify frontend? → Lý do
   - [ ] Modify backend? → Lý do
   - [ ] Add/modify database? → Với điều kiện gì?
   - [ ] Add new dependencies? → Lý do
   - [ ] Breaking changes? → Với điều kiện gì?

   **❌ KHÔNG ĐƯỢC PHÉP:**
   - KHÔNG ĐƯỢC [constraint] → Vì [lý do cụ thể]
   - KHÔNG ĐƯỢC [constraint] → Vì [lý do cụ thể]
   
   **🎯 BẮT BUỘC PHẢI LÀM:**
   - PHẢI [action] → Để đảm bảo [criteria]
   - PHẢI verify [metric] → Để kiểm tra [risk]

3. **Giải thích tại sao đề xuất constraints này:**
   - Dựa trên bug type
   - Dựa trên severity
   - Dựa trên dependencies

### 📊 YÊU CẦU XÁC NHẬN:
Sau khi đề xuất constraints, hỏi user:
```
⚠️ Constraints trên có phù hợp với dự án của bạn không?
   - Nếu OK: reply "done" để tiếp tục
   - Nếu cần điều chỉnh: reply "adjust: [mô tả]"
   
   Ví dụ: "adjust: Có thể breaking change, không cần backward compatibility"
```

---

## BƯỚC 1: PHÂN TÍCH BUG (ROOT CAUSE DEPTH)
- **Surface symptom:** Hiện tượng quan sát được
- **Root cause analysis:** Tại sao? Có phải design issue không?
- **Scope ảnh hưởng:** Single user case hay systemic pattern?
- **Dependencies:** Các component/service khác bị ảnh hưởng?
- **Severity:** Data loss? Security? Performance degradation? UX friction?

---

## BƯỚC 2: SOLUTION MATRIX
Liệt kê 2-3 phương án **KHÔ CÔNG (không code)**:

- **Option 1 - [Tên giải pháp]:**
  - Cách thực hiện (pseudocode/text description)
  - Ưu điểm: Complexity ↓, Performance ↑
  - Nhược điểm: Scalability ↓, Maintenance ↑
  - Timeline: X ngày
  - Files cần sửa: [File A, File B]

- **Option 2 - [Tên giải pháp]:**
  - Cách thực hiện
  - Ưu điểm / Nhược điểm
  - Timeline
  - Files cần sửa

- **Option 3 - [Tên giải pháp]:**
  - Cách thực hiện
  - Ưu điểm / Nhược điểm
  - Timeline
  - Files cần sửa

**RECOMMENDATION:** [Option X] - Lý do cụ thể

---

## BƯỚC 3: DEBUGGING STRATEGY
- **Hypothesis testing:** Cách verify root cause
- **Debug points:** Các breakpoint/log cần thêm
- **Tools:** Browser DevTools, Server logs, Database query, etc.
- **Reproduction steps:** Exact steps để trigger lại bug

---

## BƯỚC 4: IMPLEMENTATION PLAN (MÔ TẢ, KHÔNG CODE)
- **File A - [Tên file]:**
  - Phần nào sửa?
  - Thay đổi gì? (describe, không code)
  - Tại sao?

- **File B - [Tên file]:**
  - Phần nào sửa?
  - Thay đổi gì?
  - Tại sao?

- **Side effects:** Có gây ảnh hưởng khác không?
- **Rollback plan:** Nếu fix gây lỗi, cách revert?

---

## BƯỚC 5: TESTING & VERIFICATION PLAN
- **Unit tests cần viết:** [Mô tả, không code]
- **Integration tests:** [Mô tả]
- **Edge cases:**
  - [Scenario 1 & cách test]
  - [Scenario 2 & cách test]
  - [Scenario 3 & cách test]
- **Performance check:** Có slow down không?

---

## 🎯 BƯỚC 6: READY FOR IMPLEMENTATION?
**Nếu plan trên okayed, user comment:**
```
"Code giải pháp Option X theo plan trên"
```

**Lúc đó mới bắt đầu code với đầy đủ file cần thay đổi.**

---

## CUNG CẤP THÔNG TIN
### Bug Description
Hiện tại, tôi đang gặp vấn đề về việc play video trong trang course-progress. Lấy video là 19:33 giây làm chuẩn, thì tôi đã xem hết đến 15:44 (80%) và hệ thống đánh dấu với dữ liệu viewed là true và UI cập nhật tiến độ. Thì đột nhiên, không hiểu tại sao ngay khi UI vừa toast completed thì thanh progressbar của player quay trở về 00:00 (thời điểm bắt đầu video), mặc dù lúc này viewed vẫn đánh dấu là true rồi 
đây là dữ liệu trong database table lecture_progress khi xảy ra điều đó: id:cmgxtxwji001pt6x0w9sifciv
course_progress_id: cmgxtqz8l000pt6x04z2a4gpp
lecture_id: cmf6cyubo0005t6ewor8zgdmh
viewed: true
viewed_at: 2025-10-19 15:12:44.079000 +00:00
completion_percent: 80
last_watch_position: 943
last_watched_at: 2025-10-19 15:12:44.079000 +00:00
suspicious_flags: null
total_time_spent: 954
watch_count: 1

### Environment
- OS / Browser / Node version: Windows 11/Chrome/Node v22.16.0
- Frameworks & Dependencies: PERN
- Database / Cache: PostgreSQL/Redis

### Code Snippets (BẮTBUỘC)
```
- [ ] @VideoPlayer.jsx 
- [ ] @VideoPlayerSection.jsx 
- [ ] @CourseProgress.jsx 
- [ ] @useVideoTracking.js 
- [ ] @useVideoProgress.js 
- [ ] @progress.core.service.js 

```

### Logs & Error Output
Không có

### Additional Context (Optional)
Case này rất khó test vì lúc bị lúc không chứ không phải lúc nào cũng always. Tôi test bằng cách xóa mọi record của table lecture_progress và course_progress xong test lại là hay bị nhất

1.Khi video reset về 00:00, không có toast resuming...
2. reset ngay lập tức, ngay khi xuất hiện toast 