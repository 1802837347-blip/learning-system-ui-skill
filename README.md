# 学习系统UI-skill

用于生成或扩展「AI 自主学习系统」移动端小程序页面的 UI 规则包，覆盖学习计划、课程学习、作文批改和批改报告等核心产品界面。可作为 Codex skill 使用，也可供 Claude Code 或其他 AI 助手读取后参考。

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

Codex 会通过 `SKILL.md` 触发 skill，并按其中指引读取 `references/ui-style-guide.md`。

### Claude Code 或其他 AI 助手

这类工具通常不会自动识别 Codex skill，可以把本仓库当作 UI 规则文档使用：

```text
使用 learning-system-ui-skill 里的规则优化这个页面
```

如果助手没有自动读取规则，请明确要求它先读取：

```text
SKILL.md
references/ui-style-guide.md
```

`references/ui-style-guide.md` 包含画布、色彩、字体、组件、状态、文案和检查清单。

## 文件结构

```text
.
├── SKILL.md
├── README.md
└── references
    └── ui-style-guide.md
```

## GitHub 描述建议

```text
AI UI rules / Codex skill for AI自主学习系统 mobile pages, learning plans, course pages,作文批改 flows, reports, and history states.
```
