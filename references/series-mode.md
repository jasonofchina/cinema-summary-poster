# 🎞️ Series / Episode Mode / 系列与分集模式规范

> 用途：支持"给一部剧的多集""给系列作品""给某导演/演员作品集"批量生成风格统一的海报。
> Purpose: Batch-generate style-consistent posters for multiple episodes, a film series, or a director's/actor's filmography.

---

## Trigger Scenarios / 触发场景

用户在需求确认时表达以下意图之一，即进入系列模式：
Enter series mode when the user expresses any of the following during requirement confirmation:

1. 给《XX》第 1-8 集各做一张 / One poster per episode (e.g., Ep 1-8)
2. 给《XX》系列作品做一套海报 / A set for a film series
3. 给某导演/演员的作品集做系列海报 / A series for a director's/actor's filmography

---

## Core Rules / 核心规则

### 1. 风格统一 / Style Consistency
- 整个系列共用同一套风格：色调、字体、纸张材质、构图骨架完全一致。
  The entire series shares one style system: palette, fonts, paper texture, and composition skeleton identical.
- 只有分集之间的"差异化信息"（片名/台词/配图元素）变化。
  Only per-episode differentiated info (title/quote/visual motif) changes.

### 2. 命名规范 / Naming Convention
- 单片：`{作品名}-{集数}.png`，如 `《长安十二时辰》-第3集.png`
  Single: `{Title}-{Episode}.png`
- 系列：`{系列名}-{序号}-{片名}.png`
  Series: `{SeriesName}-{Index}-{Title}.png`

### 3. 进度中断处理 / Mid-progress Interruption
- 批量生成中途失败或用户打断时，记录已完成的集数。
  If interrupted, record which episodes are already done.
- 续做时从断点继续，已完成的不重复生成。
  Resume from the breakpoint; do not regenerate completed ones.

### 4. 跨集剧透防护 / Cross-episode Spoiler Protection
- 分集海报的台词/主旨只引用"本集及之前"的内容，不得剧透后续剧情。
  Per-episode quotes/themes must only reference content up to that episode; never spoil later plots.

---

## Configurable Items / 可配置项

| 项 / Item | 说明 / Notes |
| :--- | :--- |
| 集数范围 / Episode range | 第几集到第几集 |
| 统一风格 / Unified style | 是否强制统一（默认是） |
| 差异化元素 / Differentiated element | 每集变什么（台词/配图/评分） |
| 输出节奏 / Output pace | 一次全出，还是分批出 |

---

## Changelog / 更新记录

| Version | Date | Notes |
| :--- | :--- | :--- |
| v2.0 | 2026-08-19 | Aligned version with SKILL.md v2.0 / 与 SKILL.md v2.0 对齐 |
| v1.0 | 2026-08-18 | Initial release / 初始版本 |
