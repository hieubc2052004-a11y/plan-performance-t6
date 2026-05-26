# RULES — Second Brain

> 4 rule cốt lõi. Giữ ngắn để dễ nhớ và tuân thủ.

## Rule 1 — Tag line dòng đầu (qua `brain-eod`, không ép khi tạo)

### PHẠM VI ÁP DỤNG
Tag chỉ áp dụng cho **working documents** và **file nội bộ**:
- Raw research, data note, analysis draft
- Reference material, framework, guide
- Knowledge card, insight doc
- Ops script, pipeline note

### KHÔNG áp dụng tag cho
- **Báo cáo chính thức công ty** (BC tuần, TMP tháng, SLA) — các file này phải theo **tiêu chuẩn báo cáo công ty**, KHÔNG được phá form bằng cách chèn `tags:` ở đầu
- File template chuẩn do phòng ban khác phát hành
- File đã có YAML frontmatter (SKILL.md, config)

### Cách nhận biết "báo cáo chính thức"
- Tên file có prefix: `BC_`, `TMP_`, `SLA_`, `Phieu_`, `PO-`, `STD-`
- Hoặc nằm trong folder `Báo cáo*/`, `SLA/`, `TMP/`
- Hoặc có header `# [TMP]` / `# BÁO CÁO ĐỊNH KỲ` / `PHIẾU ĐÁNH GIÁ`
- Khi không chắc → hỏi user trước khi tag

**Lưu ý:** `BRIEF_` KHÔNG phải báo cáo chính thức — đây là working doc nội bộ giữa các team, tag bình thường.

### Format tag (với file được phép tag)
```
tags: [type, topic, date]
```
- `type` ∈ `{raw, insight, ref, ops}`
  - `raw` — ghi chú thô, research chưa validated
  - `insight` — kết luận đã validated (nên promote vào `_validated/`)
  - `ref` — tài liệu tham khảo (brand guide, framework, registry)
  - `ops` — script, pipeline, skill
- `topic` — 1 từ khoá chính (vd `crm`, `ads-meta`, `customer-journey`)
- `date` — `YYYY-MM-DD` hoặc `YYYY-WNN`

**Không bắt tự tag khi đang viết.** Skill `brain-eod` quét cuối ngày và đề xuất tag → user confirm.

### Index báo cáo chính thức (không tag)
Báo cáo chính thức được index qua **BRAIN_INDEX.md** (external) và **filename convention** (vd `BC_Weekly_*.md` — grep theo tên file là đủ). Không cần tag trong nội dung file.

## Rule 2 — Evidence là HABIT, không phải SCHEMA

Mọi con số trong file kèm:
- Tag nguồn: `[D]` data thật · `[R]` desk research · `[A]` expert · tag custom theo team (`[R-CX]`, `[R-LEGAL]`...)
- Link hoặc tên dataset ngay cạnh số

**Ví dụ đúng:**
> "Churn khách mới 18% [D] (dump `2026-05-15_segment.csv`)"

**Ví dụ sai:**
> "Churn 18%" — không có nguồn, sếp sẽ hỏi ngay.

## Rule 3 — Promote insight vào `_validated/` khi đủ điều kiện

File được phép chuyển vào `_validated/` khi:
- Có **≥2 nguồn độc lập** xác nhận cùng kết luận, **HOẶC**
- Có **≥1 nguồn `[D]` (data thật)** chắc chắn

Chỉ file trong `_validated/` được phép **cite thẳng cho lãnh đạo**.
File ngoài `_validated/` = "đang nghiên cứu, chưa đủ vững".

Dùng workflow `brain-promote` (COPY, không move — giữ reference cũ).

## Rule 4 — Không tạo folder mới khi chưa có ≥5 file cùng topic

Tránh premature structure. Nếu 1 topic chỉ có 1-2 file, để chung folder sẵn có. Khi topic đó phát sinh ≥5 file, mới tạo folder riêng.

## Thứ tự tìm context khi AI assistant cần

1. Đọc `_brain/BRAIN_INDEX.md` trước
2. `grep tags:` trên `.md` nếu cần filter type/topic
3. Semantic search nếu grep không đủ
4. Chỉ lục toàn bộ folder khi 3 bước trên fail

## Khi nào chạy `brain-eod`

- **Tối ưu:** mỗi cuối ngày làm việc (5 phút review)
- **Chấp nhận được:** 3-5 ngày/lần (skill xử lý backlog)
- **Không OK:** >1 tuần không chạy (backlog lớn, tag sẽ kém chính xác)

## Khi nào chạy `brain-quick`

- Ngày quá bận, không có 5 phút chạy full EOD
- Chỉ làm 2 việc: git snapshot + log pain nếu có
- Mất <1 phút, đảm bảo không gãy chuỗi commit hằng ngày
