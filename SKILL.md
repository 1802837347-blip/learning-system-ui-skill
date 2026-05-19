---
name: 学习系统UI-skill
description: Use this skill when creating or extending mobile mini-program UI pages for the AI自主学习系统, including login and phone verification, onboarding/profile setup modals, learning home pages, purchased/unpurchased states, pending/update/completed plan states, welcome cards, plan setup cards, AI learning tools, composition correction entry cards, composition score selection sheets, composition photo capture flows, photo order confirmation, OCR recognition and review, benefit-consumption confirmation, correction loading states, composition audio explanation pages, annotated essay walkthroughs, correction report generation, report preview/download, report intro/landing, composition correction history, monthly record filters, quota-exhausted composition entry states, feedback sheets, camera permission prompts, plan creation flows, learning information forms, plan knowledge-point selection, date picker sheets, validation/error states, generation loading states, generated plan overview pages, APP learning-plan pages, knowledge-point overview pages, short-answer challenge / 闯关专项 pages, APP all-courses catalog pages, course outline/video-list pages, expanded or collapsed calendar states, scrolled calendar states, login-required learning-plan states, daily study plans, course recommendation grids, course commerce cards, plan history, sticky filters, empty states, and related education-product screens in the same visual style.
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

## When to Apply

Use this skill when the task changes how an AI自主学习系统 page looks, feels, lays out content, or handles visible state.

Must use it for:

- Creating or extending learning-plan, course,作文批改, report, history, login, or onboarding screens.
- Optimizing existing HTML, mini-program, React, or mobile UI output to match this product family.
- Reviewing UI for spacing, containment, card structure, states, typography, or visual consistency.
- Fixing visible layout bugs such as clipped text, escaped buttons, broken badge borders, crowded metrics, or hidden fixed bars.

Skip it for pure backend logic, database/API work, or non-visual automation.

## Workflow

1. Identify the page family and state: home, daily plan, all courses, plan creation,作文批改 capture, report, history, auth, or empty/loading/error state.
2. Read [references/ui-style-guide.md](references/ui-style-guide.md) for the matching component and copy patterns.
3. If optimizing or reviewing a generated page, also read [references/quality-gates.md](references/quality-gates.md) and run the priority checks before final output.
4. Preserve the user's original text and information architecture unless they explicitly ask for content changes.
5. When outputting HTML or code, prefer resilient layout primitives: flex/grid, `box-sizing: border-box`, `min-height`, safe-area padding, and content-driven spacing.
6. Treat real images, course covers,作文 photos, icons, and report previews as primary content assets. Preserve them when provided; create meaningful fallbacks only when assets are unavailable.
7. If the source is a high-resolution screenshot, normalize it to a 375px or 390px CSS canvas before choosing font sizes, spacing, and icon sizes. Do not copy raw screenshot pixels as CSS pixels.
8. If a Figma node or screenshot is provided, treat every visible text string, tab, date, subject legend item, card count, and icon family as locked unless the user asks to redesign content.
9. For APP learning-plan screens, preserve the foundational UI tokens from the Figma reference: top tab selected style, assistant avatar/bubble, collapsed calendar heights and date states, course-card anatomy, and right play button style.
10. Before final delivery, verify the screen at the target phone width and fix any oversized type, missing icons, overflow, clipping, hidden fixed-bar content, low-contrast text, tiny tap targets, or misaligned borders.

## Page Types

Use this skill for:

- Learning home with pending plan cards and history cards.
- Home recommendation pages with brand header, grade selector, welcome/plan setup card, AI学习工具 modules, and hot course recommendations.
- AI learning tool pages and overlays for作文批改, including monthly report cards, photo-correction entry cards, quota badges, quota-exhausted disabled entry states, full-score selection sheets, camera permission prompts, two-step photo capture, thumbnails, sorting, example overlays, photo order confirmation, OCR loading/review, benefit-consumption confirmation, correction loading, audio explanation walkthroughs, report generation, report preview/download, correction history records, monthly record filters, and feedback sheets.
- Login, phone verification, guest mode, and first-use grade/province setup flows.
- Purchased/unpurchased learning home states, including no-history empty states and sticky history filters.
- Plan creation flows, especially `学习信息` -> `计划考点` -> `生成计划`, score inputs, study-frequency chips, daily course-hour steppers, period cards, date picker sheets, knowledge-point selection sheets, generation loading, generated plan overview, and validation states.
- Daily learning plan pages with month title, subject legend, collapsed week calendar, expanded full-month calendar, scrolled calendar state, and task cards.
- APP learning-plan incomplete state, with `学习计划` active, assistant reminder, month/week calendar, subject legend, unfinished course cards, and active `学习` bottom tab.
- Knowledge-point study overview pages with grade/subject segmented controls, progress summary metrics, `推荐你学` card, `全考点学习` / `主观题专项` tabs, expandable topic cards, progress rails, lock states, and discount badges.
- Short-answer challenge / 闯关专项 pages with browser-style status chrome, refined back navigation, level tabs, gradient intro module, left step rail, locked nodes, learning cards, and fixed purchase CTA.
- APP `全部课程` pages with subject chips, course-cover carousel, course summary, module tabs, topic sidebar, video list, learning-status tags, and knowledge graph entry.
- APP learning-plan unauthenticated states that keep the product shell and either preserve or omit calendar context.
- Incomplete, completed, and no-plan learning states.
- Plan detail, course task detail, subject selection, and progress pages that extend the same system.

