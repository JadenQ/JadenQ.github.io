---
name: wine-knowledge-design-system
description: 酒类知识页面的设计系统规范 — 色彩、字体、排版、组件、动画、交互的完整参考
metadata:
  type: reference
---

# 酒类知识 · Wine Knowledge — 设计系统规范

> 基于 `new-aesthetic-natural-wine.html` 提取的设计语言。所有酒类知识页面（自然酒、橙酒、品鉴指南等）必须遵循此规范，确保视觉与交互的一致性。

---

## 1. 设计哲学

**关键词：Editorial · Refined · Monastic · Minimal**

整体风格偏向 **杂志编辑式（Editorial）** —— 克制、精密、有呼吸感。不是热闹的 Dribbble 风格，而是接近高端出版物和艺术画册的视觉语言。

- **克制优于张扬**：4px 圆角而非 12-20px；细边框而非重阴影；微妙的 hover 反应而非夸张变形
- **信息层级清晰**：DM Mono 负责编号/标签，Cormorant Garamond 负责英文标题的优雅感，Noto Serif SC 负责中文内容的阅读体验，Outfit 负责正文的流畅感
- **呼吸感**：Section 间距 140px，卡片内有 36-48px padding，一切元素之间都有充足的留白
- **暗色区段**：`section-dark`（earth 背景）和 `section-wine`（wine-dark 背景）用于视觉节奏的切换——光明与阴影的交替

---

## 2. 色彩系统

### 主色板

| CSS 变量 | 色值 | 用途 | 心理联想 |
|---|---|---|---|
| `--wine` | `#6B2737` | 主强调色、标题、导航、链接、分割线菱形 | 深酒红——沉稳、典雅、权威 |
| `--wine-dark` | `#3D151E` | 暗色区段背景、深色标题、hero overlay | 深夜酒窖——神秘、纵深 |
| `--wine-light` | `#8C3A4A` | 辅助强调、原则卡片彩色圆点之一 | 玫红酒渍——温润 |
| `--terracotta` | `#C75B4A` | Section labels、timeline 年份、cert-name、色点 | 陶土赤——手工感、原始力 |
| `--amber` | `#D4956A` | 原则编号、technique-num、footer 分割线、风格卡片顶部色条之一 | 琥珀暖光——时间沉淀 |
| `--amber-light` | `#F0D4A8` | Hero 标签文字、导航文字、未来趋势卡片色条 | 淡金——高级感、装饰性 |
| `--sage` | `#7A8C6E` | Grape type 标签、未来趋势色条、生物动力色点 | 青苔——有机、自然 |
| `--clay` | `#B8917A` | Grape region 文字、分割线渐变、风格卡片色条之一 | 陶器——泥土、质朴 |

### 背景与中性色

| CSS 变量 | 良值 | 用途 |
|---|---|---|
| `--parchment` | `#FDF9F3` | 主背景、卡片背景——温暖的纸色 |
| `--cream` | `#F7F2EA` | 柔对比背景、comparison-block 背景 |
| `--cream-deep` | `#EDE5D8` | 原则卡片圆点色（dot-cream，带边框） |
| `--earth` | `#2A1A12` | 深色区段背景、Footer 背景——最深色 |
| `--earth-mid` | `#5C4A3A` | 正文描述文字、次要信息——最常用的文字色 |

### 调色规则

- **文字色只用三级**：`--earth`（最深标题）、`--wine-dark` / `--wine`（强调标题）、`--earth-mid`（正文描述）
- **背景色只用三级**：`--parchment`（默认）、`--cream`（柔对比）、`--earth` / `--wine-dark`（暗区段）
- **强调色用于**：小标签、圆点色、编号、分割线、色条——**绝不用于大面积背景**
- **边框色**：统一 `rgba(107, 39, 55, 0.06–0.10)`，极低透明度的 wine 色

---

## 3. 字体系统

### 字体栈

| 角色 | 字体 | CSS 变量 | 用途 |
|---|---|---|---|
| **Display** | Cormorant Garamond | `--font-display` | 英文标题、风格名称、城市名、先驱姓名、葡萄品种名 |
| **Body** | Outfit (wght 200–700) | `--font-body` | 正文基础字体、body 默认 |
| **Chinese** | Noto Serif SC | `--font-chinese` | 所有中文标题、中文描述文字、中文标签 |
| **Mono** | DM Mono | `--font-mono` | Section labels（§）、编号标签、年份标签、类别标签、footer meta |

