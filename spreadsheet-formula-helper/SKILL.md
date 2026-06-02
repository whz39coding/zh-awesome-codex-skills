---
name: spreadsheet-formula-helper
description: 编写和调试 Excel/Google Sheets 公式、透视表和数组公式，并在不同方言间转换。适用于用户需要可运行公式、示例和边界情况检查。Keywords: spreadsheet formulas, Excel, Google Sheets.
metadata:
  short-description: Build/debug Excel or Sheets formulas
---

# Spreadsheet Formula Helper

Produce reliable spreadsheet formulas with explanations.

## Inputs to gather
- Platform (Excel/Sheets), locale (comma vs. semicolon separators), sample data layout (headers, ranges), expected outputs, and constraints (volatile functions allowed?).
- Provide small example rows and the desired result for them.

## Workflow
1) Restate the problem with explicit ranges and sheet names; propose a minimal sample to verify.
2) Draft formula(s); when dynamic arrays are available, prefer them over copy-down formulas.
3) Explain how it works and where to place it; include named ranges if helpful.
4) Edge cases: blank rows, mixed types, timezone/date quirks, duplicates; offer guardrails (e.g., `IFERROR`, `LET`, `LAMBDA`).
5) Variants: if porting between Excel and Sheets, provide both versions.

## Output
- Primary formula, short explanation, and a 2–3 row worked example showing inputs → outputs.
- Optional: quick troubleshooting checklist for common errors.
