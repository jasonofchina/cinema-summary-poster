# 🎬 Cinema Summary Poster / 影视总结海报生成器

> Input a movie or TV series, and AI will automatically generate a cinematic summary poster featuring classic quotes, core themes, and reviews.
> 
> 输入一部电影或电视剧，AI 自动生成一张包含经典台词、主旨思想、评价的电影级总结海报。

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
```text
cinema-summary-poster/
├── SKILL.md                      # Core Skill Prompt / 核心 Skill 提示词
├── README.md                     # This file / 本文件
├── .env.example                  # API Key Environment Variable Template / API Key 环境变量模板
├── references/
│   ├── style-guide.md            # Genre-to-style mapping / 风格匹配指南
│   └── font-spec.md              # Font rules & anti-garble spec / 字体规范与防乱码
├── examples/
│   └── good-example.md           # Positive/negative examples / 正例与反例参考
└── assets/
    └── README.md                 # Asset usage guide / 素材使用说明