### 字重分配

- **Cormorant Garamond**：标题用 `400`（regular），大装饰编号用 `300`（light），姓名用 `500`（medium）
- **Outfit**：body 默认 `300`（light），正文描述不另行加粗
- **Noto Serif SC**：标题 `700`，正文描述 `500` 或默认 `400`
- **DM Mono**：`400` 或 `500`

### 字号层级

| 元素 | 字号 | 字体 | 备注 |
|---|---|---|---|
| Hero 中文标题 | `clamp(4rem, 10vw, 8rem)` | `--font-chinese` | letter-spacing: 0.15em |
| Hero 英文标题 | `clamp(1.2rem, 3vw, 2rem)` | `--font-display` | letter-spacing: 0.6em, uppercase, wght 300 |
| Hero 标签 | `0.72rem` | `--font-mono` | letter-spacing: 0.35em, uppercase |
| Hero 副标题 | `clamp(0.95rem, 1.8vw, 1.15rem)` | `--font-chinese` | line-height: 2 |
| Section 英文标题 | `clamp(2.4rem, 5vw, 3.8rem)` | `--font-display` | wght 400, letter-spacing: -0.01em |
| Section 中文标题 | `clamp(1.8rem, 4vw, 2.8rem)` | `--font-chinese` | wght 700 |
| Section label | `0.7rem` | `--font-mono` | letter-spacing: 0.3em, uppercase, 前有 24px 细线 |
| Section intro | `1.05rem` | `--font-chinese` | line-height: 2, max-width: 680px |
| 原则编号 | `3rem` | `--font-display` | wght 300, opacity: 0.5 |
| 原则标题 | `1.1rem` | `--font-chinese` | wght 700 |
| 原则描述 | `0.92rem` | `--font-chinese` | line-height: 1.9 |
| 风格标签 | `0.65rem` | `--font-mono` | letter-spacing: 0.2em, uppercase |
| 风格名（英） | `1.6rem` | `--font-display` | wght 500 |
| 风格名（中） | `1rem` | `--font-chinese` | wght 600 |
| 风格描述 | `0.88rem` | `--font-chinese` | line-height: 1.9 |
| 统计数值 | `2.8rem` | `--font-display` | wght 300 |
| 统计标签 | `0.82rem` | `--font-chinese` | line-height: 1.5 |
| Footer meta | `0.72rem` | `--font-mono` | letter-spacing: 0.15em |

---

## 4. 排版与间距

### Section 系统

| 变量 | 值 | 说明 |
|---|---|---|
| `--section-gap` | `140px` | Section 之间的纵向间距（900px 以下 → 100px，640px 以下 → 80px） |
| `--content-max` | `1280px` | 普通区段最大宽度 |
| `--content-narrow` | `860px` | 窄内容区段最大宽度 |
| `--nav-height` | `64px` | 固定导航栏高度（640px 以下 → 56px） |

### Section 类型

- **`.section`**：`padding: var(--section-gap) 40px; max-width: var(--content-max); margin: 0 auto;`
- **`.section-full`**：`padding: var(--section-gap) 40px; max-width: 100%;`（用于暗色区段，内部再套 max-width 容器）
- **`.section-narrow`**：`padding: var(--section-gap) 40px; max-width: var(--content-narrow); margin: 0 auto;`
- **`.section-cream`**：背景 `var(--cream)`
- **`.section-dark`**：背景 `var(--earth)`，文字 `var(--cream)`
- **`.section-wine`**：背景 `var(--wine-dark)`，文字 `var(--cream)`

### 分割线系统

Section 之间用 **菱形分割线**：

```html
<div class="divider"><div class="divider-diamond"></div></div>
```

视觉：8×8px wine 色菱形（rotate 45deg, opacity 0.4），两侧有 clay 色渐变细线。

### 卡片内部间距

| 元素 | Padding | 备注 |
|---|---|---|
| 原则卡片 | `40px 36px` | border: 1px solid rgba(107,39,55,0.08) |
| 先驱卡片 | `48px` | grid: 120px 1fr |
| 风格卡片 | `52px 36px 40px` | 顶部有 4px 色条 |
| 区域卡片 | `32px` | border-radius: 4px |
| 文化卡片 | `40px 32px` | 背景: cream |
| 统计卡片 | `40px 20px` | 居中排列 |
| 争议列 | `48px` | 背景: rgba 或 sage tint |
| 趋势卡片 | `36px 28px` | 底部有 3px 渐变色条 |
| 认证卡片 | `32px` | cert-name 1.4rem |

