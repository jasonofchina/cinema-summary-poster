---
name: cinema-summary-poster
description: |
  Generate a cinematic summary poster featuring classic quotes, core themes, and reviews based on the user's movie/TV series input and scene requirements.
  Supports two output modes: (A) return a ready-to-use image-generation prompt (default, no API key needed); (B) directly generate the image using the user's own API key (key used once, never stored).
  根据用户输入的影视作品名称及场景需求，生成包含经典台词、主旨思想、评价信息的电影级总结海报。
  支持两种出图模式：(A) 返回可直接使用的生图 Prompt（默认，无需配置 API Key）；(B) 用户提供自备生图 API Key 直接生图（Key 仅本次使用，不保存不泄露）。

  New in v2.0: quote candidate pool (3-choose-1), configurable rating sources, series/episode batch mode, plain-text summary card pre-confirmation, and built-in negative prompts.
  版本 v2.0 新增：台词备选池（三选一）、评分数据源可配置、系列/分集批量模式、纯文字摘要卡出图前确认、内置负面提示词库。

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

The final deliverable depends on the output mode:
最终交付物取决于出图模式：
- Mode A (default): a ready-to-use image-generation prompt (text). / 模式 A（默认）：可直接使用的生图 Prompt（文本）。
- Mode B: a ready-to-use poster image with integrated text and visuals. / 模式 B：文字与画面一体的成品海报图片。

## When to use / 触发条件
Trigger this Skill when the user expresses the following intents:
当用户表达以下意图时触发本 Skill：
- "Help me make a summary poster for [Movie Name]" / "帮我做一张《XXX》的总结海报"
- "Generate a movie recap visual" / "生成一部电影的影视总结图"
- "Make a poster for this show with a classic quote and theme" / "给这部剧做一张海报，要有经典台词和主旨"
- Contains keywords like "movie poster", "cinema summary poster", "movie recap visual", "电影海报", "剧集总结", "影视总结", "影视总结图" / 包含相关中英文关键词

## Do not use / 排除条件
- User only requests pure text reviews or essays (no image needed) / 用户仅要求纯文字影评、观后感文章（无图片需求）
- User requests generic illustrations, landscapes, commercial/event posters unrelated to film/TV / 用户要求生成与影视无关的通用插画、风景图、商业海报、活动海报
- User already has a complete design and only needs minor font/color tweaks / 用户已有完整设计稿，仅需微调字体大小或颜色
- User requests videos, GIFs, or non-static formats / 用户要求生成视频、动图、GIF 等非静态图片格式
- User only mentions "poster" without any film/TV title / 用户仅提及 "poster" 但未关联任何影视作品名称
- User requests real PII (names, private emails, local usernames, real test data) in the poster / 用户要求在海报中包含真实姓名、私人邮箱、电脑用户名、真人测试数据等个人信息

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
13. Output Mode (choose one) / 出图模式（二选一）:
    - A. Return Prompt — AI generates a detailed prompt; user takes it to MJ / Jimeng / SD etc. to generate the image (Default) / 返回 Prompt — AI 生成详细 prompt，用户拿去 MJ/即梦/SD 等出图（默认）
    - B. Direct Generation — user provides their own image-gen API key; AI generates directly (key used once, never stored) / 直接生图 — 用户提供自备生图 API Key，AI 直接出图（Key 仅本次使用，不保存不泄露）
14. Quote Candidate Pool (Optional; Default: AI selects the most iconic one) / 台词备选池（可选；默认：AI 选最经典一句）
    - AI proposes 3 candidate quotes (tagged: philosophical / emotional / plot), user picks one. / AI 给出 3 句候选台词（标注类型：哲理 / 情感 / 剧情），用户三选一。
    - If user does not specify, use the first (most iconic) quote. / 用户未指定时，默认采用第 1 句（最经典）。
