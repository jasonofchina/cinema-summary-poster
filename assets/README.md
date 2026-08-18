# 📦 Assets Usage Guide / 素材资源使用说明

> This directory stores static assets used during poster generation.
> Currently empty. Follow this guide to add assets when ready.
> Written for absolute beginners — no coding knowledge required.
>
> 这个目录专门放"海报生成时会用到的静态素材"。
> 目前为空。未来按照下面的清单把素材文件放进来即可。
> 面向完全不懂代码的小白编写，照着做就行。

---

## What Goes Here / 这个目录未来要放什么

| Asset Type / 素材类型 | Format / 文件格式 | Purpose / 用途 | Required / 是否必须 |
| :--- | :--- | :--- | :--- |
| Paper Textures / 纸张纹理图 | PNG / JPG | Poster background simulating parchment, Xuan paper, etc. / 海报背景 | ✅ Yes / 必须 |
| Watermark Template / 水印模板 | PNG (transparent) / 透明底PNG | Used when user requests watermark / 用户要求加水印时使用 | ⭕ Optional / 可选 |
| Font Files / 字体文件 | TTF / WOFF2 | For special font requests / 特殊字体需求时使用 | ⭕ Optional / 可选 |
| Color Swatches / 配色卡 | PNG | Quick reference for genre-specific palettes / 快速查看推荐颜色 | ⭕ Optional / 可选 |

> 💡 Note / 注意: No actual images or fonts needed right now. Only this documentation.
> 当前阶段不需要真实图片或字体文件，只需要这份说明文档。

---

## Naming Convention (Mandatory) / 文件命名规范（必须遵守）

Format / 统一格式: `{asset-type}-{tone-or-weight}.{extension}`

### Paper Textures / 纸张纹理图
- Pattern / 命名: `{paper-type}-{tone}.png`
- Examples / 示例:
  - `xuan-paper-warm.png`
  - `parchment-dark.png`
  - `kraft-vintage.png`

### Watermark Templates / 水印模板
- Pattern / 命名: `watermark-{color}.png`
- Examples / 示例:
  - `watermark-lightgray.png`
  - `watermark-lightblue.png`

### Font Files / 字体文件
- Pattern / 命名: `{font-name}-{weight}.ttf`
- Examples / 示例:
  - `songti-regular.ttf`
  - `kaiti-regular.ttf`
  - `noto-sans-medium.ttf`

### Color Swatches / 配色卡
- Pattern / 命名: `palette-{genre}.png`
- Examples / 示例:
  - `palette-scifi.png`
  - `palette-period.png`

---

## Where to Find Free Assets / 素材从哪找（免版权素材站推荐）

| Asset Type / 素材类型 | Recommended Sites / 推荐网站 | Notes / 说明 |
| :--- | :--- | :--- |
| Paper Textures / 纸张纹理 | Unsplash, Pexels, TextureLabs | Search "paper texture" |
| Fonts / 字体 | Google Fonts, Font Squirrel | Select "Free for commercial use" |
| Watermark Icons / 水印图标 | Flaticon, IconFinder | Select free commercial license |
| Color Palettes / 配色参考 | Coolors, Adobe Color | Copy HEX values directly |

> ⚠️ Important / 重要提醒:
> - Always verify license is "Free for commercial use" or "CC0" before downloading. / 下载前务必确认许可证。
> - Never use fonts with unknown licensing to avoid infringement. / 不要使用来源不明的字体。

---

## Expected Directory Structure / 文件夹结构建议

After adding assets, the structure should look like:
补充素材后，目录结构应该长这样：

```text
assets/
├── paper-textures/          # Paper textures / 纸张纹理图
│   ├── xuan-paper-warm.png
│   ├── parchment-dark.png
│   └── kraft-vintage.png
├── watermark-template.png   # Watermark template / 水印模板
├── fonts/                   # Font files / 字体文件
│   ├── songti-regular.ttf
│   └── kaiti-regular.ttf
└── color-swatches.png       # Color swatches (optional) / 配色卡（可选）
