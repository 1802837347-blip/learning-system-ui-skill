---
name: 学习系统UI-skill
description: Use this skill when creating or extending mobile mini-program UI pages for the AI自主学习系统, including login and phone verification, onboarding/profile setup modals, learning home pages, purchased/unpurchased states, pending/update/completed plan states, welcome cards, plan setup cards, AI learning tools, composition correction entry cards, composition score selection sheets, composition photo capture flows, photo order confirmation, OCR recognition and review, benefit-consumption confirmation, correction loading states, composition audio explanation pages, annotated essay walkthroughs, correction report generation, report preview/download, report intro/landing, composition correction history, monthly record filters, quota-exhausted composition entry states, feedback sheets, camera permission prompts, plan creation flows, learning information forms, plan knowledge-point selection, date picker sheets, validation/error states, generation loading states, generated plan overview pages, APP learning-plan pages, APP all-courses catalog pages, course outline/video-list pages, expanded or collapsed calendar states, scrolled calendar states, login-required learning-plan states, daily study plans, course recommendation grids, course commerce cards, plan history, sticky filters, empty states, and related education-product screens in the same visual style.
metadata:
  short-description: Generate AI自主学习系统 UI and作文批改 flows
---

# 学习系统UI-skill

Use this skill to generate new pages that match the existing AI自主学习系统 visual language.

## Core Direction

- Build a 375px or 390px mobile mini-program interface, matching the target screen family.
- Keep the product feeling quiet, clean, trustworthy, and study-focused.
- Use a pale cool background, soft blue top atmosphere, rounded white cards, compact tags, and direct task-oriented content.
- Do not create a marketing hero. The first screen should show useful learning content or the current learning state.

## Page Types

Use this skill for:

- Learning home with pending plan cards and history cards.
- Home recommendation pages with brand header, grade selector, welcome/plan setup card, AI学习工具 modules, and hot course recommendations.
- AI learning tool pages and overlays for作文批改, including monthly report cards, photo-correction entry cards, quota badges, quota-exhausted disabled entry states, full-score selection sheets, camera permission prompts, two-step photo capture, thumbnails, sorting, example overlays, photo order confirmation, OCR loading/review, benefit-consumption confirmation, correction loading, audio explanation walkthroughs, report generation, report preview/download, correction history records, monthly record filters, and feedback sheets.
- Login, phone verification, guest mode, and first-use grade/province setup flows.
- Purchased/unpurchased learning home states, including no-history empty states and sticky history filters.
- Plan creation flows, especially `学习信息` -> `计划考点` -> `生成计划`, score inputs, study-frequency chips, daily course-hour steppers, period cards, date picker sheets, knowledge-point selection sheets, generation loading, generated plan overview, and validation states.
- Daily learning plan pages with month title, subject legend, collapsed week calendar, expanded full-month calendar, scrolled calendar state, and task cards.
- APP `全部课程` pages with subject chips, course-cover carousel, course summary, module tabs, topic sidebar, video list, learning-status tags, and knowledge graph entry.
- APP learning-plan unauthenticated states that keep the product shell and either preserve or omit calendar context.
- Incomplete, completed, and no-plan learning states.
- Plan detail, course task detail, subject selection, and progress pages that extend the same system.

## Required Patterns

For home-like pages:

- Start with either a greeting row or a brand header plus grade selector.
- Use a prominent blue-green gradient card for welcome, plan setup, pending plans, or completed-plan success.
- When present, place `AI学习工具` between the plan card and `热门推荐`; use it for focused utility cards such as作文批改 rather than marketing banners.
- Use white rounded cards for history and secondary content; use compact two-column cards for course recommendations.
- Keep filters small: white background, light border, 10px radius, text plus down arrow.
- Distinguish `首次` and `更新` badges in pending-plan rows.

For entry/auth flows:

- Use the same pale cyan top atmosphere and soft glass white cards.
- Keep forms calm and minimal: rounded pale inputs, blue text links, black primary button, optional guest mode.
- Use modal overlays for required profile setup rather than taking users to a heavy configuration page.

For作文批改 capture flows:

- Use a dark camera-first interface with a two-step header: `拍题目` then `拍作文`.
- Request camera permission with a centered white modal when needed; primary action is `去开启`, secondary is `暂不开启`.
- Keep capture controls fixed at the bottom: gallery/image, large shutter, flashlight, iPhone home indicator, and captured-thumbnail strip above controls.
- Step 1 focuses on full prompt/material capture; Step 2 supports multiple作文 pages and can show `去排序`.
- Provide `查看示例` / `收起示例` for作文 page framing guidance without leaving the camera flow.
- After capture, use `确认作文顺序` to preview the selected photo, drag/sort thumbnails, continue补拍, or start recognition; show a confirmation modal before批改 if the user needs to verify order.
- OCR flow uses a centered recognition loading state, then `核对识别文字` with an assistant reminder, editable recognized title/body sections, and bottom actions `返回拍照` and `确认文字并批改`.
- Before final correction, confirm quota consumption with `确认开始批改？`; then show the dark expert-correction loading screen with scan/progress treatment and no extra CTA.
- After correction, support `作文讲解` screens that pair annotated作文 photos on the left with a narrow teacher commentary card on the right and fixed audio controls at the bottom.
- Use distinct walkthrough stages for起评分/审题立意, 加分项, 扣分项, 整体评价, and the final `查看批改报告` handoff.
- Report flow can include a promotional intro, report-generation loading, a scrollable report document preview, `重看讲解`/`下载报告`, and feedback bottom sheets.
- History flow can include `历史批改记录`, a monthly badge summary, score/category rows, `待解锁` rows, empty records, and a bottom month selector sheet.

