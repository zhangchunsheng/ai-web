# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

本项目为 Claude Code 提供烙馍网 AI 团队站点的开发指南。

## 项目概述

这是一个**纯静态 HTML 网站**，属于烙馍网 AI 团队（luomor.com 的 AI 分部）—— 由张春生（Peter Zhang）运营的个人品牌/营销站点。项目**没有构建系统、没有 package.json、没有框架、没有 Node.js**，只有带有内联 CSS 和第三方 JavaScript（Google AdSense、Google Analytics、百度统计）的独立 `.html` 文件。

## 文件清单

| 文件 | 主题色 | 说明 |
|------|--------|------|
| `index.html` | 深色科幻风（紫色/靛蓝） | "一人 AI 公司"概念页 — 宣言式页面，深色主题，CSS 变量 `--primary: #6366f1`、`--dark: #0f172a` |
| `about.html` | 企业蓝 | 传统「AI 团队」介绍页 — LLM/NLP/CV/MLOps 团队矩阵，蓝色主题 `--primary-color: #2563eb` |
| `gemini.html` | 橙色务实风 | 务实的「AI 落地」页 — 专注实际 AI 落地实施，橙色主题 `--primary: #f97316` |
| `grok.html` | 传统饮食文化（红色/金色） | 烙馍网传统中华面食文化页 — 烙馍文化传承，红色主题 |
| `luomor_ai_team.html` | 高端企业风（金色/深色） | 「AI 团队」企业级页面 — 滚动动画、高端排版（ZCOOL XiaoWei、Space Mono），金色主题 |
| `docs/` | 空目录 | 无内容 |

## 无需构建/测试

本项目为静态站点。开发流程：
- 直接编辑 HTML 文件
- 在浏览器中打开 `.html` 文件或通过任何静态 HTTP 服务器预览
- 上传文件到 luomor.com 服务器即可部署

## 页面间共有模式

所有页面共享以下元素：
- **Google AdSense**：`ca-pub-6096731848877113`（每个页面顶部注入）
- **Google Analytics**：`G-87JET1FJ65`
- **百度统计**：`c8281d72e36e9ac47796d3d2d3c0166c`
- **语言**：`zh-CN`（简体中文）
- **响应式断点**：`@media (max-width: 768px)` 适配移动端
- **外部链接**：所有 Logo 链接均指向 `https://www.luomor.com`
- **联系方式**：`coupon@luomor.com`、`ai@luomor.com`

## 关键架构说明

1. **每个 HTML 文件完全独立** — 所有 CSS 均内联在 `<style>` 标签中，无外部样式表或 JS 打包。
2. **无共享资源目录** — 图标使用 emoji 字符，图片使用占位服务（picsum.photos）。
3. **无 SPA/路由** — 页面是独立的着陆页，不是多页应用。
4. **`gemini-code-*.html` 文件**为自动生成的文件，可能来自先前的 AI 工具会话，不属于日常维护内容。
5. **未发现现有的 `.claude/` 目录**或 Cursor/Copilot 规则。

## 修改页面时注意

- **CSS 作用域**：每个页面有自己独立的 CSS 和 `:root` 变量。修改一个页面不会影响其他页面。
- **导航**：每个页面有内部锚点链接或指向 `luomor.com` 的外部链接。这些 HTML 文件之间没有交叉导航。
- **广告/统计脚本**：这些脚本在每个 HTML 文件顶部重复出现。新建页面时，从任意现有页面复制即可。
- **字体**：部分页面加载了 Google Fonts（Noto Sans SC、Noto Serif SC、ZCOOL XiaoWei、Space Mono）。修改时注意检查各页面 `<head>` 中的 `<link>` 和 `@import` 声明。
