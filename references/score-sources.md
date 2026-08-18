# ⭐ Score Sources Configuration / 评分数据源配置说明

> 用途：控制海报上"评价信息"的来源与展示方式。
> Purpose: Control the source and display of "review info" on the poster.
> 相关：对应 SKILL.md Step 0 第 7 项「评价信息」。
> Related to: SKILL.md Step 0, Item 7 "Review Info".

---

## Supported Sources / 支持的数据源

| Source / 来源 | Region / 地区 | 说明 / Notes |
| :--- | :--- | :--- |
| 豆瓣 Douban | 中国大陆 | 默认首选，评分 + 短评 |
| IMDb | 国际 | 默认次选，评分 |
| Rotten Tomatoes (RT) | 北美 | 烂番茄新鲜度 |
| 猫眼 Maoyan | 中国大陆 | 票房向评分 |
| 时光网 Mtime | 中国大陆 | 专业影评 |

---

## Default Behavior / 默认行为

- 默认：豆瓣评分 + 一句短评 + IMDb 评分。
  Default: Douban rating + one short review + IMDb rating.
- 获奖记录（奥斯卡/金棕榈/金像奖等）默认不显示，用户要求时才加。
  Awards (Oscar/Palme d'Or/HKFA) hidden by default; add only when user requests.

---

## How Users Configure / 用户如何配置

用户无需改文件，直接在对话中用自然语言声明即可，例如：
No file editing needed — users declare preferences in natural language, e.g.:

- "只用豆瓣评分" / "Only use Douban rating"
- "加上烂番茄新鲜度" / "Also add Rotten Tomatoes score"
- "展示获奖记录" / "Show awards"
- "不要评分，只要短评" / "No rating, just a short review"

AI 识别意图后，在 Step 0 确认时同步更新第 7 项。
The AI detects the intent and updates Item 7 during Step 0 confirmation.

---

## Data Retrieval Rules / 数据检索规则

1. 豆瓣、猫眼、时光网无官方 API，默认走"检索交叉核对"，无需 Key。
   Douban/Maoyan/Mtime have no official API; use search + cross-verification, no key needed.
2. IMDb / RT 如需结构化数据，可配合 OMDB API（Key 见 `.env.example`，可选）。
   For structured IMDb/RT data, optionally use the OMDB API (key in `.env.example`).
3. 检索不到评分时，明确告知用户"未查到评分"，不要编造数字。
   If no rating is found, tell the user honestly; never fabricate numbers.

---

## Changelog / 更新记录

| Version | Date | Notes |
| :--- | :--- | :--- |
| v1.0 | 2026-08-18 | Initial release / 初始版本 |
