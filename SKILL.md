---
name: cinema-summary-poster
description: |
  Generate a cinematic summary poster featuring classic quotes, core themes, and reviews based on the user's movie/TV series input and scene requirements.
  根据用户输入的影视作品名称及场景需求，生成包含经典台词、主旨思想、评价信息的电影级总结海报。
  
  Trigger words: "movie poster", "cinema summary poster", "movie recap visual", "电影海报", "剧集总结", "影视总结", "总结海报", "影视总结图".
  触发词：包含"电影海报""剧集总结""影视总结""总结海报""cinema summary poster""movie recap visual""影视总结图"等关键词。
  
  Exclusions: Not for pure text reviews, generic non-film images, minor layout tweaks of existing designs, commercial/event posters, or content containing real PII.
  排除条件：不用于纯文字影评生成；不用于非影视题材的通用图片生成；不用于已有完整设计稿的微调排版；不用于通用商业海报、活动海报、产品宣传图设计；不用于包含真实个人信息的内容生成。
---

# Cinema Summary Poster Generator / 影视总结海报生成器

## Goal / 目标
Generate a cinematic visual-quality summary poster based on the user's movie/TV series name and scene requirements.
根据用户提供的电影或电视剧名称及场景需求，生成一张电影级视觉品质的总结海报。

The poster must integrate the following core information (subject to user confirmation):
海报需融合以下核心信息（具体由用户确认取舍）：
- A classic quote / 一句经典台词
- Core theme / meaning / 主旨思想 / 意义阐释
- Film reviews / ratings / 影片评价 / 评分
- Other user-specified content / 其他用户指定内容

The final output is a ready-to-use poster image with integrated text and visuals, matching the original film's tone.
最终产出为一张可直接使用的成品海报图片，文字与画面一体，风格贴合原片调性。

## When to use / 触发条件
Trigger this Skill when the user expresses the following intents:
当用户表达以下意图时触发本 Skill：
- "Help me make a summary poster for [Movie Name]" / "帮我做一张《XXX》的总结海报"
- "Generate a movie recap visual" / "生成一部电影的影视总结图"
- "Make a poster for this show with a classic quote and theme" / "给这部剧做一张海报，要有经典台词和主旨"
- Contains keywords like "movie poster", "cinema summary poster", "movie recap visual", "电影海报", "剧集总结", "影视总结", "cinema summary poster", "movie recap visual" / 包含相关中英文关键词

## Do not use / 排除条件
- User only requests pure text reviews or essays (no image needed) / 用户仅要求纯文字影评、观后感文章（无图片需求）
- User requests generic illustrations, landscapes, commercial/event posters unrelated to film/TV / 用户要求生成与影视无关的通用插画、风景图、商业海报、活动海报
- User already has a complete design and only needs minor font/color tweaks / 用户已有完整设计稿，仅需微调字体大小或颜色
- User requests videos, GIFs, or non-static formats / 用户要求生成视频、动图、GIF 等非静态图片格式
- User only mentions "poster" without any film/TV title / 用户仅提及 "poster" 但未关联任何影视作品名称
- User requests real PII (names, private emails, local usernames, real test data) in the poster / 用户要求在海報中包含真实姓名、私人邮箱、电脑用户名、真人测试数据等个人信息

## Inputs to collect / 需要收集的信息

### Required (Prompt user if missing) / 必填项（缺失时主动询问）
1. Movie/TV Series Name: Accurate title, preferably with year/season (Default: None) / 电影/电视剧名称：准确片名，含年份或季数更佳（默认：无）
2. Scene Requirements: Specific visual scene desired (Default: None) / 场景需求：用户希望呈现的具体画面场景（默认：无）
3. Base Style: e.g., "Film grain", "3D render", "Ink wash" (Default: Auto-match by genre) / 基本风格：如"胶片质感""3D渲染""水墨风"等（默认：根据影片类型自动匹配）
4. Aspect Ratio: Output width/height ratio (Default: 3:4 Portrait) / 画幅比例：输出图片宽高比（默认：3:4 竖版）

### Optional (Confirm with user) / 可选项（需主动询问用户确认）
5. Classic Quote: User-specified or AI-selected (Default: AI selects the most iconic) / 经典台词：用户指定 or 由 AI 选取（默认：AI 选取最经典一句）
6. Core Theme: User-specified or AI-extracted (Default: AI extracts one sentence) / 主旨思想：用户指定 or 由 AI 提炼（默认：AI 提炼一句话）
7. Review Info: Ratings, short reviews, awards (Default: Douban/IMDb rating + one short review) / 评价信息：评分、短评、获奖记录等（默认：豆瓣/IMDb 评分 + 一句短评）
8. Text Content Selection: Which of 5-7 to include/exclude (Default: Include all) / 文字内容取舍：以上 5-7 项哪些要、哪些不要（默认：全部包含）
9. Font Requirements: Title/body fonts, special fonts (Default: See Font Rules below) / 字体要求：标题字体、正文字体、是否特殊字体（默认：见下方字体规则）
10. Paper Texture: Parchment/Xuan paper/Coated paper/Sketch paper, etc. (Default: Auto-match by style) / 背景纸张材质：羊皮纸/宣纸/铜版纸/素描纸等（默认：根据剧情风格自动匹配）
11. Watermark: Whether to add, color preference (Default: None) / 是否添加水印：以及水印颜色偏好（默认：不添加）
12. Special Styles: Watercolor/Comic/Oil/Sketch/Abstract/Illustration (Default: None) / 特殊风格：水彩/漫画/油画/素描/抽象/插画（默认：不使用）

### Font Rules (Details for Item 9) / 字体规则（第 9 项展开）
**Reference: references/font-spec.md**

**Default Scheme (No special request):**
默认方案（用户无特殊要求时）：
- Title/Subtitle: **Songti (Serif) Regular** for Chinese; **Sans-Serif** for English (to prevent garbled text). / 标题 / 小标题：**中文宋体 常规**；**英文无衬线体**（防乱码）。
- Body: **Kaiti (Script) Regular** / 正文内容：**楷体 常规**

**Special Font Handling:**
特殊字体处理：
- If user requests calligraphy/art fonts: Use AI to generate font effects. / 若用户要求书法体/艺术字：使用 AI 生成字体效果。
- **Constraint:** Strictly no garbled text, missing characters, or merged strokes. If readability drops, suggest downgrading to default fonts. / **约束：** 严禁出现乱码、缺字、笔画粘连。若可读性下降，建议降级为默认字体。

**Typography Requirements:**
通用排版要求：
- Reasonable, concise, clear layout with appropriate letter spacing / 文字排版合理、简洁、清晰，字间距适当
- No typos, no garbled text, clear and readable theme / 无错别字、无乱码，主题清晰易读
- Font size adapts to aspect ratio and content volume / 字体大小适配画面比例和内容量
- Clear hierarc

