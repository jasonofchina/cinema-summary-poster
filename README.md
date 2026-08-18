# 🎬 Cinema Summary Poster / 影视总结海报生成器

> Input a movie or TV series, and AI will generate a cinematic summary poster featuring classic quotes, core themes, and reviews.
> Two output modes: (A) return a ready-to-use image-generation prompt (default, no key needed); (B) directly generate the image with your own API key (key used once, never stored).
>
> 输入一部电影或电视剧，AI 自动生成一张包含经典台词、主旨思想、评价的电影级总结海报。
> 支持两种出图模式：(A) 返回可直接使用的生图 Prompt（默认，无需 Key）；(B) 用你自备的 API Key 直接生图（Key 仅本次使用，不保存不泄露）。

## Core Philosophy / 核心理念
Style serves the story; simple but not simplistic. Sci-fi has digital texture, period dramas carry the charm of Xuan paper, and indie films hold the warmth of watercolors.
每张海报都应贴合原片调性——科幻片有数字质感，古装片有宣纸韵味，文艺片有水彩温度。风格服务于故事，简洁而不简单。

## ⚠️ Pre-release Security Checklist / 发布前必做安全检查
Before every commit or release, the following MUST be executed:
每次提交代码或发布新版本前，必须执行：

1. **Desensitization Review / 脱敏审查**: Check line-by-line for real names, private emails, local usernames, or real test data.
   逐行检查是否包含真名、私人邮箱、电脑用户名、真人测试数据。
2. **GitGuardian Scan / GitGuardian 扫描**: Automated CI/CD pipeline check. Merging is strictly prohibited if failed.
   CI/CD 流水线自动检测，未通过禁止合并。
3. **API Key Validation / API Key 验证**: Ensure no hardcoded keys; `.env` is optional and for developer self-testing only.
   确认无硬编码密钥；`.env` 为可选项，仅供开发者自测。
4. **User Key Handling / 用户 Key 处理**: Confirm the Skill never stores, logs, or restates user-provided keys; Mode B falls back to Mode A on any failure.
   确认 Skill 不存储、不记录、不复述用户提供的 Key；模式 B 失败时回退模式 A。
5. **Quota Check / 限额检查**: Confirm API Key rate limits are set, and log the last rotation date.
   确认 API Key 已设置调用上限，并记录上次轮换日期。

## Workflow / 工作流
- **Step -1**: Security Check (PII detection; `.env` optional, missing → Mode A) / 安全检查（PII 检测；`.env` 可选，缺失自动走模式 A）
- **Step 0**: Requirement Confirmation (13 items incl. output mode) / 需求确认（含出图模式共 13 项）
- **Step 0.5**: Output Mode Branch (A: return prompt / B: direct generation with user key, fallback on failure) / 出图模式分叉（A 返回 prompt / B 用户自带 Key 直接生图，失败回退）
- **Step 1**: Film Analysis & Style Tone Setting / 影片分析与风格定调
- **Step 2**: Visual Composition Design (Characters + Background) / 画面构图设计（人物 + 背景）
- **Step 3**: Typography & Text Layout / 文字内容编排
- **Step 4**: Overall Style Integration / 整体风格融合
- **Step 5**: Watermark Processing (Optional) / 水印处理（可选）
- **Step 6**: Special Style Processing (Optional) / 特殊风格处理（可选）
- **Step 7**: Generation & Self-Check (incl. key-safety items) / 生成与自检（含 Key 安全项）
- **Step 8**: Delivery & Confirmation / 交付与确认

## Directory Structure / 目录结构
```text
cinema-summary-poster/
├── SKILL.md                      # Core Skill prompt / 核心 Skill 提示词
├── README.md                     # This file / 本文件
├── .env.example                  # Optional API key template (dev self-test only) / 可选 API Key 模板（仅供自测）
├── references/
│   ├── style-guide.md            # Genre-to-style mapping / 风格匹配指南
│   └── font-spec.md              # Font rules & anti-garble spec / 字体规范与防乱码
├── examples/
│   └── good-example.md           # Positive/negative examples / 正例与反例参考
├── assets/
│   └── README.md                 # Asset usage guide / 素材使用说明
└── .github/
    └── ISSUE_TEMPLATE/           # Issue templates / 议题模板
        ├── bug-report.md         # Bug report template / Bug 报告模板
        └── feature-request.md    # Feature request template / 功能建议模板
```

## Installation / 安装方式
Send this repository link to an AI Agent that supports Skill installation (e.g., Claude Code, Codex) and say:
将本仓库链接发送给支持 Skill 安装的 AI Agent（如 Claude Code、Codex 等），并说：

> Install this Skill for me: https://github.com/jasonofchina/cinema-summary-poster

> 帮我安装这个 Skill：https://github.com/jasonofchina/cinema-summary-poster

Or manually copy `SKILL.md` to your Skill directory. No `.env` is required for Mode A.
或手动将 SKILL.md 复制到你的 Skill 目录。模式 A 无需任何 `.env` 配置。

## Default Configuration / 默认配置
- **Output Mode / 出图模式**: A (Return Prompt) / 返回 Prompt
- **Aspect Ratio / 画幅比例**: 3:4 (Portrait / 竖版)
- **Title Font / 标题字体**: Songti Regular (CN) + Sans-Serif (EN) / 中文宋体 + 英文无衬线
- **Body Font / 正文字体**: Kaiti Regular / 楷体 常规
- **Watermark / 水印**: Disabled / 不添加
- **Special Styles / 特殊风格**: Disabled / 不使用

## Usage Examples / 使用示例
只需输入片名，即可开始生成总结海报方案：
Just enter a title to start generating a poster plan:

> 帮我做一张《星际穿越》的总结海报

> Make a summary poster for Interstellar

随后按提示确认需求（片名、场景、风格、台词、字体等），并选择出图模式即可。
Then confirm the requirements (title, scene, style, quote, font, etc.) and choose an output mode.

## Feedback / 反馈与建议
使用中遇到问题或有功能建议，请到 [Issues](https://github.com/jasonofchina/cinema-summary-poster/issues) 提交：
Found a bug or have a suggestion? Please open an issue at [Issues](https://github.com/jasonofchina/cinema-summary-poster/issues):

- 🐛 Bug 报告 / Bug report → 使用「Bug 报告 / Bug Report」模板
- 💡 功能建议 / Feature request → 使用「功能建议 / Feature Request」模板

## Changelog / 更新日志
- **v1.4 (2026-08-18)**: Added dual output modes (A: return prompt / B: user-key direct generation) with API-key security redlines and automatic fallback; `.env` now optional (missing → Mode A). / 新增双出图模式与 API Key 安全红线，失败自动回退；`.env` 改为可选，缺失默认模式 A。
- **v1.3 (2026-08-18)**: Fixed filename encoding bugs, unified font rules (CN Songti + EN Sans-serif), aligned asset paths, completed truncated SKILL.md sections. / 修复文件名乱码 Bug，统一字体规则，对齐素材路径，补全 SKILL.md 截断部分。
- **v1.2 (2026-08-18)**: Added security execution constraints, pre-release desensitization checklist, GitGuardian integration, and API Key management standards. / 增加安全执行约束、发布前脱敏检查、GitGuardian 集成、API Key 规范管理。
- **v1.1 (2026-08-17)**: Optimized trigger words; standardized placeholder READMEs. / 优化触发词；规范化空目录占位 README。
- **v1.0 (2026-08-16)**: Initial release. / 初始版本。

## License / 开源协议
MIT
