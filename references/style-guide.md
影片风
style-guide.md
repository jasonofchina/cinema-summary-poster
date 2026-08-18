# 🎨 Style Guide / 影片风格与视觉规范指南

> This document is the master style reference for the Cinema Summary Poster Skill.
> AI must read this file during Step 1 "Film Analysis & Style Tone Setting" before deciding on color, texture, composition, and paper material.
> All rules are written for beginners with zero design experience.
>
> 这份文档是"影视总结海报"的风格总纲。
> AI 在执行 Step 1「影片分析与风格定调」时，必须先读取本文件，再决定海报的色调、质感、构图和纸张材质。
> 所有规则都面向"完全不懂设计的小白"写成，照着抄就能用。
>
> Dual-mode note / 双模式说明: In Mode A (Return Prompt), the style descriptions from this guide must be quoted verbatim into the prompt so users can reproduce the look on any platform.
> 模式 A（返回 Prompt）下，本指南的风格描述必须原文写入 prompt，便于用户在任何平台复现画面。

---

## Genre-to-Style Mapping / 按影片类型选择风格（核心对照表）

This table is the "Style Bible" of this Skill.
Once the film genre is confirmed, follow the recommendations strictly. Do not improvise.
下面这张表是本 Skill 的"风格圣经"。只要确定了影片类型，就直接按表格里的推荐来，不要自由发挥。

| Genre / 影片类型 | Color Palette / 推荐色调 | Texture / Style / 推荐质感 | Paper Material / 推荐纸张 | Composition / 构图建议 | Forbidden Elements / 禁忌元素 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 🚀 Sci-fi / Cyberpunk / 科幻/赛博 | Deep blue, Silver gray, Neon purple, Cool white / 深蓝、银灰、霓虹紫、冷白 | 3D render, Digital glow, Minimalist geometry / 3D渲染、数字光效、极简几何 | Dark solid electronic bg (no paper texture) / 深色纯色电子背景（无纸纹） | Centered symmetry or rule of thirds, subject centered, ample whitespace / 居中对称或三分法，主体居中，留白多 | Code rain, digital streams, excessive tech elements / 代码雨、数字流、过度科技元素 |
| 🏯 Period / Epic / 古装/史诗 | Warm gold, Ochre red, Ink black, Xuan white / 暖金、赭红、墨黑、宣纸白 | Film grain, Oil brushstroke, Ink wash / 胶片质感、油画笔触、水墨晕染 | Parchment, Xuan paper / 羊皮纸、宣纸 | Vertical layering: title top, character center, notes bottom / 上下分层，标题在上、人物居中、注释在下 | Modern elements, neon fluorescent colors / 现代元素、过于鲜艳的荧光色 |
| 🌿 Indie / Romance / 文艺/爱情 | Off-white, Light gray, Haze blue, Warm orange / 米白、浅灰、雾霾蓝、暖橘 | Watercolor wash, Film grain, Soft light / 水彩晕染、胶片颗粒、柔光 | Watercolor paper, Sketch paper / 水彩纸、素描纸 | Ample whitespace, subject off-center, quote in blank area / 留白充足，人物偏侧，台词放空白处 | High saturation, strong contrast, complex FX / 高饱和度、强烈对比、复杂特效 |
| 🎨 Animation / Comedy / 动画/喜剧 | Macaron, Bright yellow, Sky blue, Grass green / 马卡龙色、明快黄、天蓝、草绿 | Flat illustration, Comic line art, Vector / 扁平插画、漫画线稿、矢量风 | Coated paper, Print paper / 铜版纸、打印纸 | Exaggerated subject scale, text wrapping or corner placement / 主体夸张放大，文字环绕或角落 | Realistic human faces, dark oppressive tones / 写实人脸、暗黑压抑色调 |
| 🌑 Suspense / Thriller / 悬疑/惊悚 | Deep black, Dark red, Cool green, Gray purple / 深黑、暗红、冷绿、灰紫 | High contrast, Film noir, Grain noise / 高对比、黑色电影、颗粒噪点 | Kraft paper, Vintage paper / 牛皮纸、复古怀旧纸 | Silhouette, partial close-up, text in shadow areas / 人物剪影、局部特写、文字放阴影处 | Bright warm tones, cute elements / 明亮温暖色调、可爱元素 |
| 📷 Documentary / 纪录片 | Natural gray, Earth tone, Low saturation / 自然灰、大地色、低饱和 | Realistic photography, Photojournalism, No filter / 写实摄影、纪实风、无滤镜 | Sketch paper, Print paper / 素描纸、打印纸 | True-to-life proportions, scene restoration / 人物真实比例、场景还原 | Over-beautification, cartoonish, exaggerated distortion / 过度美化、卡通化、夸张变形 |

