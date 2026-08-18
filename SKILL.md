---
name: cinema-summary-poster
description: |
  Generate a cinematic summary poster featuring classic quotes, core themes, and reviews based on the user's movie/TV series input and scene requirements.
  Supports two output modes: (A) return a ready-to-use image-generation prompt (default, no API key needed); (B) directly generate the image using the user's own API key (key used once, never stored).
  根据用户输入的影视作品名称及场景需求，生成包含经典台词、主旨思想、评价信息的电影级总结海报。
  支持两种出图模式：(A) 返回可直接使用的生图 Prompt（默认，无需配置 API Key）；(B) 用户提供自备生图 API Key 直接生图（Key 仅本次使用，不保存不泄露）。

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
    - A. Return Prompt — AI generates a detailed prompt; user takes it to MJ / Jimeng / SD etc. to generate the image (Default) / 返回 Prompt — 我生成详细 prompt，你自己拿去 MJ/即梦/SD 等生图（默认）
    - B. Direct Generation — user provides their own image-generation API key; AI outputs the image directly / 直接生图 — 你提供自己的生图 API Key，我直接出图
    - (Ask only if B is selected: which platform? what is the API key?) /（用户选 B 时才追问：用哪个平台？API Key 是什么？）
    - Notice to user: the key is used only this once, never stored or leaked / 提示用户：Key 仅本次使用，不会存储或泄露

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
- Clear hierarchy with size/weight variations (Title > Subtitle > Body > Notes) / 不同层级文字有主次、粗细变化（标题 > 副标题 > 正文 > 注释）

## Procedure / 执行步骤

### Step -1: Security Check (MUST EXECUTE) / 安全检查（必须执行）
1. Check user input for suspected API Keys, Tokens, passwords, etc. If the user voluntarily provides a key for Mode B, proceed to Step 0.5 with the security notice; if a key appears in any other context, ask the user to remove it. / 检查用户输入是否包含疑似 API Key、Token、密码等敏感字符串。若用户为模式 B 主动提供 Key，按 Step 0.5 流程处理并给出安全告知；若 Key 出现在其他上下文，提示用户撤回。
2. Check user input for real PII (names, private emails, local usernames). / 检查用户输入是否包含真实姓名、私人邮箱、电脑用户名等 PII 信息。
3. Check whether `.env` exists (OPTIONAL): if it exists with `CINEMA_POSTER_API_KEY`, that key is for the developer's own testing only; if missing, DO NOT terminate — default to Mode A. / 检查 `.env` 是否存在（可选）：若存在且含 `CINEMA_POSTER_API_KEY`，该 Key 仅供开发者自测；若不存在，不终止，默认走模式 A。
4. If PII or unexpected sensitive-info checks fail, TERMINATE immediately and prompt the user to correct. / 若 PII 或非预期敏感信息检查失败，立即终止执行并提示用户修正。

### Step 0: Requirement Confirmation (MUST EXECUTE) / 需求确认（必须执行）
Confirm the following with user at once (do not ask one by one):
向用户一次性确认以下信息（不要逐条追问）：

> Please confirm the following poster details, I will generate based on this:
> 请确认以下海报信息，我会据此生成：
> 1. 🎬 Film Name / 影片名称：___
> 2. 🎥 Scene Requirements / 场景需求：___
> 3. 🎨 Base Style / 基本风格：___ (Default: Auto-match / 默认根据影片自动匹配)
> 4. 📐 Aspect Ratio / 画幅比例：___ (Default: 3:4 Portrait / 默认 3:4 竖版)
> 5. 💬 Classic Quote / 经典台词：___ (Default: AI selected / 默认由我选取)
> 6. 💡 Core Theme / 主旨思想：___ (Default: AI extracted / 默认由我提炼)
> 7. ⭐ Review Info / 评价信息：___ (Default: Rating + short review / 默认含评分+一句短评)
> 8. 📝 Which of 5-7 to keep/remove? / 以上 5-7 项，哪些需要保留/去掉？
> 9. 🔤 Font Requirements / 字体要求：___ (Default: Songti title + Kaiti body / 默认宋体标题+楷体正文)
> 10. 📜 Paper Texture / 背景纸张材质：___ (Default: Auto-match / 默认根据剧情匹配)
> 11. 💧 Add Watermark? / 是否添加水印：___ (Default: No / 默认不添加)
> 12. 🖌️ Special Style / 特殊风格：___ (Default: None / 默认不使用)
> 13. 🖼️ Output Mode / 出图模式：___ (A. Return Prompt, default / B. Direct generation, provide your own key / A. 返回 Prompt，默认 / B. 直接生图，需提供自备 Key)
>
> Reply "Confirm" or modify items accordingly.
> 回复"确认"或修改对应项即可。

