#  Cinema Summary Poster / 影视总结海报生成器

> Input a movie or TV series, and AI will automatically generate a cinematic summary poster featuring classic quotes, core themes, and reviews.
> 
> 输入一部电影或电视剧，AI 自动生成一张包含经典台词、主旨思想、评价的电影级总结海报。

## Core Philosophy / 核心理念
Style serves the story; simple but not simplistic. Sci-fi has digital texture, period dramas carry the charm of Xuan paper, and indie films hold the warmth of watercolors.
每张海报都应贴合原片调性——科幻片有数字质感，古装片有宣纸韵味，文艺片有水彩温度。风格服务于故事，简洁而不简单。

## ️ Pre-release Security Checklist / 发布前必做安全检查
Before every commit or release, the following MUST be executed:
每次提交代码或发布新版本前，必须执行：

1. **Desensitization Review / 脱敏审查**: Check line-by-line for real names, private emails, local usernames, or real test data.
   逐行检查是否包含真名、私人邮箱、电脑用户名、真人测试数据。
2. **GitGuardian Scan / GitGuardian 扫描**: Automated CI/CD pipeline check. Merging is strictly prohibited if failed.
   CI/CD 流水线自动检测，未通过禁止合并。
3. **API Key Validation / API Key 验证**: Ensure all keys are injected via `.env` with zero hardcoding.
   确认所有密钥均通过 `.env` 注入，无硬编码。
4. **Quota Check / 限额检查**: Confirm API Key rate limits are set, and log the last rotation date.
   确认 API Key 已设置调用上限，并记录上次轮换日期。

## Workflow / 工作流
- **Step -1**: Security Check (.env validation + PII detection) / 安全检查（.env验证 + PII检测）
- **Step 0**: Requirement Confirmation (Movie, scene, style, aspect ratio, text, fonts, etc.) / 需求确认（影片、场景、风格、画幅、文字内容、字体等）
- **Step 1**: Film Analysis & Style Tone Setting / 影片分析与风格定调
- **Step 2**: Visual Composition Design (Characters + Background) / 画面构图设计（人物 + 背景）
- **Step 3**: Typography & Text Layout / 文字内容编排
- **Step 4**: Overall Style Integration / 整体风格融合
- **Step 5**: Watermark Processing (Optional) / 水印处理（可选）
- **Step 6**: Special Style Processing (Optional) / 特殊风格处理（可选）
- **Step 7**: Generation & Self-Check (Including security items) / 生成与自检（含安全项）
- **Step 8**: Delivery & Confirmation / 交付与确认

## Directory Structure / 目录结构
cinema-summary-poster/
├── SKILL.md          # Core Skill Prompt / 核心 Skill 提示词
├── README.md         # This file / 本文件
├── .env.example      # API Key Environment Variable Template / API Key 环境变量模板
├── references/       # Reference materials (with asset requirement list) / 参考资料（含素材需求清单）
├── examples/         # Example posters (with asset requirement list) / 示例海报（含素材需求清单）
└── assets/           # Asset resources (with asset requirement list) / 素材资源（含素材需求清单）

## Installation / 安装方式
Send this repository link to an AI Agent that supports Skill installation (e.g., Claude Code, Codex) and say:
将本仓库链接发送给支持 Skill 安装的 AI Agent（如 Claude Code、Codex 等），并说：
> Install this Skill for me: https://github.com/{your-username}/cinema-summary-poster
> 帮我安装这个 Skill：https://github.com/{your-username}/cinema-summary-poster

Or manually copy `SKILL.md` to your Skill directory, and ensure a valid `.env` file exists in the same directory.
或手动将 SKILL.md 复制到你的 Skill 目录中，并确保同级目录存在有效的 `.env` 文件。

## Default Configuration / 默认配置
- **Aspect Ratio / 画幅比例**: 3:4 (Portrait / 竖版)
- **Title Font / 标题字体**: Songti Regular / 宋体 常规
- **Body Font / 正文字体**: Kaiti Regular / 楷体 常规
- **Watermark / 水印**: Disabled / 不添加
- **Special Styles / 特殊风格**: Disabled / 不使用
- **API Key**: Injected via `CINEMA_POSTER_API_KEY` environment variable / 通过 CINEMA_POSTER_API_KEY 环境变量注入

## Changelog / 更新日志
- **v1.2 (2026-08-18)**: Added security execution constraints, pre-release desensitization checklist, GitGuardian integration, and API Key management standards. / 增加安全执行约束、发布前脱敏检查、GitGuardian集成、API Key规范管理。
- **v1.1 (2026-08-17)**: Optimized trigger words to avoid conflicts with generic poster Skills; standardized empty directory placeholder READMEs. / 优化触发词避免与通用海报 Skill 冲突；规范化空目录占位 README。
- **v1.0 (2026-08-16)**: Initial release with complete prompt framework. / 初始版本，包含完整提示词框架。

## License / 开源协议
MIT