---

## 5. 组件库

### 5.1 导航栏 `.site-nav`

- 固定顶部，高度 64px
- 背景：`rgba(253, 249, 243, 0.82)` + `backdrop-filter: blur(20px) saturate(1.4)`
- 底部边框：`1px solid rgba(107, 39, 55, 0.08)`
- 左侧 `.nav-brand`：中文字体，wght 700，1.1rem，wine 色——**应设为 `<a>` 标签链接至知识库首页**
- `.nav-links`：flex 布局，6px gap，pill 形链接（6px 12px padding, 20px radius）
- 滚动时：`.nav-scrolled` 添加阴影；向下滚动超过 400px：`.nav-hidden` 隐藏导航
- 活动链接：wine 色 + 底部 4px 圆点

### 5.2 Hero 区段

- 全屏高度 `100vh`，min-height 700px
- 三层叠加：`hero-bg`（图片）→ `hero-overlay`（渐变遮罩）→ `hero-noise`（SVG 噪点纹理，opacity 0.04）
- Hero overlay 渐变：`rgba(42,26,18,0.55)` → `rgba(61,21,30,0.65)` → `rgba(42,26,18,0.80)`
- 内容元素有 `data-parallax` 视差效果
- 底部有 `scroll-line` 脉冲动画

### 5.3 Section Label

```html
<div class="section-label">§1</div>
```

- DM Mono, 0.7rem, letter-spacing: 0.3em, uppercase
- terracotta 色
- 前置 24px × 1px terracotta 细线（`::before`）

### 5.4 原则卡片 `.principle-card`

- 2 列网格布局
- 左侧大编号（Cormorant Garamond, 3rem, wght 300, amber 色, opacity 0.5）
- 标题前有 **彩色圆点** `.principle-dot`（8px, border-radius 50%）
  - 圆点颜色分配：`dot-wine`, `dot-terracotta`, `dot-amber`, `dot-sage`, `dot-clay`, `dot-earth`, `dot-light`, `dot-cream`
- hover：translateY(-6px) + box-shadow: 0 20px 60px rgba(42,26,18,0.08)
- 圆角：4px

### 5.5 比较表格 `.comparison-block`

- 结构化数据表格，4 列网格
- Header 行：wine-dark 背景，cream 文字
- 自然酒列：`highlight-col` 背景 rgba(107,39,55,0.04)
- Row 和 header 内 div 之间有细分割线

### 5.6 时间线 `.timeline`

- 中心轴线：2px 宽，rgba(107,39,55,0.12)
- 轴线有 **渐变填充线** `.timeline-line-fill`：wine → terracotta 渐变，随滚动进度填充
- 奇数项左对齐，偶数项右对齐
- 时间点 `.timeline-dot`：14px, wine 边框 2px, parchment 填充
- 活动状态 `.active`：wine 填充 + scale(1.3)
- 年份用 DM Mono, 0.72rem, terracotta 色

### 5.7 先驱卡片 `.pioneer-card`

- Grid: 120px 1fr
- 左侧 `.pioneer-avatar`：120px 圆形，wine → terracotta 渐变背景，缩写字母（Cormorant Garamond, 2.4rem, wght 300, cream 色）
- 姓名：Cormorant Garamond, 1.8rem, wght 500
- 年份：DM Mono, 0.75rem, earth-mid 色
- 角色：Noto Serif SC, 1rem, wght 600, terracotta 色
- "四人帮" 卡片 `.gang-card`：左侧 4px wine 宽边框

### 5.8 光谱流 `.spectrum-flow`

- 5 列 flex 布局，无间距，6px 圆角
- hover 时 flex 从 1 扩展到 1.5——**呼吸式交互**
- 色序：`#E8DDD0` → `#C5C9A8` → `sage` → `terracotta` → `wine`
- 每列有 level 标签（DM Mono, 0.65rem）、中文标题、描述

### 5.9 风格卡片 `.style-card`