Wait for user confirmation before proceeding.
等待用户确认后再进入下一步。

### Step 0.5: Output Mode Branch / 出图模式分叉
- If user chose A (Return Prompt) / 若用户选 A（返回 Prompt）:
  Follow the original flow (Steps 1-4) to compose the full prompt (visual description + style + palette + text hierarchy + font specs + aspect ratio), output it in Step 7, then end. No API key is needed at any point. / 按原有流程（Step 1-4）生成完整 prompt（画面描述+风格+配色+文字层级+字体说明+画幅参数），在 Step 7 输出后结束。全程无需任何 API Key。
- If user chose B (Direct Generation) / 若用户选 B（直接生图）:
  1. Confirm the API platform (e.g., Tongyi Wanxiang / Jimeng / Stable Diffusion / DALL·E). / 确认 API 平台（如：通义万相 / 即梦 / Stable Diffusion / DALL·E 等）。
  2. Ask the user to provide that platform's API key, with a clear notice: used only this once, never stored, never leaked. / 请用户提供该平台的 API Key，并明确告知：仅本次使用，不保存不泄露。
  3. Call the platform's image-generation interface with the composed prompt. / 调用对应平台的生图接口，传入已生成的 prompt。
  4. Return the generated image; on failure (no network/tool capability, invalid key, quota exhausted, timeout), fall back to "Return Prompt" mode and explain. / 返回生成图片；若失败（无联网/工具能力、Key 无效、配额耗尽、超时），回退到"返回 Prompt"模式并说明原因。

### Step 1: Film Analysis & Style Tone Setting / 影片分析与风格定调
**Reference: references/style-guide.md**

Based on confirmed film name:
根据确认后的影片名称：
1. Analyze genre (Sci-fi/Romance/Suspense/Animation/Period/War, etc.) / 分析影片类型
2. Determine overall visual style tone / 确定整体视觉风格基调
3. Determine paper texture (ref: references/style-guide.md) / 确定背景纸张材质
4. Determine color scheme (primary, secondary, accent) / 确定色彩方案

**Style Matching Reference (Strictly follow):**
风格匹配参考（严格遵循）：
- **Epic / Period (史诗/古装):**
  - Visual Style: Film grain, Oil painting texture / 胶片质感、油画质感
  - Paper Texture: Parchment, Xuan paper / 羊皮纸、宣纸
- **Sci-fi / Cyberpunk (科幻/赛博):**
  - Visual Style: 3D render, Digital style / 3D渲染、数字风格
  - Paper Texture: Plain electronic background (Dark/Simple) / 普通电子背景色（深色/极简）
  - Note: Avoid "Matrix" code rain or flashy tech elements. Keep it clean. / 注意：避免代码雨等过度科幻元素，保持简洁。
- **Indie / Romance (文艺/爱情):**
  - Visual Style: Watercolor, Film photography / 水彩、胶片摄影
  - Paper Texture: Watercolor paper, Sketch paper / 水彩纸、素描纸
- **Animation / Comedy (动画/喜剧):**
  - Visual Style: Illustration, Comic style / 插画、漫画风格
  - Paper Texture: Coated paper, Print paper / 铜版纸、打印纸
- **Suspense / Thriller (悬疑/惊悚):**
  - Visual Style: High contrast, Dark tone, Noir / 高对比、暗调、黑色电影风
  - Paper Texture: Kraft paper, Vintage paper / 牛皮纸、复古怀旧纸
- **Documentary (纪录片):**
  - Visual Style: Realistic, Photojournalism / 写实、纪实摄影风
  - Paper Texture: Sketch paper, Print paper / 素描纸、打印纸

### Step 2: Visual Composition Design / 画面构图设计
Character Design (if applicable):
人物设计（如涉及）：
- Restore character appearance per film/TV settings, matching actions/expressions to plot / 按照电影/电视剧人物设定还原形象，动作、神态与剧情匹配
- Costumes/props match settings, reasonable interaction between characters / 服装、道具符合剧情设定，不同人物之间的动作要素合理搭配
- Height proportions match settings, clear, realistic, natural details / 身高比例符合剧情设定，细节刻画清晰、真实、自然

Background Scene Design:
背景场景设计：
- Restore scene per plot, logical, color style matches tone / 按照剧情设定还原场景，符合逻辑，色彩风格符合剧情调性
- Reasonable composition, clear natural details, logical lighting, correct perspective / 构图合理，细节清晰自然，光影符合逻辑，透视正确

