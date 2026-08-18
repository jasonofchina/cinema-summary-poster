# 🔤 Font Specification / 海报字体使用规范

> This document solves the #1 problem with AI-generated posters: garbled text.
> All font rules MUST align with SKILL.md Font Rules:
> **Chinese Titles use Songti (Serif); English Titles use Sans-Serif; Body uses Kaiti (Script).**
>
> 这份文档专门解决"AI 生成海报时文字出错"的问题。
> 所有字体规则必须与 SKILL.md 中的「字体规则」保持一致：
> **中文标题用宋体，英文标题用无衬线体，正文用楷体。**

---

## Default Font Scheme / 默认字体方案

| Text Level / 文字层级 | Chinese Font / 中文字体 | English Font / 英文字体 | Weight / 字重 | Content / 适用内容 |
| :--- | :--- | :--- | :--- | :--- |
| Main Title / 主标题 | Songti / 宋体 | Sans-Serif / 无衬线 | Regular or Bold | Film/Series name / 电影/电视剧名称 |
| Subtitle / 副标题 | Songti / 宋体 | Sans-Serif / 无衬线 | Regular | Classic quote, one-line theme / 经典台词、一句话主旨 |
| Body / 正文 | Kaiti / 楷体 | Kaiti / Script | Regular | Review, short comment, explanation / 影评、短评、阐释文字 |
| Annotation / 注释 | Songti / 宋体 | Sans-serif / 无衬线 | Light | Rating source, year, credit / 评分来源、年份、署名 |

> ⚠️ Critical Rules / 重要规则:
> - Chinese titles MUST use Songti; never Heiti or Yuanti. / 中文标题必须用宋体，不能用黑体、圆体。
> - English titles MUST use Sans-Serif to prevent AI stroke merging/garbling. / 英文标题必须用无衬线体，防止 AI 笔画粘连乱码。
> - Chinese body MUST use Kaiti; never Songti (breaks hierarchy). / 中文正文必须用楷体，不能用宋体。

---

## Preventing AI Garbled Text / 如何避免 AI 出图文字乱码

This is the most common failure point. Follow strictly.
这是本 Skill 最容易翻车的地方，必须严格遵守。

### ✅ 5 Mandatory Actions / 必须做的 5 件事

1. **Use Sans-serif for Foreign Titles / 外文片名用无衬线字体**
   English, Japanese, Korean titles → always Sans-serif. Serif strokes merge in AI generation.
   英文、日文、韩文片名统一用 Sans-serif，衬线字体笔画容易粘连。
2. **Post-process Complex Text / 复杂文字后期叠字**
   Title > 6 characters or contains rare characters → do NOT let AI draw it.
   Generate background first, then overlay text with image editor.
   片名超 6 字或含生僻字，先让 AI 生成背景图，再用图片编辑工具叠字。
3. **Limit Characters Per Line / 控制单行字数**
   Title ≤ 8 chars. Quote ≤ 20 chars. Otherwise wrap or trim.
   标题不超过 8 字，台词不超过 20 字，超过就换行或删减。
4. **Character-by-Character Verification / 生成后逐字检查**
   Inspect every single character. Regenerate immediately if any garbling, missing stroke, or merging found.
   每个字都要看一遍，发现乱码、缺笔画、粘连立即重新生成。
5. **Special Font Downgrade / 特殊字体降级机制**
   If user requests calligraphy/art font, try once. If readability drops, tell user: "This font causes AI garbling; recommend switching to Songti or Kaiti."
   用户要求书法体/花体时先尝试，可读性差则建议换成宋体或楷体。

### ❌ 3 Absolute Prohibitions / 绝对禁止的 3 件事

1. **Never use cursive/grass script / 禁止连笔字、草书、狂草** — AI cannot reproduce connected strokes accurately.
2. **Never use >3 fonts per poster / 禁止超过 3 种字体** — Causes AI confusion and incorrect glyphs.
3. **Never ask AI to generate handwritten Chinese / 禁止 AI 生成手写体中文** — Unstable strokes, near-certain missing characters.

---

## Font Instructions in Mode A Prompts / 模式 A Prompt 中的字体说明规范

When returning a prompt (Mode A), font and text requirements MUST be written into the prompt as explicit text instructions, e.g.:
返回 Prompt（模式 A）时，必须把字体与文字要求以明确文本写入 prompt，例如：
- "Title in Chinese Songti (Serif), English title in Sans-Serif." / "中文标题使用宋体（Serif），英文标题使用无衬线体（Sans-Serif）。"
- "Body text in Kaiti (Script)." / "正文使用楷体。"
- "Render the background WITHOUT text; overlay all text in post-processing." / "背景图不含文字，所有文字后期叠加。"

This ensures users can reproduce correct typography on any external platform (MJ / Jimeng / SD / DALL·E).
这样用户在任何外部平台（MJ/即梦/SD/DALL·E）都能复现正确排版。

---

## Size Hierarchy & Layout / 字号层级与排版规范

| Level / 层级 | Size Ratio (% of frame height) / 字号比例 | Position / 位置建议 |
| :--- | :--- | :--- |
| Main Title / 主标题 | 8% - 12% | Top 1/3 or center / 画面上方 1/3 或正中央 |
| Subtitle / 副标题 | 5% - 7% | Below title, gap = title height × 0.5 / 主标题下方 |
| Body / 正文 | 3% - 5% | Bottom 1/3 or side / 画面下方 1/3 或侧边 |
| Annotation / 注释 | 2% - 3% | Bottom edge or corner / 画面底部或角落 |

### General Typography Rules / 排版通用要求
- Letter spacing: Title = char width × 0.1; Body = char width × 0.05. / 字间距
- Line height: Body = char height × 1.5. / 行间距
- Alignment: Title centered; Body left-aligned or centered; Annotation right-aligned. / 对齐方式

---

## Font File Placement / 字体文件放置说明

Future font files go in `assets/fonts/`.
Naming convention: `{font-name}-{weight}.ttf`
未来字体文件放在 `assets/fonts/`，命名规范如下：
- `songti-regular.ttf`
- `kaiti-regular.ttf`
- `noto-sans-medium.ttf`

> 📌 Only open-source commercially licensed fonts allowed. No unauthorized commercial fonts.
> 字体文件必须使用开源可商用字体，禁止使用未授权的商业字体。

---

## Changelog / 更新记录

| Version / 版本 | Date / 日期 | Notes / 说明 |
| :--- | :--- | :--- |
| v2.0 | 2026-08-19 | Aligned version with SKILL.md v2.0 / 版本号与 SKILL.md v2.0 对齐 |
| v1.2 | 2026-08-18 | Added Mode A prompt font-instruction spec / 新增模式 A prompt 字体说明规范 |
| v1.1 | 2026-08-18 | Fixed font rule conflict: EN title changed to Sans-Serif; aligned path to assets/fonts/ / 修复字体规则冲突：英文标题改为无衬线体；路径对齐至 assets/fonts/ |
| v1.0 | 2026-08-18 | Initial: Songti title + Kaiti body, anti-garble spec / 初始版本，明确宋体标题+楷体正文，新增防乱码规范 |
