
---

## Phần 1 – Thiết kế quy trình (5 bước)

```
1. Tiếp nhận → 2. Làm rõ + viết AC → 3. Gán MoSCoW → 4. Chọn vào Sprint → 5. Làm và nghiệm thu
        ↑                                                                          |
        └─────────── yêu cầu mới phát sinh giữa Sprint quay lại bước 1 ───────────┘
```

| Bước | Việc cần làm | Người chịu trách nhiệm | Điều kiện sang bước sau |
|------|--------------|------------------------|-------------------------|
| **1. Tiếp nhận** | Bộ phận đề xuất gửi story theo mẫu "Là một…, tôi muốn…, để…" kèm lý do và mục tiêu. Story được ghi vào Product Backlog, **chưa xếp ưu tiên, chưa vào Sprint**. | **PO** ghi nhận; bộ phận đề xuất cung cấp thông tin. SM giữ cổng này, không cho story đi tắt. | Story đúng mẫu, có giá trị và người đề xuất rõ ràng, đã nằm trong Product Backlog. |
| **2. Làm rõ + viết AC** (Backlog Refinement) | PO và Developers cùng viết **3–7 AC** theo Given – When – Then (mỗi AC một kịch bản, có số liệu/thông báo cụ thể). Developers hỏi làm rõ và **ước lượng điểm**. | **PO** chịu trách nhiệm AC; **Developers** ước lượng và rà AC có kiểm thử được không. **SM** điều phối buổi họp. | Story có 3–7 AC đúng Given – When – Then, PO và Developers đã thống nhất, và đã có điểm ước lượng. Thiếu AC thì **dừng ở bước này**. |
| **3. Gán nhãn MoSCoW** | PO gán Must / Should / Could / Won't cho **một bản phát hành cụ thể** bằng phép thử chung: thiếu hạng mục này bản phát hành có chạy được không, có cách xử lý tạm không, có gắn mục tiêu bản phát hành không. Các bộ phận trình bày nhu cầu, **PO là người quyết**. Kiểm tra tổng Must không vượt khoảng 60% năng lực. | **PO** quyết nhãn và ghi lý do; **SM** nhắc lại phép thử khi có tranh cãi. | Mọi story ứng viên đều có nhãn kèm lý do, tổng Must ≈ 60% năng lực trở xuống, hạng mục Won't đã được báo cho bên liên quan. |
| **4. Chọn vào Sprint** (Sprint Planning) | Kiểm tra "sẵn sàng vào Sprint": có AC thống nhất, có điểm, có nhãn. Developers chọn từ đầu Backlog theo thứ tự PO đã xếp, **vừa năng lực Sprint**, và xác nhận DoD chung áp dụng cho từng story. | **Developers** cam kết khối lượng; **PO** quyết thứ tự; **SM** kiểm tra danh sách sẵn sàng. | Tổng điểm không vượt năng lực, mọi story trong Sprint đủ AC + điểm + nhãn, đã có Sprint Goal. |
| **5. Làm và nghiệm thu** | Developers xây dựng. Story chỉ **Done** khi đạt **toàn bộ AC** (PO xác nhận) **và toàn bộ DoD chung** (Developers xác nhận). Yêu cầu mới phát sinh giữa Sprint **không chen vào**, quay lại bước 1. | **Developers** làm và đảm bảo DoD; **PO** nghiệm thu AC; **SM** bảo vệ Sprint. | Đạt cả AC lẫn DoD thì mới tính vào Increment và đưa ra Sprint Review. |

**Ghi chú về DoD:** DoD là một bản chung cho mọi story, do Developers xây dựng. Không sửa riêng cho từng story, chỉ được nâng dần theo năng lực của đội, bàn ở Sprint Retrospective (SM điều phối).

---

## Phần 2 – Xử lý tình huống

### Tình huống 1: Marketing đòi đưa "Tặng mã giới thiệu bạn bè" (chưa có AC) vào Sprint đang chạy

**Cách xử lý:** Story không được vào thẳng Sprint đang chạy, vì nó chưa có AC nên chưa qua bước 2, và Sprint đang chạy đã có Sprint Goal và cam kết của Developers. Lan chuyển yêu cầu về **bước 1** (ghi vào Product Backlog), Đức quyết ưu tiên, rồi story được viết AC ở buổi Refinement để vào Sprint kế tiếp. Nếu Đức thấy thật sự khẩn cấp, Đức và Developers có thể thương lượng đổi phạm vi (đổi lấy hạng mục có điểm tương đương) mà không làm hỏng Sprint Goal, nhưng story **vẫn phải có AC trước khi bắt đầu làm**.

**AC mẫu cho story "Tặng mã giới thiệu bạn bè":**

**Given** khách A có mã giới thiệu "ABC123" và người bạn B chưa có tài khoản,
**When** B đăng ký tài khoản mới bằng mã "ABC123",
**Then** hệ thống tặng khách A 01 mã khuyến mãi "GO20" (giảm 20%) và hiển thị mã này trong danh sách mã của khách A.

*Đây là AC ví dụ. Điều kiện tặng (đăng ký hay hoàn thành chuyến đầu tiên) và loại mã tặng do Đức chốt.*

### Tình huống 2: Cả 3 bộ phận đều cho yêu cầu của mình là Must

**Cách xử lý:** Nhãn MoSCoW do **PO quyết**, không do bộ phận nói to nhất, và chỉ tính cho **một bản phát hành cụ thể**. Mọi yêu cầu đi qua cùng phép thử ở bước 3, và tổng Must không được vượt khoảng 60% năng lực. Nếu cả 3 yêu cầu cùng là Must thì gần như chắc chắn vượt trần, nên bắt buộc phải có yêu cầu bị hạ nhãn. Yêu cầu nào không qua phép thử được xếp Should/Could/Won't và báo rõ lý do cho bộ phận đề xuất.

**Cách gán nhãn mẫu** (bản phát hành "Tháng khuyến mãi", năng lực 10 điểm, trần Must ≈ 6 điểm):

| Bộ phận | Yêu cầu | Điểm | Nhãn | Lý do |
|---------|---------|------|------|-------|
| Vận hành | Sửa lỗi hiển thị sai cước sau khuyến mãi | 2 | **Must** | Đang thu sai tiền khách, thiếu thì không thể phát hành và không có cách xử lý tạm. |
| Marketing | Tặng mã giới thiệu bạn bè | 3 | **Should** | Gắn với chương trình khuyến mãi nhưng thiếu thì bản phát hành vẫn chạy được; vẫn phải viết AC (xem tình huống 1) trước khi vào Sprint. |
| Chăm sóc khách hàng | Chat với tài xế | 3 | **Won't** (lần này) | Khách vẫn gọi điện được và không thuộc mục tiêu bản phát hành; báo rõ cho CSKH và đề xuất đưa vào bản sau. |

Kiểm tra trần: nếu nhận cả 3 là Must thì 2 + 3 + 3 = 8 điểm = **80% năng lực**, vượt mức khoảng 60%. Sau khi gán nhãn theo phép thử, chỉ còn 1 Must (2 điểm), nằm trong trần.