> ⚠️ Note / 注意: For cross-genre films (e.g., Sci-fi + Romance), prioritize the primary genre. The secondary genre only affects minor color adjustments, not texture.
> 如果影片是"科幻+爱情"这种跨类型，优先选主类型，副类型只影响色调微调，不改变质感。

---

## Universal Design Principles / 通用设计原则

The following 5 principles apply to ALL posters without exception:
无论什么类型，以下 5 条原则不能破：

1. **Simplicity First / 简洁至上**: No more than 5 main visual elements. No clutter. / 画面元素不超过 5 个主体，不要堆砌。
2. **Style Consistency / 风格统一**: Characters, background, text, and paper must belong to the same visual system. / 人物、背景、文字、纸张必须属于同一视觉体系。
3. **Text Legibility / 文字清晰**: All text must be instantly readable, never obscured by background. / 任何文字都必须一眼能看清，不能被背景干扰。
4. **Breathing Space / 留白呼吸**: At least 20% of the poster must be whitespace or minimal. / 海报至少留 20% 区域是空白或极简。
5. **No Distraction / 不喧宾夺主**: Paper texture is auxiliary only; it must never steal focus from characters or quotes. / 背景纸张纹理只起辅助作用，不能抢走人物和台词的焦点。

---

## Special Scenario Handling / 特殊场景处理

### Multi-character Ensemble / 人物数量较多（群像海报）
- Max 3 main characters; others rendered as silhouettes or blurred. / 主要人物最多 3 个，其余做剪影或模糊处理。
- Height proportions must match original film settings. / 身高比例必须符合原片设定。

### Large-scale Epic Scene / 大场景（史诗级画面）
- Use "large scene, small characters"; characters occupy 10%-20% of frame. / 采用"大场景小人物"，人物占画面 10%-20%。
- Must convey spatial depth; avoid flat composition. / 必须体现空间纵深感，避免平面化。

### Text-only Poster (No Characters) / 纯文字海报（无人物）
- Allowed: Title + Quote + Theme only. / 允许只放片名+台词+主旨。
- Background must use paper texture or minimalist color block; never pure white. / 背景必须用纸张纹理或极简色块，不能纯白。

### User-specified Special Style / 用户指定特殊风格
- Prioritize user request. / 优先按用户要求。
- If user request severely conflicts with genre, warn user and suggest alternatives. / 如果与影片类型严重冲突，需提醒用户并给出替代方案。

---

## Quick Color Reference / 色彩搭配速查

| Scenario / 场景 | Primary / 主色 | Secondary / 辅色 | Accent / 点缀色 |
| :--- | :--- | :--- | :--- |
| Sci-fi Cool / 科幻冷峻 | Deep Blue #1a2a4a | Silver Gray #b0b8c4 | Neon Purple #8a5cf6 |
| Period Rich / 古装厚重 | Ochre Red #8b3a2e | Warm Gold #c9a86a | Ink Black #1a1a1a |
| Indie Gentle / 文艺温柔 | Off-white #f5f0e8 | Haze Blue #a8b8c8 | Warm Orange #d4956a |
| Animation Bright / 动画明快 | Sky Blue #6ac1e4 | Bright Yellow #f5d76e | Grass Green #7ec850 |
| Suspense Dark / 悬疑压抑 | Deep Black #0d0d0d | Dark Red #6e1a1a | Cool Green #2a4a3a |
| Documentary Natural / 纪录片自然 | Earth Brown #8a6f47 | Natural Gray #b0a89a | Muted Blue #6a8a9a |

> 💡 Usage / 使用方法: After confirming genre, pick one palette directly from this table. Do not create custom colors.
> 确定影片类型后，直接从上表选一组颜色，不要自行调色。

---

## Changelog / 更新记录

| Version / 版本 | Date / 日期 | Notes / 说明 |
| :--- | :--- | :--- |
| v1.1 | 2026-08-18 | Added dual-mode note: Mode A prompts must quote this guide verbatim / 新增双模式说明：模式 A prompt 需原文引用本指南 |
| v1.0 | 2026-08-18 | Initial release covering 6 genres / 初始版本，覆盖六大影片类型 |