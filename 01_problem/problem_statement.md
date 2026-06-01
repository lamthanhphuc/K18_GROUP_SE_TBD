# Problem Statement

## 1. Background

Trong các cuộc hackathon, nhiều đội (team) phát triển một sản phẩm phần mềm trong một khoảng thời gian rất ngắn. Mentor và Organizer phải theo dõi tiến độ và chất lượng của nhiều repository khác nhau, trong khi thời gian để đọc và đánh giá mã nguồn cho từng đội rất hạn chế. Việc review thủ công mỗi repository tốn nhiều thời gian và dẫn tới độ phủ không đều giữa các đội. Nhiều đội chưa tuân thủ cấu trúc repository rõ ràng (ví dụ thiếu README, thiếu thư mục test, file mã quá dài hoặc chứa TODO/FIXME), gây khó khăn cho việc bảo trì và chấm điểm.

Hệ thống SEAL Hackathon Management System có định hướng lưu trữ liên kết repository của các đội và chạy một module AI Review định kỳ để sinh phản hồi tham khảo. Module này chỉ cung cấp dữ liệu tham khảo để hỗ trợ Mentor, Organizer và Participant — không thay thế vai trò chấm điểm chính thức của Judge.

## 2. Target Users

- Participant: nộp repository và nhận feedback để cải thiện code, cấu trúc dự án và tài liệu.
- Mentor: sử dụng AI Review làm công cụ lọc, ưu tiên các repository cần can thiệp nhanh và hỗ trợ mentoring hiệu quả hơn.
- Organizer: theo dõi chất lượng repository chung của cuộc thi, giám sát tiến độ review và trạng thái review của các team.
- Judge: vẫn thực hiện chấm điểm chính thức theo rubric; AI Review chỉ đóng vai trò tham khảo và không ảnh hưởng tự động đến ranking.

## 3. Problem

- Mentor và Organizer gặp khó khăn khi phải review số lượng lớn repository trong thời gian ngắn.
- Review thủ công thường thiếu đồng nhất giữa các đội và có thể bỏ sót các vấn đề cơ bản như thiếu validation, thiếu xử lý lỗi (error handling), code smell, lỗi bảo mật cơ bản, thiếu test, hoặc cấu trúc dự án không rõ ràng.
- Nhiều repository không theo một khuôn khổ tiêu chuẩn, gây khó khăn cho việc đánh giá và tái sản xuất (reproduce) dự án.
- Cần một công cụ hỗ trợ sinh feedback định kỳ ở mức tham khảo, giúp tập trung nỗ lực con người vào những vấn đề quan trọng hơn.

## 4. Existing Solutions

- Manual code review do con người thực hiện.
- Công cụ phân tích tĩnh (static analysis) như linters và scanners phát hiện lỗi theo quy tắc.
- Hệ thống tự động hoá chất lượng mã (CI checks, code quality platforms) báo cáo metric cố định.
- LLM-based code review cung cấp nhận xét mềm dẻo và ngữ cảnh hóa.
- Công cụ đề xuất cấu trúc repository (repository scaffolding / templates) đưa ra khung tham khảo.
- Các hệ thống phản hồi tự động trong giáo dục lập trình (automated feedback) gợi ý sửa lỗi cơ bản cho sinh viên.

Các hướng này sẽ được phân tích sâu hơn trong phần Related Work của báo cáo nghiên cứu.

## 5. Limitation of Existing Solutions

- Manual review có chất lượng cao nhưng tốn thời gian và khó mở rộng khi số lượng team tăng.
- Static analysis phát hiện lỗi theo rule nhưng feedback thường cứng nhắc và thiếu ngữ cảnh dự án cụ thể.
- LLM/AI feedback linh hoạt nhưng có thể sai lầm, tạo ra kết luận không chính xác nếu không có giới hạn rõ ràng; cần sự kiểm duyệt của con người.
- Các công cụ đề xuất cấu trúc repository thường cung cấp khuôn mẫu chung, chưa liên kết chặt với bối cảnh hackathon (thời gian ngắn, yêu cầu nộp dự án, đa dạng ngôn ngữ/framework).
- Chưa có công cụ tích hợp trực tiếp workflow hackathon (team, bảng, mentor, organizer, judge, ranking) để đưa feedback AI vào luồng làm việc mà vẫn bảo đảm tính tham khảo và không can thiệp tự động vào kết quả chấm điểm.