- 3 列网格（900px 以下 2 列，640px 以下 1 列）
- 顶部 4px 色条（每张不同：amber / terracotta / wine-light / earth / clay / sage）
- 标签：DM Mono, 0.65rem, uppercase
- 英文名：Cormorant Garamond, 1.6rem, wght 500
- 中文名：Noto Serif SC, 1rem, wght 600

### 5.10 葡萄品种行 `.grape-row`

- 2 列网格：200px 1fr
- 品种名：Cormorant Garamond, 1.8rem, wght 400, italic, wine 色
- 类型标签：DM Mono, 0.68rem, uppercase, sage 色
- 区域信息：0.8rem, clay 色
- hover：translateY(-4px)
- 行间 1px 分割线

### 5.11 酿造工艺卡片 `.technique-card`（暗色区段）

- 3 列网格，无间距，边框分割
- 大编号：Cormorant Garamond, 4rem, wght 300, amber 色, opacity 0.3
- 中文名称：cream 色
- 英文名称（italic）：amber-light 色, opacity 0.7
- 描述：rgba(247,242,234,0.7)
- 背景：section-dark（earth）

### 5.12 统计卡片 `.stat-card`

- 4 列网格（900px → 2 列，640px → 1 列）
- 数值：Cormorant Garamond, 2.8rem, wght 300, wine 色
- 有 **数字滚动动画** `data-count`：IntersectionObserver 触发，1.8s ease-out cubic

### 5.13 争议列 `.debate-columns`

- 2 列布局（900px → 1 列）
- 争议列：rgba(107,39,55,0.04) 背景 + wine 色边框
- 未来列：rgba(122,140,110,0.08) 背景 + sage 色边框
- 标题前有 **几何图标**：三角形（terracotta, clip-path）或圆形（sage）

### 5.14 横向滚动 `.h-scroll`

- flex 布局 + scroll-snap-type: x mandatory
- 自定义滚动条：4px 高度, wine-light 色
- 支持鼠标拖拽滚动

### 5.15 拉引语 `.pull-quote`

- 居中，max-width 800px
- 上下各有 60px × 1px wine 色细线（opacity 0.4）
- 中文引文：clamp(1.2rem, 2.5vw, 1.6rem), wght 500, line-height: 2
- 引用来源：DM Mono, 0.75rem, earth-mid 色

---

## 6. 动画与交互

### 滚动揭示系统

| 类名 | 效果 | 过渡 |
|---|---|---|
| `.reveal` | translateY(40px) → 0, opacity 0 → 1 | 0.8s cubic-bezier(0.25,0.46,0.45,0.94) |
| `.reveal-left` | translateX(-50px) → 0 | 0.8s ease |
| `.reveal-right` | translateX(50px) → 0 | 0.8s ease |
| `.reveal-scale` | scale(0.92) → 1 | 0.8s ease |
| `.stagger` | 子元素逐个揭示 | 0.05s → 0.82s 递增延迟 |

触发方式：IntersectionObserver, threshold 0.1, rootMargin `-60px`

### 卡片 Hover

统一模式：`translateY(-6px)` + `box-shadow`（rgba(42,26,18,0.06–0.12)）
过渡：`transform 0.4s ease, box-shadow 0.4s ease`

### 特殊交互

| 交互 | 元素 | 说明 |
|---|---|---|
| **自定义光标** | `.cursor-dot` | 8px wine 色圆点, mix-blend-mode: difference; hover 时放大至 32px amber 色 |
| **滚动进度条** | `.scroll-progress` | 3px 高度, wine → terracotta → amber 渐变 |
| **视差** | `[data-parallax]` | hero-bg 和 hero-content 元素, 乘数由属性值决定 |
| **导航自动隐藏** | `.site-nav` | 向下滚动超过 400px 时 translateY(-100%) 隐藏 |
| **时间线进度填充** | `.timeline-line-fill` | 随滚动高度百分比增加 |
| **时间线圆点激活** | `.timeline-dot.active` | 到达视口中心时变实心 + scale(1.3) |
| **数字滚动动画** | `[data-count]` | 1.8s, ease-out cubic, 支持范围值如 "$10-13B" |
| **光谱呼吸扩展** | `.spectrum-card:hover` | flex 从 1 变为 1.5 |
| **横向拖拽滚动** | `.h-scroll` | mousedown/move/up 拖拽 |

### 无障碍