Scene Scale Handling:
场景尺度处理：
- Macro (large scene, small characters): Correct proportions, spatial depth, emotional expression without breaking plot / 宏观场景：人物比例正确，体现空间感和纵深感，情感表达到位且不脱离剧情
- Standard (small scene, small characters): Reasonable composition, correct proportions, clear natural details, emotional expression without breaking plot / 普通场景：构图合理，人物比例正确，细节清晰自然，情感表达到位且不脱离剧情

### Step 3: Typography & Text Layout / 文字内容编排
Based on text content confirmed in Step 0:
根据 Step 0 确认的文字内容：
1. Determine text hierarchy: Title (film name) → Subtitle (quote/theme) → Body (review/explanation) → Notes (source/credit) / 确定文字层级
2. Assign fonts per Font Rules / 按字体规则分配字体
3. Determine text position (top/center/bottom/side) / 确定文字在画面中的位置
4. Ensure text area does not conflict with main visual / 确保文字区域与画面主体不冲突
5. In Mode A, all font/layout requirements must be written into the prompt as text instructions, and post-processing text overlay is recommended for complex text. / 模式 A 下，所有字体/排版要求必须以文字指令写入 prompt，并建议复杂文字后期叠字。

### Step 4: Overall Style Integration / 整体风格融合
- Overall style must match plot setting, paper texture unified with visual style / 整体风格必须符合剧情设定，背景纸张材质与画面风格统一
- Style should be moderate, not overpowering / 风格显现适度，不要喧宾夺主
- No flashy cluttered elements, prioritize simplicity and clarity / 不要花哨繁杂堆砌元素，以简洁明了为核心原则

### Step 5: Watermark Processing (If requested) / 水印处理（如用户要求添加）
- Color: Light gray or light blue / light Morandi blue / 颜色：浅灰色 或 浅蓝色 / 浅莫兰迪蓝色
- Design: Clean and simple, no complex embossing, minimal text/elements / 设计：简洁明了，不要立体浮雕等复杂效果，尽量不要出现文字或过多元素堆砌
- Size/Position: Moderate proportion, centered, single watermark, no stacking, does not affect readability / 大小/位置：比例适中，画面中央居中，单水印设计，不重复叠加，不影响阅读体验

### Step 6: Special Style Processing (If requested) / 特殊风格处理（如用户要求）
Optional special styles, confirm with user before use:
以下为可选特殊风格，需提前与用户沟通确认后使用：
- Watercolor: Chinese ink wash / 国风水彩、水墨风
- Comic: Japanese manga, Chinese comic / 日式漫画、国风漫画
- Oil Painting: Realistic, Expressive, Impressionist / 写实油画、写意油画、印象派
- Sketch: Pencil, Charcoal / 铅笔素描、炭笔素描
- Abstract: Color blocks, Graffiti, Collage, Montage, Big-character poster / 大色块拼接、涂鸦、拼贴、蒙太奇、大字报
- Illustration: Flat, Textured, Vector / 扁平插画、肌理插画、矢量插画

When using special styles, apply uniformly to overall effect (including image and characters).
使用特殊风格时，整体效果（包括图像和人物）统一采用该风格。

### Step 7: Generation & Self-Check / 生成与自检
- Mode A: Output the complete structured prompt (visual + text + parameters), then self-check the prompt for completeness. / 模式 A：输出完整结构化 prompt（画面+文字+参数），并自检 prompt 完整性。
- Mode B: Generate the image, then self-check each item below. / 模式 B：生成图片后，逐项自检：

Self-check list / 自检清单：
- [ ] No typos, no garbled text / 文字无错别字、无乱码
- [ ] Clear font hierarchy (size/weight variations) / 字体层级清晰（粗细、大小有变化）
- [ ] Appropriate letter spacing, not crowded / 字间距适当，排版不拥挤
- [ ] Character appearance matches original setting / 人物形象符合原片设定
- [ ] Background scene matches plot logic / 背景场景符合剧情逻辑
- [ ] Lighting, perspective correct / 光影、透视正确
- [ ] Overall style matches film tone / 整体风格贴合影片调性
- [ ] Paper texture unified with style / 纸张材质与风格统一
- [ ] Watermark (if any) positioned reasonably, does not interfere with reading / 水印（如有）位置合理、不干扰阅读
- [ ] Correct aspect ratio (Default: 3:4) / 画幅比例正确（默认 3:4）
- [ ] Mode A: prompt includes style, palette, text hierarchy, font specs and aspect ratio / 模式 A：prompt 包含风格、配色、文字层级、字体说明与画幅参数
- [ ] Mode B: user's key is NOT written to any file, log, or reply / 模式 B：用户 Key 未写入任何文件、日志或回复

