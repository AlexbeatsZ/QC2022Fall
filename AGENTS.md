> [!WARNING]
> **迁移审计未完成。** 本项目的 AI 提示词曾在 `AIREADME.md` → `AGENTS.md` 迁移中发生内容合并、删改、语义重写，或无法用 Git 证明为纯改名。当前内容可能与项目真实状态不一致。
>
> 在进行任何项目修改前，必须先核对迁移前后的 Git 历史、当前代码与配置、真实运行/部署状态，以及项目内部调用模型的提示词和启动参数。确认迁移内容与真实状态一致后，删除本警告，再继续正常修改；不得仅依据本文件恢复、删除或改变项目行为。

# QC2022Fall build guidance

## 1. Project Goal
Compile the QC2022Fall course repository into PDF artifacts.

## 2. Lessons Learned
- The document must be built with XeLaTeX because it uses `ctex`, `fontspec`, and CJK fonts.
- The original FZX/SourceHan font files were not present on this Windows machine; use bundled Windows fonts (`simsun.ttc`, `simhei.ttf`, `simkai.ttf`, `msyh.ttc`) for local compilation.
- `fig/angular_momentum_Wikipedia.pdf` is a jsPDF file that XeLaTeX/xdvipdfmx cannot embed here because of an unavailable `ArialUnicode` font; rendering it once to PNG and referencing the PNG avoids the failure.
- Chinese text or punctuation inside math mode can disappear as missing characters; keep Chinese text in `\text{...}` where appropriate and use normal math punctuation inside displayed equations.
