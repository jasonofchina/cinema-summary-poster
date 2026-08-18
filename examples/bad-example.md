# ❌ Bad Examples / 反例参考（避坑对照）

> 配合 `good-example.md` 使用，左侧错误、右侧正确，快速对照避坑。
> Use alongside `good-example.md`: left = wrong, right = correct.

---

| # | ❌ 错误做法 / Wrong | ✅ 正确做法 / Correct |
| :--- | :--- | :--- |
| 1 | 科幻片用了宣纸背景 / Sci-fi with Xuan paper bg | 科幻用深色纯色电子背景 / Dark solid electronic bg |
| 2 | 英文片名用宋体（笔画粘连）/ EN title in Songti | 英文用无衬线体 / EN title in Sans-Serif |
| 3 | 一张海报用 5 种字体 / 5 fonts on one poster | 最多 3 种：宋体标题+楷体正文+宋体注释 |
| 4 | 台词压在人物脸上 / Quote overlaid on face | 文字放留白区，避开主体 / Text in whitespace |
| 5 | 生成真实明星脸 / Real celebrity likeness | 风格化/插画化处理 / Stylized treatment |
| 6 | 画面堆满 10+ 元素 / 10+ elements clutter | 主体≤5 个，留白≥20% |
| 7 | prompt 缺字体说明 / Prompt missing font specs | 含字体说明 + 后期叠字提示 |
| 8 | 存储/复述用户 API Key / Storing user key | 仅用一次，不存储不展示，失败回退模式 A |

---

## Changelog / 更新记录

| Version | Date | Notes |
| :--- | :--- | :--- |
| v1.0 | 2026-08-18 | Initial release / 初始版本（从 good-example.md 的 Pitfall Checklist 拆分） |
