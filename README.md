# 学习系统UI-skill

用于生成或扩展「AI 自主学习系统」移动端小程序页面的 UI design skill，覆盖学习计划、课程学习、作文批改和批改报告等核心产品界面。可作为 Codex skill 使用，也可供 Claude Code 或其他 AI 助手读取后参考。

## 适用场景

- 学习首页、待办计划、历史计划、课程推荐
- 登录、手机号验证、首次信息补全、游客状态
- 制定计划流程、学习信息填写、计划考点选择、日期选择弹层、错误态
- 每日学习计划、课程任务卡、日历计划、全部课程、课程目录和视频列表
- 作文批改入口、满分选择、拍照取图、相机权限、照片排序、OCR 识别和文字核对
- 作文批改中、作文讲解、批改报告生成、报告预览、下载报告、反馈表单
- 作文批改历史、月份筛选、批改次数用完、空状态和待解锁状态

## 使用方式

### Codex

将本目录放入 Codex skills 目录后，可以直接在相关任务中说：

```text
使用 学习系统UI-skill 优化这个页面
```

或：

```text
使用 学习系统UI-skill 生成一个 AI 自主学习系统的作文批改页面
```

Codex 会通过 `SKILL.md` 触发 skill，并按其中的 Automatic Execution Protocol 自动读取并应用设计规则、tokens、页面模式、组件规格和质量门禁。

用户不需要在 prompt 中逐个列出所有规则文件。只要触发本 skill，执行者就应该自动读取并应用 `SKILL.md` 中列出的核心 reference 文件，并在交付前修复 `references/quality-gates.md` 的 Hard Failures。

如果是在修 UI 问题或优化已有页面，可以这样说：

```text
使用 学习系统UI-skill 优化这个页面，并按 references/quality-gates.md 做交付前检查
```

结合 PRD 时，可以简写为：

```text
使用 learning-system-ui-skill，根据这个 PRD 优化页面，输出可交互 HTML。
```

PRD 负责信息架构，例如 Tab 数量、字段、状态、卡片内容和要删除的模块；skill 负责视觉系统，例如色彩、字号、间距、圆角、图标、卡片、渐变和质量验收。交付前如果存在 `references/quality-gates.md` 的 Hard Failures，应该先修复再交付。

没有 PRD、只提供页面或截图时，也可以直接说：

```text
使用 learning-system-ui-skill 优化这个页面，输出可交互 HTML。
```

这时原页面本身就是信息架构来源：Tab 数量、文案、模块顺序、卡片数量、字段、状态和数据都要保留；skill 只负责把视觉样式优化成 AI 自主学习系统风格。

### Claude Code 或其他 AI 助手

这类工具通常不会自动识别 Codex skill，可以把本仓库当作 UI 规则文档使用：

```text
使用 learning-system-ui-skill 里的规则优化这个页面
```

如果助手没有自动读取规则，请明确要求它先读取：

```text
SKILL.md
references/design.md
references/design.tokens.json
references/quality-gates.md
```

`references/design.md` 是主设计规则，适合 UI 生成、UI 优化和评审，记录 AI 自主学习系统的画布、字号、间距、圆角、渐变、卡片、图标、日历、学习计划、课程和作文批改等通用设计原则。

`references/design.tokens.json` 是结构化 token 源，适合让 AI 精确读取颜色、字号、间距、圆角、阴影和组件规格。

`references/tokens.css` 和 `references/tailwind.config.ts` 用于实现工作，帮助 HTML/CSS/Tailwind 页面直接复用设计变量，减少临时写错字号、圆角、渐变和间距。

`references/page-patterns.md` 用于先判断页面属于哪类模式，例如学习计划、全部课程、知识点学习、简答题闯关、作文批改、弹窗/底部表单等。

`references/component-specs.md` 用于沉淀可复用组件规格，包括顶部标签、AI 助手气泡、日历、课程卡、底部导航、按钮、标签、渐变卡和基础 icon fallback。

图标和默认头像不靠临场手画。生成时应先使用 Figma/source 原图资产，其次使用 `assets/icons/`、`assets/avatars/` 中的本地资产；仍缺失时从 Lucide、Tabler、Heroicons、Phosphor、MingCute、Iconoir 或 Material Symbols 等成熟开源图标库中选择最贴近的 SVG，复制到仓库后再引用。

`references/ui-style-guide.md` 包含早期提炼的画布、色彩、字体、页面细节、状态和文案规范，可作为页面细节补充。

`references/quality-gates.md` 用于优化和验收，重点检查卡片内容是否出界、按钮是否在容器内、文字/指标是否被裁切、标签描边是否异常、真实图片是否被占位替代、固定底栏是否遮挡内容，以及触控、可读性、状态和安全区等通用 UI 质量问题。


## 字体说明

本仓库默认不附带字体安装包。特殊字体会在 `references/ui-style-guide.md` 中记录名称和兜底方案，实际生成页面时优先使用目标环境已有字体。

如果需要像素级复刻某些标题字形，应先确认字体授权允许再单独加入字体文件。

## 文件结构

```text
.
├── SKILL.md
├── README.md
├── assets
│   ├── assistant-avatar.png
│   ├── avatars
│   │   └── default-parent.svg
│   ├── icons
│   │   ├── calendar-days.svg
│   │   ├── chevron-down.svg
│   │   ├── chevron-left.svg
│   │   ├── chevron-right.svg
│   │   ├── circle-user-round.svg
│   │   ├── clipboard-list.svg
│   │   ├── file-check.svg
│   │   ├── house.svg
│   │   ├── lock-keyhole.svg
│   │   ├── play.svg
│   │   ├── search.svg
│   │   └── user-round.svg
│   ├── status-light.svg
│   ├── status-white.svg
│   └── composition
│       ├── badge-empty.svg
│       ├── badge-valued.svg
│       ├── empty-no-content.svg
│       ├── reference-history-empty.png
│       ├── reference-history-records.png
│       ├── tag-locked.svg
│       ├── tag-rank-1.svg
│       ├── tag-rank-2.svg
│       ├── tag-rank-3.svg
│       ├── tag-rank-4.svg
│       └── tag-rank-5.svg
└── references
    ├── component-specs.md
    ├── design.md
    ├── design.tokens.json
    ├── page-patterns.md
    ├── quality-gates.md
    ├── tailwind.config.ts
    ├── tokens.css
    ├── ui-style-guide.md
```

## GitHub 描述建议

```text
AI UI rules / Codex skill for AI自主学习系统 mobile pages, learning plans, course pages,作文批改 flows, reports, history states, and UI quality gates.
```