If any item fails, correct and regenerate (Mode B failure triggers fallback to Mode A).
如任一项不通过，修正后重新生成（模式 B 失败时触发回退到模式 A）。

### Step 8: Delivery & Confirmation / 交付与确认
- Mode A: Deliver the prompt text and ask whether the user needs adjustments. / 模式 A：交付 prompt 文本，并询问是否需要调整。
- Mode B: Deliver the image (plus the prompt for the user's backup) and ask: / 模式 B：交付图片（附 prompt 供用户留档），并询问：

> Poster generated, please check:
> 海报已生成，请检查：
> 1. Is text content accurate? / 文字内容是否准确？
> 2. Satisfied with visual style? / 画面风格是否满意？
> 3. Need any detail adjustments? / 是否需要调整任何细节？
>
> Specify changes directly, I will regenerate.
> 如需修改请直接说明，我会重新生成。

## API Key Security Redlines / API Key 安全红线
1. The user's API key is used only within this session; it is NEVER written to any file, log, or reply record. / 用户的 API Key 仅在本次会话内使用，绝不写入任何文件、日志或回复记录。
2. NEVER record, restate, or display the user's complete API key. / 绝不记录、复述、展示用户的完整 API Key。
3. NEVER use the developer's API key to generate images on behalf of the user. / 绝不使用开发者的 API Key 替用户生图。
4. If the user has not voluntarily provided a key, ALWAYS use "Return Prompt" mode; never proactively demand a key. / 用户未主动提供 Key 时，一律走"返回 Prompt"模式，不主动索要。
5. If the runtime environment lacks HTTP/image-generation tooling, automatically fall back to "Return Prompt" mode. / 若运行环境不具备联网/生图工具能力，自动回退到"返回 Prompt"模式。

## Output format / 输出格式
- Mode A (default) / 模式 A（默认）:
  - Structured prompt text (image description + style/palette + text hierarchy + font specs + aspect ratio + negative hints). / 结构化 prompt 文本（画面描述+风格/配色+文字层级+字体说明+画幅参数+负面提示）。
  - Can be saved as .md or .txt; ready to paste into MJ / Jimeng / SD / DALL·E. / 可保存为 .md 或 .txt，可直接粘贴到 MJ/即梦/SD/DALL·E 使用。
- Mode B / 模式 B:
  - A static poster image. Aspect Ratio: Default 3:4, options 4:3, 1:1, 16:9, 9:16 / 静态海报图片，画幅默认 3:4，可选 4:3、1:1、16:9、9:16
  - Image Style: Cinematic visual quality / 图片风格：电影级视觉品质
  - Text Content: Film name + Classic quote + Core theme + Review (per user selection) / 文字内容：片名 + 经典台词 + 主旨思想 + 评价（按用户确认取舍）
  - File Format: PNG or JPG; short side ≥ 1080px recommended / 文件格式：PNG 或 JPG，建议短边 ≥ 1080px

## Definition of done / 完成标准
- [ ] User confirmed all required and optional inputs, including output mode / 用户确认了所有必填和可选输入项（含出图模式）
- [ ] Output mode executed accordingly (A: prompt delivered; B: image delivered) / 按确认的出图模式执行（A 交付 prompt；B 交付图片）
- [ ] Mode B: user's key used once only, never stored or displayed / 模式 B：用户 Key 仅用一次，未存储未展示
- [ ] On Mode B failure, fell back to Mode A with a clear explanation / 模式 B 失败时成功回退模式 A 并说明原因
- [ ] Visual style matches film genre / 画面风格与影片类型匹配
- [ ] Text content accurate, no typos, no garbled text / 文字内容准确、无错别字、无乱码
- [ ] Clear font hierarchy, concise readable layout / 字体层级清晰，排版简洁易读
- [ ] Characters/scenes match original setting (if applicable) / 人物/场景符合原片设定（如涉及）
- [ ] Lighting, perspective, proportions correct / 光影、透视、比例正确
- [ ] Paper texture unified with style, not overpowering / 纸张材质与风格统一且不喧宾夺主
- [ ] Watermark (if any) meets specs / 水印（如有）符合规范
- [ ] Correct aspect ratio / 画幅比例正确
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
- examples/good-example.md: Positive and negative examples, including a Mode A prompt example / 正例与反例参考（含模式 A prompt 范例）
- assets/README.md: Asset resource usage guide / 素材资源使用说明

All above files are created and maintained in their respective directories.
以上文件均已创建并维护在各自目录中。
