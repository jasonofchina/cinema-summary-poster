# 🚫 Negative Prompts Library / 负面提示词库

> 用途：出图时自动附加的"负面提示词"，防止 AI 生成常见废图。
> Purpose: Negative prompts appended automatically to prevent common AI-generation failures.
> 适用：模式 A 的 prompt 末尾、模式 B 的接口参数中。
> Applies to: Mode A prompt tails and Mode B interface parameters.

---

## Basic Negative Prompts / 基础负面提示词（全类型通用）

```text
garbled text, missing characters, merged strokes, watermark,
extra fingers, distorted hands, deformed face, bad anatomy,
blurry, low quality, jpeg artifacts, oversaturated, cluttered,
duplicate elements, asymmetric composition, wrong perspective
```

对应中文说明 / Explanation:
乱码文字、缺字、笔画粘连、水印、多余手指、手部畸形、面部变形、人体比例错误、模糊、低画质、JPEG 压缩伪影、过饱和、画面杂乱、重复元素、构图失衡、透视错误

---

## Genre-Specific Additions / 按类型追加

| Genre / 类型 | Additional Negative Prompts / 追加负面提示词 |
| :--- | :--- |
| Sci-fi / 科幻 | code rain, digital streams, excessive tech clutter / 代码雨、数字流、过度科技元素 |
| Period / 古装 | modern elements, neon colors, fluorescent / 现代元素、霓虹色、荧光色 |
| Animation / 动画 | realistic faces, dark oppressive tones / 写实人脸、暗黑压抑色调 |
| Suspense / 悬疑 | bright warm tones, cute elements / 明亮暖色调、可爱元素 |
| Documentary / 纪录片 | cartoonish, exaggerated distortion, over-beautification / 卡通化、夸张变形、过度美化 |

---

## Mode A vs Mode B / 两种模式的用法差异

### 模式 A（返回 Prompt）
把"基础负面提示词"直接以英文原文写进 prompt 末尾，例如：
Append the "Basic Negative Prompts" verbatim (in English) to the prompt tail, e.g.:
```text
Negative prompt: garbled text, missing characters, merged strokes, watermark, blurry, low quality...
```

### 模式 B（直接生图）
把负面提示词作为 `negative_prompt` 参数传入生图接口，与画面 prompt 分离。
Pass the negative prompts as the `negative_prompt` parameter, separate from the image prompt.

---

## Changelog / 更新记录

| Version | Date | Notes |
| :--- | :--- | :--- |
| v2.0 | 2026-08-19 | Aligned version with SKILL.md v2.0 / 与 SKILL.md v2.0 对齐 |
| v1.0 | 2026-08-18 | Initial release / 初始版本 |
