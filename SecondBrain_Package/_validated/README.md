# _validated/ — Insight được phép cite chính thức

> Folder này chứa insight đã qua kiểm chứng theo **Rule 3** trong `_brain/RULES.md`.
> Chỉ file trong folder này được cite cho lãnh đạo / báo cáo chính thức.
> File ngoài folder này = "đang nghiên cứu, chưa đủ vững".

## Điều kiện vào folder

File được promote vào đây khi thoả MỘT trong 2 điều kiện:
- **≥2 nguồn độc lập** xác nhận cùng kết luận, HOẶC
- **≥1 nguồn `[D]` (data thật)** chắc chắn

## Convention

- Filename: `YYYY-MM-DD_<TenInsight>.md` (prefix ngày promote)
- Dòng 2-3 mỗi file bắt buộc có:
  ```markdown
  > **Promoted vào `_validated/` ngày YYYY-MM-DD**
  > **Nguồn:** <link/dataset/interview/report>. File gốc: `<original path>`.
  ```
- COPY từ file gốc (không move) — giữ reference ngược lại.

## Cách thêm file vào đây

Dùng workflow `brain-promote`:
```
/brain-promote <path-to-file>
```

Hoặc thủ công:
1. `cp source.md _validated/YYYY-MM-DD_<TenInsight>.md`
2. Prepend block "Promoted + Nguồn" vào đầu file
3. Update `_brain/BRAIN_INDEX.md` nếu cần
4. Git commit: `promote YYYY-MM-DD: <short title>`

## Khi file outdated

- KHÔNG xoá. Đổi prefix `deprecated_YYYY-MM-DD_<TenInsight>.md` để giữ history.
- Hoặc move sang `_validated/_archive/`.
- Update `BRAIN_INDEX.md` ghi deprecated reason.
