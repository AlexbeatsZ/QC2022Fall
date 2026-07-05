# AIREADME

## 1. Project Goal
Compile the QC2022Fall course repository into PDF artifacts.

## 2. Lessons Learned
- The document must be built with XeLaTeX because it uses `ctex`, `fontspec`, and CJK fonts.
- The original FZX/SourceHan font files were not present on this Windows machine; use bundled Windows fonts (`simsun.ttc`, `simhei.ttf`, `simkai.ttf`, `msyh.ttc`) for local compilation.
- `fig/angular_momentum_Wikipedia.pdf` is a jsPDF file that XeLaTeX/xdvipdfmx cannot embed here because of an unavailable `ArialUnicode` font; rendering it once to PNG and referencing the PNG avoids the failure.
- Chinese text or punctuation inside math mode can disappear as missing characters; keep Chinese text in `\text{...}` where appropriate and use normal math punctuation inside displayed equations.

## 3. Task Board
- [x] Inspect repository structure and build instructions.
- [x] Compile source files into PDF.
- [x] Verify generated PDF artifacts.