For daily learning-plan pages:

- Top channel title: active `学习计划` with cyan underline, secondary `全部课程`.
- Assistant bubble under the title with state-specific copy.
- Month section: `{年份}年{月份}月计划`, `展开日历`, subject legend, weekday row, and date blocks.
- Expanded calendar switches the action to `收起日历`, shows month-switch controls, and uses the full 7-column month grid.
- Login-required APP plan states keep the top channel and active `学习` tab; use `请登录查看学习计划` and `立即登录`.
- Show task cards when there are plans; show a light illustration and `今日无计划~` when empty.
- Keep the bottom tabbar fixed with `首页`、`学习`、`我的`; active learning tab uses orange.

For APP all-courses pages:

- Top channel title switches active state to `全部课程`; `学习计划` becomes the muted secondary tab.
- Use subject chips below the tabs; selected subject is a black gradient pill, unselected subjects are white pills.
- Show a course-cover carousel before the outline content; center cover is primary, side covers are partially visible and faded.
- Course summary includes title, module/topic/test/video counts, teacher avatar/name, right-side utility icons, and a `知识图谱` pill.
- Below the summary, use module tabs, a left topic sidebar, and right-side grouped video cards with star difficulty, progress time, status tags, and orange play buttons.

For plan creation flows:

- Use a normal mini-program title bar with back arrow, centered title like `高二数学-春季自主计划`, and the WeChat capsule on the right.
- Place a three-step progress stepper below the title bar: `1 学习信息`、`2 计划考点`、`3 生成计划`.
- Keep the active step cyan-blue with a 22px numbered circle and soft halo; inactive steps are pale blue-gray with 2px gray dividers.
- Use a compact blue-green `伴学规划建议` card under the stepper before the form.
- Show season and enrollment context inside the advice card, e.g. `春季学季 · 在读 1 科` or `寒季学季 · 在读 2 科`.
- The advice card should explain the next two steps with short bullet lines and show recommended study-hour limits.
- Use pale rounded inputs for scores, target score, date fields, and picker rows.
- Use 40px rounded frequency chips such as `每周`、`每双周`、`每三周`、`每四周`; selected chip is white with `#00639E` border and blue text.
- Use 64px day/hour picker rows with minus and plus circular controls; values use MiSans 22px for the number and 13px for `课时`.
- Fix the bottom action container; enabled `下一步` is black gradient, disabled state uses 50% opacity.
- For 寒暑季 multi-period planning, group start/end dates and daily hours in white period cards, support placeholder and filled date states, show `删除` on filled removable periods, then add a bordered `＋ 添加时间段` row.
- For date selection, use a dimmed page overlay and a bottom sheet with rounded top corners; keep the calendar clean and confirm with a fixed black button.
- Show validation with red `#E70000` input borders and 14px red helper text directly below the field; disable the bottom action until errors are resolved.
- In step 2, completed prior steps use a green check circle; the active `计划考点` step keeps the cyan-blue numbered circle.
- Step 2 advice cards can be taller, around 306px, and should show matched season rhythm, suggested lesson and knowledge-point ranges, score-to-target guidance, and optional previous-season review; 寒季 two-month ranges can be smaller than spring ranges.
- Use a compact selector row for `计划学习{学科}考点（多选）`; empty state says `请选择`, selected state says `已选{n}个考点，{n}个视频`.
- Knowledge-point selection opens a dimmed bottom sheet with selected-count summary, expandable topic/subtopic groups, `全选`, star difficulty, `已学习` tags, circular check controls, and fixed `确认`; only include the recommendation card and `一键勾选未学习` when previous-season unfinished content exists.
- The final generation action is `开始生成学习计划`; use loading copy `正在生成学习计划` while generating.
- Generated plan pages use all three stepper items as green completed checks, a sync success card with `去学习`, a plan overview card, difficulty distribution, and a first-month calendar preview.
- APP learning-plan pages should keep the existing learning tab patterns while reflecting generated plan content from the creation flow.

## State Rules

- Incomplete: assistant says `{学生名}同学，请完成今天的学习计划吧`; task cards show progress time like `12:30/37:01`.
- Completed: assistant says `{学生名}同学，今日计划全部完成啦！真棒！`; task cards show full time like `37:01/37:01` plus `已学习`.
- No plan: assistant says `{学生名}同学，今日暂无学习计划，有余力的话可以前往课程继续充充电哟~`; content area shows centered empty illustration and `今日无计划~`.

## Reference

Before generating a full screen, read [references/ui-style-guide.md](references/ui-style-guide.md) for exact tokens, component dimensions, copy patterns, and checklist.