15. Rating Source (Optional; Default: Douban + IMDb) / 评分数据源（可选；默认：豆瓣 + IMDb）
    - Options: Douban / IMDb / Rotten Tomatoes / Maoyan / Mtime; awards display (Oscar / Palme d'Or / HKFA) optional. / 可选：豆瓣 / IMDb / 烂番茄 / 猫眼 / 时光网；是否展示获奖记录（奥斯卡 / 金棕榈 / 金像奖）可选。

## Font Rules / 字体规则
- Chinese title: Songti (Serif). / 中文标题：宋体。
- English title: Sans-Serif (to avoid AI stroke merging). / 英文标题：无衬线体（避免 AI 笔画粘连）。
- Chinese body: Kaiti (Script). / 中文正文：楷体。
- Annotation: Songti Light. / 注释：宋体 Light。
- Never use >3 fonts per poster. / 单张海报不超过 3 种字体。
- Complex text (>6 chars title, rare characters): generate background first, overlay text in post-processing. / 复杂文字（片名超 6 字、生僻字）：先出背景图，再后期叠字。

## Security Rules / 安全规范（API Key 处理）
1. User's API key is used only within the current session; never written to files, logs, or reply records. / 用户的 API Key 仅在本次会话内使用，绝不写入任何文件、日志或回复记录。
2. Never record, restate, or display the user's full API key. / 绝不记录、复述、展示用户的完整 API Key。
3. Never use the developer's API key to generate images for users. / 绝不使用开发者的 API Key 替用户生图。
4. When the user does not proactively provide a key, always use Mode A; do not solicit keys. / 用户未主动提供 Key 时，一律走模式 A，不主动索要。
5. On Mode B failure (invalid key / quota exhausted / timeout / no external API capability), fall back to Mode A and output the full prompt. / 模式 B 失败（Key 无效 / 配额耗尽 / 超时 / 环境不支持外部 API）时，回退模式 A 并输出完整 prompt。

## Workflow / 工作流

### Step -1: Security Check / 安全检查
- Detect PII in user input; refuse generation and prompt to use fictional content if real PII detected. / 检测用户输入中的个人信息；若发现真实 PII，拒绝生成并提示改用虚构内容。
- Check `.env` (optional): missing → Mode A. If exists with a developer key, it is for developer self-testing only, never used to generate for users. / 检查 `.env`（可选）：缺失则走模式 A；若存在开发者 Key，仅供开发者自测，不用于替用户生图。

### Step 0: Requirement Confirmation / 需求确认
- Confirm the 15 items above (Required + Optional). / 确认上述 15 项（必填 + 可选）。
- If in series/episode mode, also confirm episode range, unified style, differentiated element, and output pace (see references/series-mode.md). / 若为系列/分集模式，另行确认集数范围、是否统一样式、差异化元素、输出节奏（见 references/series-mode.md）。

### Step 0.5: Output Mode Branch / 出图模式分叉
- Mode A: proceed to generate a detailed prompt. / 模式 A：进入生成详细 prompt 流程。
- Mode B: request the user's API key and platform (e.g., Tongyi Wanxiang / Jimeng / Stable Diffusion / DALL·E), then call the corresponding image API. / 模式 B：请用户提供 API Key 与平台（如通义万相 / 即梦 / Stable Diffusion / DALL·E），并调用对应生图接口。

### Step 0.6: Text Summary Card (Pre-generation Confirmation) / 纯文字摘要卡（出图前确认）
Before generating the image, output a plain-text summary card for confirmation to avoid wasting image-generation quota on wrong info:
出图前，先输出一张"纯文字摘要卡"供用户确认，避免信息错误浪费出图额度：

> 📋 海报信息摘要 / Poster Summary Card
> - 片名 / Title：___
> - 台词 / Quote：___
> - 主旨 / Theme：___
> - 评分 / Rating：___
> - 年份 / Year：___
> - 出图模式 / Mode：A / B

Proceed to Step 1 only after the user confirms (e.g., replies "确认"). / 用户确认无误（如回复"确认"）后再进入 Step 1。

### Step 1: Film Analysis & Style Tone Setting / 影片分析与风格定调
- Confirm the genre and fetch/verify basic info (year, rating, awards) via search; never fabricate data. / 确认影片类型，并通过检索获取/核对基本信息（年份、评分、获奖），绝不编造数据。
- Determine style tone and palette via references/style-guide.md. / 依据 references/style-guide.md 确定风格与配色。

### Step 2: Visual Composition Design / 画面构图设计
- Design characters + background per references/style-guide.md (whitespace ≥20%, main subjects ≤5). / 依据 references/style-guide.md 设计人物与背景（留白 ≥20%，主体 ≤5 个）。

### Step 3: Typography & Text Layout / 文字内容编排
- Apply font rules and anti-garble spec per references/font-spec.md. / 依据 references/font-spec.md 应用字体规则与防乱码规范。

### Step 4: Overall Style Integration / 整体风格融合
- Unify palette, texture, and tonal consistency. / 统一色调、质感与整体一致性。

### Step 5: Watermark Processing (Optional) / 水印处理（可选）

### Step 6: Special Style Processing (Optional) / 特殊风格处理（可选）

### Step 7: Generation & Self-Check / 生成与自检
- Mode A: write font/text requirements into the prompt (see references/font-spec.md), and append negative prompts (see references/negative-prompts.md). / 模式 A：将字体与文字要求写入 prompt（见 references/font-spec.md），并附加负面提示词（见 references/negative-prompts.md）。
- Mode B: pass negative prompts as the `negative_prompt` parameter. / 模式 B：将负面提示词作为 `negative_prompt` 参数传入。
- Self-check: key-safety items, no garbled text, no real PII. / 自检：Key 安全项、无乱码、无真实 PII。

### Step 8: Delivery & Confirmation / 交付与确认
- Mode A: deliver the complete prompt. / 模式 A：交付完整 prompt。
- Mode B: deliver the generated image. / 模式 B：交付生成的图片。
- Confirm user satisfaction. / 确认用户满意。

## Completion checklist / 完成清单
- [ ] Film/series name correct / 片名正确
- [ ] Quote, theme, rating accurate / 台词、主旨、评分准确
- [ ] Style tone matches genre / 风格贴合影片类型
- [ ] Font rules followed, no garbled text / 遵循字体规则，无乱码
- [ ] Aspect ratio correct / 画幅比例正确
- [ ] No real PII or sensitive credentials included / 未包含任何真实个人信息或敏感凭证
- [ ] User confirmed satisfaction / 用户确认满意

## Failure handling / 异常处理
- User did not provide film name: Prompt actively, do not guess / 用户未提供影片名称：主动询问，不猜测
- Film too obscure to confirm info: Inform user, ask for supplementary description or reference image / 影片过于冷门，无法确认信息：告知用户，请用户提供补充描述或参考图
- AI cannot accurately generate requested font: Inform risk, suggest similar or default font / 用户要求的字体 AI 无法准确生成：告知风险，建议换用近似字体或默认字体
- Special style severely conflicts with film tone: Explain conflict, suggest alternatives / 特殊风格与影片调性严重冲突：向用户说明冲突点，建议替代方案
- Generated result has garbled text: Regenerate immediately, do not use garbled version / 生成结果出现乱码文字：立即重新生成，不使用含乱码的版本
- User requests real person portrait: Explain limitations, suggest stylized/illustrated treatment / 用户要求添加现实人物肖像：说明生成限制，建议采用风格化或插画化处理
- User chose B but environment cannot call external APIs: Explain and fall back to Mode A, output the full prompt / 用户选 B 但环境不支持外部 API 调用：说明并回退模式 A，输出完整 prompt
- User's key invalid or quota exhausted: Do NOT retry with the developer's key; fall back to Mode A / 用户 Key 无效或配额耗尽：不用开发者 Key 重试，回退模式 A
- API call timeout: Retry once; if still failing, fall back to Mode A / API 调用超时：重试一次，仍失败则回退模式 A
- Detected unexpected API Key leak in user input: Terminate, prompt user to rotate the key / 检测到用户输入中意外泄露 API Key：终止执行，提示用户轮换密钥
- User input contains real PII: Refuse generation, prompt to modify to fictional content / 用户输入包含真实个人信息：拒绝生成，提示修改为虚构内容

## Additional resources / 配套文件引用
- references/style-guide.md: Film genre to visual style/paper material mapping spec / 影片风格与纸张材质匹配规范
- references/font-spec.md: Font usage spec, anti-garble rules and Mode A prompt font instructions / 字体使用规范、防乱码规则与模式 A prompt 字体说明
- references/negative-prompts.md: Negative prompts library, appended on generation / 负面提示词库，出图时自动附加
- references/score-sources.md: Rating source configuration / 评分数据源配置说明
- references/series-mode.md: Series/episode batch mode spec / 系列/分集模式规范
- examples/good-example.md: Positive examples, including a Mode A prompt example / 正例参考（含模式 A prompt 范例）
- examples/bad-example.md: Negative examples / 反例参考
- assets/README.md: Asset resource usage guide / 素材资源使用说明

All above files are created and maintained in their respective directories.
以上文件均已创建并维护在各自目录中。
