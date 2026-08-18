# 文件路径：assets/README.md

# 📦 素材资源使用说明（Assets）

> 这个目录专门放"海报生成时会用到的静态素材"。
> 目前这个目录是空的，未来你需要按照下面的清单，把素材文件放进来。
> 别担心，下面写得非常详细，就算完全不懂代码也能照着做。

---

## 一、这个目录未来要放什么？

| 素材类型 | 文件格式 | 用途 | 是否必须 |
| :--- | :--- | :--- | :--- |
| 纸张纹理图 | PNG / JPG | 海报背景，模拟羊皮纸、宣纸等质感 | ✅ 必须 |
| 水印模板 | PNG（透明底） | 用户要求加水印时使用 | ⭕ 可选 |
| 字体文件 | TTF / WOFF2 | 特殊字体需求时使用 | ⭕ 可选 |
| 配色卡 | PNG | 快速查看各影片类型的推荐颜色 | ⭕ 可选 |

> 💡 注意：当前阶段不需要真实图片或字体文件，只需要这份说明文档。
> 未来补充素材时，直接按下面的命名规范放进来即可。

---

## 二、文件命名规范（必须遵守）

统一格式：`{素材类型}-{色调或字重}.{扩展名}`

### 纸张纹理图
- 命名：`{纸张类型}-{色调}.png`
- 示例：
  - `xuan-paper-warm.png`（宣纸-暖色）
  - `parchment-dark.png`（羊皮纸-深色）
  - `kraft-vintage.png`（牛皮纸-复古）

### 水印模板
- 命名：`watermark-{颜色}.png`
- 示例：
  - `watermark-lightgray.png`
  - `watermark-lightblue.png`

### 字体文件
- 命名：`{字体名}-{字重}.ttf`
- 示例：
  - `songti-regular.ttf`
  - `kaiti-regular.ttf`
  - `noto-sans-medium.ttf`

### 配色卡
- 命名：`palette-{影片类型}.png`
- 示例：
  - `palette-scifi.png`
  - `palette-period.png`

---

## 三、素材从哪找？（免版权素材站推荐）

如果你不知道去哪里找素材，下面这些网站都可以免费商用：

| 素材类型 | 推荐网站 | 说明 |
| :--- | :--- | :--- |
| 纸张纹理 | Unsplash、Pexels、TextureLabs | 搜索 "paper texture" |
| 字体 | Google Fonts、Font Squirrel | 选择 "Free for commercial use" |
| 水印图标 | Flaticon、IconFinder | 选择免费可商用图标 |
| 配色参考 | Coolors、Adobe Color | 直接复制 HEX 色值 |

> ⚠️ 重要提醒：
> - 下载素材前，务必确认许可证是 "Free for commercial use" 或 "CC0"。
> - 不要使用来源不明的字体，避免侵权。

---

## 四、文件夹结构建议

未来补充素材后，目录结构应该长这样：

```text
assets/
├── paper-textures/          # 纸张纹理图
│   ├── xuan-paper-warm.png
│   ├── parchment-dark.png
│   └── kraft-vintage.png
├── watermark-template.png   # 水印模板
├── fonts/                   # 字体文件
│   ├── songti-regular.ttf
│   └── kaiti-regular.ttf
└── color-swatches.png       # 配色卡（可选）