- `prefers-reduced-motion: reduce` 时：所有动画设 0.01ms，所有 reveal 直接显示，自定义光标隐藏
- `a:focus-visible`：2px amber 色 outline + 2px offset
- `.sr-only` 类用于无障碍隐藏文字
- 所有交互元素有 `aria-label` 或语义标签

---

## 7. 响应式断点

| 断点 | 主要变化 |
|---|---|
| **≤ 1200px** | 原则网格 2 列；统计 2 列；酿造工艺 2 列；比较表字号缩小 |
| **≤ 900px** | section-gap → 100px；section padding → 24px；原则/酿造/趋势 1 列；时间线变左对齐单列；光谱纵向排列；区域列表 1 列；葡萄品种行 1 列；争议列 1 列；先觉头像 80px |
| **≤ 640px** | section-gap → 80px；nav-height → 56px；hero 标题 letter-spacing 缩小；风格/文化/统计/工艺/认证/趋势 1 列；先觉卡片居中单列；**自定义光标隐藏**；body cursor 恢复 auto |

---

## 8. 印刷样式

- 隐藏：nav、scroll-progress、cursor-dot、hero-bg/overlay/noise、scroll-hint
- Hero 变为白底黑字
- 暗色区段变为白底黑字
- 所有 reveal 动画强制 opacity:1, transform:none
- 卡片 break-inside:avoid, 1px solid #ccc
- 字号 11pt, body 黑色白底
- 链接 color:inherit, 无装饰

---

## 9. 新页面创建指南

创建新的酒类知识页面时，遵循以下步骤：

### 必须包含的元素

1. **完整 CSS 变量块**——从 `:root` 复制全部变量定义
2. **Google Fonts 引入**——Cormorant Garamond + DM Mono + Noto Serif SC + Outfit
3. **滚动进度条** `.scroll-progress`
4. **固定导航栏** `.site-nav`——左侧 `.nav-brand` **必须是 `<a href="index.html">` 链接回知识库首页**
5. **Hero 区段**——全屏高度，三层叠加（图片 → 渐变遮罩 → 噪点纹理）
6. **菱形分割线**——Section 之间使用 `<div class="divider"><div class="divider-diamond"></div></div>`
7. **Section label**——每个 Section 开头用 `<div class="section-label">§N</div>`
8. **IntersectionObserver 揭示脚本**——.reveal / .reveal-left / .reveal-right / .reveal-scale / .stagger
9. **Footer**——包含 `<a href="index.html">← 返回酒类知识库</a>` 链接
10. **`prefers-reduced-motion` 无障碍处理**
11. **`@media print` 印刷样式**

### 禁止事项

- ❌ 不使用 Playfair Display、Inter 或旧版色值（#722F37, #D4A574 等）
- ❌ 不使用 emoji 作为卡片图标（原则卡片、风格卡片等——用编号或彩色圆点代替）
- ❌ 不使用大于 6px 的圆角（border-radius）
- ❌ 不使用粗重阴影（box-shadow 值不超过 0 24px 64px rgba(42,26,18,0.12)）
- ❌ 不在正文使用 bold/wght 700（仅标题使用）
- ❌ 不使用 `background: white` 或 `#fff`——始终用 `--parchment: #FDF9F3`

### 知识库首页更新

每新增一个主题页面，同步更新 `wines/index.html`：
- 将对应的 `topic-card.coming-soon` 改为 `topic-card available`
- 添加 `<a href="xxx.html">` 链接
- 移除 `::before` 即将上线标签
- 在 footer `.footer-links` 中添加新页面链接

---

## 10. 文件结构约定

```
wines/
├── index.html                ← 知识库导航首页
├── natural-wine.html         ← 自然酒深度文章
├── orange-wine.html          ← 橙酒（未来）
├── images/
│   ├── hero-vineyard.jpg     ← 自然酒 hero 图
│   ├── image_001.jpg         ← 自然酒内页图
│   ├── orange-hero.jpg       ← 橙酒 hero 图（未来）
│   └── ...
```

- 每个主题页面独占一个 HTML 文件
- 所有页面共享 `wines/images/` 目录
- 图片命名约定：`{topic}-{purpose}.jpg`，如 `orange-hero.jpg`
- Hero 图引用路径：`images/xxx.jpg`（相对路径，不使用绝对路径或临时路径）

---

## 相关记忆

- [[wine-knowledge-design-system]] — 本文档自身
- 未来新增页面时，参照本文档的"新页面创建指南"章节
