# BRAIN INDEX — Bản đồ Second Brain

> File này được `brain-eod` cập nhật tự động mỗi ngày.
> Đây là điểm vào đầu tiên khi AI assistant hoặc bạn cần tìm context.

## Role

**Marketing** — 30Shine. Quản lý campaign, brand, content, ads, KOC, budget.

## Quy ước đọc bảng
- **Chủ đề** — mảng nội dung chính
- **Đường dẫn** — folder/file nguồn (relative từ repo root)
- **Skill liên quan** — skill/script automation nên dùng
- **Trạng thái** — `active` (đang dùng) / `archive` (lưu trữ) / `deprecated` (đã lỗi thời)

## Bảng chỉ đường

| Chủ đề | Đường dẫn chính | Skill liên quan | Trạng thái |
|---|---|---|---|
| Context & Background | `../00_context/` | — | active |
| Raw data (chưa xử lý) | `../01_raw_data/` | — | active |
| Cleaned data (đã xử lý) | `../02_cleaned_data/` | — | active |
| Báo cáo chính thức | `../03_reports/` | `baocao` | active |
| Creative assets & brief | `../04_creative/` | — | active |
| KOC management | `../05_koc/` | — | active |
| Budget & kế hoạch chi | `../06_budget/` | — | active |
| Skills & prompts AI | `../07_skills/`, `../08_prompts/` | `second-brain` | active |
| Decision log | `../09_decision_log/` | — | active |
| **Insight đã validated** | `_validated/` | `brain-promote` | **active** |

## File lõi của Second Brain

| File | Mục đích |
|---|---|
| `_brain/BRAIN_INDEX.md` | File này — bản đồ chỉ đường |
| `_brain/RULES.md` | Quy tắc vận hành (4 rule) |
| `_brain/PAIN_LOG.md` | Nhật ký pain point khi dùng hệ thống |
| `_validated/` | Insight đã kiểm chứng ≥2 nguồn, được phép cite chính thức |

## Lần cập nhật gần nhất

> Skill `brain-eod` append vào đây mỗi cuối ngày. Format:
> `- YYYY-MM-DD HH:MM — brain-eod scan N ngày, tagged X file, promoted Y file, flagged Z số liệu thiếu nguồn`

- **2026-05-26** — Second Brain khởi tạo (qua `/brain-init`).