## Required Patterns

For every generated screen:

- Treat every visible card as a real containment boundary: titles, metrics, tags, and primary CTAs must sit inside the card's padding box.
- Prefer flex/grid layout for card internals. Avoid absolute-positioning CTAs or tags inside cards unless the parent is `position: relative` and the card reserves enough right/bottom padding for them.
- Use `min-height` instead of tight fixed heights when card content includes stats, two-line copy, badges, or buttons.
- Before final output, check that no text, tag, button, icon, or border crosses its parent card edge or is clipped by insufficient height.
- Tags and stage badges use a single clear fill plus one border; avoid doubled outlines, misaligned pseudo-element borders, or clipped gradient strokes.
- Treat作文 photos as content assets, not decorative placeholders. If no real image asset is provided, create a believable handwritten essay sheet with Chinese text strokes, grid paper, score marks, and colored annotations; never replace the essay image with only generic horizontal bars.
- Reuse bundled assets when available. For the APP learning-plan assistant avatar, use [assets/assistant-avatar.png](assets/assistant-avatar.png) at 40px visual size instead of redrawing a generic `AI` icon.

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
- The作文 photo area is the core evidence of this flow. Preserve real photo texture when available; otherwise render a plausible essay manuscript, not a skeleton placeholder.
- Use distinct walkthrough stages for起评分/审题立意, 加分项, 扣分项, 整体评价, and the final `查看批改报告` handoff.
- Report flow can include a promotional intro, report-generation loading, a scrollable report document preview, `重看讲解`/`下载报告`, and feedback bottom sheets.
- History flow can include `历史批改记录`, a monthly badge summary, score/category rows, `待解锁` rows, empty records, and a bottom month selector sheet.

For daily learning-plan pages:

- Do not reinterpret this page as a generic CRM, work schedule, customer communication, or office task dashboard. Keep all copy and information architecture in the education/learning-plan domain.
- Top channel title: active `学习计划` with cyan underline, secondary `全部课程`.
- Do not add controls that are absent from the Figma target, such as a search button, greeting headline, task-completion counter, or extra section title.
- Assistant bubble under the title uses the source's state-specific one-line copy; do not append estimated duration, task counts, or schedule summary.
- Month section: `{年份}年{月份}月计划`, `展开日历`, subject legend, weekday row, and date blocks. Keep the exact visible year/month, weekday order, dates, selected day, and subject dots from the source.
- Expanded calendar switches the action to `收起日历`, shows month-switch controls, and uses the full 7-column month grid.
- Login-required APP plan states keep the top channel and active `学习` tab; use `请登录查看学习计划` and `立即登录`.
- In incomplete state, show unfinished course task cards with subject tag, knowledge point, title, star/progress indicator, time progress, and circular play action. Do not turn them into time-slot schedule cards with `未开始` badges.
- In the Figma `APP-学习计划-未完成` reference, the task cards start immediately after the collapsed week calendar; there is no separate `今日任务` / `今日安排` header row.
- Show a light illustration and `今日无计划~` only for the no-plan/empty state, not for incomplete state.
- Keep the bottom tabbar fixed with `首页`、`学习`、`我的`; active learning tab uses orange.

For knowledge-point study overview pages:

- Preserve the compact mobile scale. Do not enlarge text because the prompt screenshot is high resolution.
- Keep the top controls, summary metrics, recommendation card, tabs, topic cards, progress rail, expand/collapse icons, and lock icons aligned to the same grid.
- Every structural icon must render: back arrow, status icons, segmented-control markers, sparkle/discount badge accents, expand/collapse circles, progress dots, and lock icons.
- Use `全考点学习` and `主观题专项` as learning tabs; active tab gets the cyan underline. Do not replace them with generic section headings.

For short-answer challenge pages:

- Preserve the browser or webview chrome when the source shows it: time, centered domain pill such as `uinotes.com`, ellipsis, Wi-Fi, battery, and home indicator are part of the visible page.
- The top-left back control must match the reference: use a clean SVG chevron with round caps/joins; do not wrap it in a square or circle unless the source has that container.
- Keep the pale blue page atmosphere and white rounded content sheet. Do not flatten the top area into a plain card stack.
- Level tabs such as `第一关`、`第二关`、`第三关` share a baseline; the active tab has a short blue underline, and badges such as `试用` sit above the correct tab without pushing labels out of alignment.
- Gradient intro modules are functional content. Match the blue/lavender fill, border, rounded corners, shadow, and right-side decorative learning icon instead of replacing the module with a flat pale rectangle.
- The left step rail uses one fixed x-axis. Active number nodes, locked nodes, and the vertical line must align with the card stack and with the corresponding card centers.
- Learning cards reserve a fixed left gutter for the step rail and a content column for titles, helper blocks, `去学习`, and chevrons. Do not let cards overlap the rail or drift away from their nodes.
- Bottom purchase CTA color must match the source. If the reference uses a blue gradient `立即购买` pill, do not replace it with the generic black action gradient.

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

Before delivering an optimized or reviewed screen, read [references/quality-gates.md](references/quality-gates.md) and pass the critical layout, containment, and interaction checks.