## 6. Proposed Prototype

Mục tiêu: tái hiện (Read & Reproduce) một prototype module AI-Assisted Code Review phù hợp bối cảnh hackathon, với phạm vi và giới hạn rõ ràng.

- Input:
	- Thông tin team (team id, thành viên, submission metadata).
	- Repository URL (git) hoặc file zip mã nguồn.
	- Thông tin context (loại dự án, ngôn ngữ chính và thời điểm review gần nhất nếu cần chạy theo lịch review định kỳ).
- Processing steps:
	1. Source scanner: trích xuất cây thư mục và liệt kê các file chính (README, package manifests, build scripts, test folders, src).
	2. Structural analysis: phân tích cấu trúc hiện tại, nhận diện mô hình dự án (library, web app, CLI, v.v.).
	3. Static checks cơ bản: kiểm tra TODO/FIXME, file quá dài, thiếu README, thiếu thư mục test, hardcoded secrets (giả định), thiếu validation/error handling ở mức heuristic.
	4. LLM/AI-based review: tổng hợp nhận xét theo template, tạo danh sách issues và suggestions, đề xuất khung cấu trúc repository tham khảo.
	5. Serialize result vào JSON theo schema ngắn gọn.
	6. Lưu lịch sử review và trạng thái (PENDING → COMPLETED/FAILED).
- Output fields (tóm tắt): `review_score`, `summary`, `issues`, `suggestions`, `repository_structure_notes`, `status`, `reviewed_at`, và `review_history`.

Ràng buộc prototype: đây là bản tái hiện nghiên cứu (Read & Reproduce) — không trực tiếp can thiệp vào điểm số chính thức, không tự động cập nhật ranking, và luôn gắn nhãn là "tham khảo". Con người (Mentor/Judge/Organizer) giữ quyền quyết định cuối cùng.

## 7. Expected Output

Input:

- Team information (id, members, submission metadata).
- Repository URL hoặc file zip chứa mã nguồn.
- Trích xuất cây thư mục và các file nguồn.
- Kết quả tóm tắt từ static analysis.

Output (JSON-like fields):

- `review_score`: số điểm tham khảo (ví dụ 0–100) hoặc null nếu không đủ dữ liệu.
- `summary`: nhận xét tổng quan ngắn gọn về chất lượng và điểm mạnh/điểm yếu chính.
- `issues`: danh sách các vấn đề phát hiện được (mỗi mục gồm `type`, `file`, `line` (nếu có), `description`, `severity`).
- `suggestions`: danh sách gợi ý cải thiện tương ứng với từng issue hoặc gợi ý cấu trúc chung.
- `repository_structure_notes`: một khung tham khảo ngắn (ví dụ: `src/`, `tests/`, `docs/`, `README.md`, `CONTRIBUTING.md`, `build scripts`, `ci/`) phù hợp với loại dự án.
- `status`: một trong `PENDING`, `COMPLETED`, `FAILED`.
- `reviewed_at`: timestamp của lần review.
- `review_history`: lịch sử các lần review trước đó (timestamp, reviewer_type: AI/HUMAN, summary, score).

Ghi chú quan trọng: kết quả do AI/LLM sinh ra chỉ làm tài liệu tham khảo — không thay thế quá trình chấm điểm chính thức của Judge và không ảnh hưởng tự động tới ranking hay quyết định loại/đi tiếp của team.

---

Tài liệu này nhằm phục vụ giai đoạn nghiên cứu Kỳ 5: Read & Reproduce, mô tả phạm vi, mục tiêu và đầu ra mong đợi của việc tái hiện một module hỗ trợ review mã nguồn bằng AI cho bài nộp hackathon.
