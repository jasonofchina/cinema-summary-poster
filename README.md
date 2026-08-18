# 🎬 Cinema Summary Poster（影视总结海报生成器）

> 输入一部电影或电视剧，AI 自动生成一张包含经典台词、主旨思想、评价的电影级总结海报。

## 核心理念
每张海报都应贴合原片调性——科幻片有数字质感，古装片有宣纸韵味，文艺片有水彩温度。风格服务于故事，简洁而不简单。

## ⚠️ 发布前必做安全检查
每次提交代码或发布新版本前，必须执行：
1. **脱敏Review**：逐行检查是否包含真名、私人邮箱、电脑用户名、真人测试数据
2. **GitGuardian扫描**：CI/CD流水线自动检测，未通过禁止合并
3. **API Key验证**：确认所有密钥均通过`.env`注入，无硬编码
4. **限额检查**：确认API Key已设置调用上限，并记录上次轮换日期

## 工作流
- Step -1：安全检查（.env验证 + PII检测）
- Step 0：需求确认（影片、场景、风格、画幅、文字内容、字体等）
- Step 1：影片分析与风格定调
- Step 2：画面构图设计（人物 + 背景）
- Step 3：文字内容编排
- Step 4：整体风格融合
- Step 5：水印处理（可选）
- Step 6：特殊风格处理（可选）
- Step 7：生成与自检（含安全项）
- Step 8：交付与确认

## 目录结构
cinema-summary-poster/
├── SKILL.md          # 核心 Skill 提示词
├── README.md         # 本文件
├── .env.example      # API Key 环境变量模板
├── references/       # 参考资料（含素材需求清单）
├── examples/         # 示例海报（含素材需求清单）
└── assets/           # 素材资源（含素材需求清单）

## 安装方式
将本仓库链接发送给支持 Skill 安装的 AI Agent（如 Claude Code、Codex 等），并说：
> 帮我安装这个 Skill：https://github.com/{your-username}/cinema-summary-poster

或手动将 SKILL.md 复制到你的 Skill 目录中，并确保同级目录存在有效的 `.env` 文件。

## 默认配置
- 画幅比例：3:4（竖版）
- 标题字体：宋体 常规
- 正文字体：楷体 常规
- 水印：不添加
- 特殊风格：不使用
- API Key：通过 CINEMA_POSTER_API_KEY 环境变量注入

## 更新日志
- v1.2 (2026-08-18)：增加安全执行约束、发布前脱敏检查、GitGuardian集成、API Key规范管理
- v1.1 (2026-08-17)：优化触发词避免与通用海报 Skill 冲突；规范化空目录占位 README
- v1.0 (2026-08-16)：初始版本，包含完整提示词框架

## License
MIT



