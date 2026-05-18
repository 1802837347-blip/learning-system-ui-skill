---
name: 学习系统UI-skill
description: Use this skill when creating or extending mobile mini-program UI pages for the AI自主学习系统, including login and phone verification, onboarding/profile setup modals, learning home pages, purchased/unpurchased states, pending/update/completed plan states, welcome cards, plan setup cards, plan creation flows, learning information forms, plan knowledge-point selection, date picker sheets, validation/error states, generation loading states, generated plan overview pages, APP learning-plan pages, daily study plans, course recommendation grids, course commerce cards, plan history, sticky filters, calendar states, empty states, and related education-product screens in the same visual style.
metadata:
  short-description: Generate AI自主学习系统 mobile UI pages
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
- Home recommendation pages with brand header, grade selector, welcome/plan setup card, and hot course recommendations.
- Login, phone verification, guest mode, and first-use grade/province setup flows.
- Purchased/unpurchased learning home states, including no-history empty states and sticky history filters.
- Plan creation flows, especially `学习信息` -> `计划考点` -> `生成计划`, score inputs, study-frequency chips, daily course-hour steppers, period cards, date picker sheets, knowledge-point selection sheets, generation loading, generated plan overview, and validation states.
- Daily learning plan pages with month title, subject legend, week calendar, and task cards.
- Incomplete, completed, and no-plan learning states.
- Plan detail, course task detail, subject selection, and progress pages that extend the same system.

## Required Patterns

For home-like pages:

- Start with either a greeting row or a brand header plus grade selector.
- Use a prominent blue-green gradient card for welcome, plan setup, pending plans, or completed-plan success.
- Use white rounded cards for history and secondary content; use compact two-column cards for course recommendations.
- Keep filters small: white background, light border, 10px radius, text plus down arrow.
- Distinguish `首次` and `更新` badges in pending-plan rows.

For entry/auth flows:

- Use the same pale cyan top atmosphere and soft glass white cards.
- Keep forms calm and minimal: rounded pale inputs, blue text links, black primary button, optional guest mode.
- Use modal overlays for required profile setup rather than taking users to a heavy configuration page.

For daily learning-plan pages:

- Top channel title: active `学习计划` with cyan underline, secondary `全部课程`.
- Assistant bubble under the title with state-specific copy.
- Month section: `{年份}年{月份}月计划`, `展开日历`, subject legend, weekday row, and date blocks.
- Show task cards when there are plans; show a light illustration and `今日无计划~` when empty.
- Keep the bottom tabbar fixed with `首页`、`学习`、`我的`; active learning tab uses orange.

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
- For multi-period planning, group start/end dates and daily hours in white period cards, then add a bordered `＋ 添加时间段` row.
- For date selection, use a dimmed page overlay and a bottom sheet with rounded top corners; keep the calendar clean and confirm with a fixed black button.
- Show validation with red `#E70000` input borders and 14px red helper text directly below the field; disable the bottom action until errors are resolved.
- In step 2, completed prior steps use a green check circle; the active `计划考点` step keeps the cyan-blue numbered circle.
- Step 2 advice cards can be taller, around 306px, and should show matched season rhythm, suggested lesson and knowledge-point ranges, score-to-target guidance, and optional previous-season review.
- Use a compact selector row for `计划学习{学科}考点（多选）`; empty state says `请选择`, selected state says `已选{n}个考点，{n}个视频`.
- Knowledge-point selection opens a dimmed bottom sheet with selected-count summary, recommendation card, expandable topic/subtopic groups, `全选`, `一键勾选未学习`, star difficulty, `已学习` tags, circular check controls, and fixed `确认`.
- The final generation action is `开始生成学习计划`; use loading copy `正在生成学习计划` while generating.
- Generated plan pages use all three stepper items as green completed checks, a sync success card with `去学习`, a plan overview card, difficulty distribution, and a first-month calendar preview.
- APP learning-plan pages should keep the existing learning tab patterns while reflecting generated plan content from the creation flow.

## State Rules

- Incomplete: assistant says `{学生名}同学，请完成今天的学习计划吧`; task cards show progress time like `12:30/37:01`.
- Completed: assistant says `{学生名}同学，今日计划全部完成啦！真棒！`; task cards show full time like `37:01/37:01` plus `已学习`.
- No plan: assistant says `{学生名}同学，今日暂无学习计划，有余力的话可以前往课程继续充充电哟~`; content area shows centered empty illustration and `今日无计划~`.

## Reference

Before generating a full screen, read [references/ui-style-guide.md](references/ui-style-guide.md) for exact tokens, component dimensions, copy patterns, and checklist.
