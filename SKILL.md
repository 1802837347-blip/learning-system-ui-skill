---
name: 学习系统UI-skill
description: Use this skill when creating, optimizing, or reviewing mobile mini-program UI pages for the AI自主学习系统. It enforces the AI自主学习系统 cyan/blue palette, bundled status bar asset, source-content preservation, source illustration/icon extraction, composition score/rank assets, immersive single-data cards, essay record lists, and page patterns for learning plans, courses,作文批改/report/history, login, onboarding, plan creation, APP learning-plan pages, knowledge-point pages, short-answer challenge pages, all-courses pages, empty/loading/error states, and related education-product screens.
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

## Hard Output Contract

These constraints override source screenshots and generic UI instincts:

1. Reference screenshots provide information architecture, copy, counts, spacing clues, and extractable assets. They are not palette sources.
2. All UI chrome must use AI自主学习系统 tokens: cyan/blue atmosphere, blue/cyan selected states, white cards, gray-blue text, and blue actions. Orange, brown, beige, peach, amber, tan, and warm gradients from arbitrary references are failures unless an exact component spec explicitly allows that warm token.
3. Source illustrations and icons are locked for shape/detail/style, but their UI-facing colors are not locked. If an extracted icon or illustration contains warm colors that conflict with the cyan/blue system, keep its geometry and detail while remapping non-content colors into the cyan/blue token family. Preserve natural colors only for photos, course covers,作文 images, manuscript/report evidence, and other real content media.
4. Normal light app pages must use [assets/status-light.svg](assets/status-light.svg) directly for the status bar. Full cyan/blue immersive header pages such as `历史批改记录` must use [assets/status-white.svg](assets/status-white.svg). Do not redraw `9:41`, cellular signal, Wi-Fi, or battery.
5. If the source contains required data, the optimized UI must keep it. For batch/composition report list pages, cards must not collapse to avatar/name/phone only; they must preserve report action, title, submit time, score, and category/dang when present.
6. When content matches作文 score/rank summaries, use the bundled composition rank/tag assets instead of drawing new badges. Single data display pages use an immersive card with the title/content on the left and the badge/medal on the right. Essay record lists use left score+rank and right title+time.
7. When content matches `历史批改记录`, monthly作文 records, or the Figma nodes `4424:491` / `5201:3715`, use the exact history-record structure: cyan/blue immersive header, white status bar, white rounded-top sheet, month filter, and record rows with left score/rank asset plus right title/time. Do not fall back to generic cards, avatars, phone numbers, or report-button rows.

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
2. For UI generation and review, first read [references/design.md](references/design.md) and [references/design.tokens.json](references/design.tokens.json). These are the primary source of truth for spacing, type scale, radius, color, gradients, icons, and component behavior.
3. For implementation work, also use [references/tokens.css](references/tokens.css) and [references/tailwind.config.ts](references/tailwind.config.ts) when relevant instead of inventing one-off CSS values.
4. Read [references/page-patterns.md](references/page-patterns.md) and choose the closest page pattern. For arbitrary pages, map the source to the nearest pattern instead of inventing a new visual system.
5. Read [references/component-specs.md](references/component-specs.md) for reusable component anatomy, dimensions, spacing, colors, radius, shadows, and icon rules.
6. Read [references/ui-style-guide.md](references/ui-style-guide.md) when the task needs older extracted page details or a page-specific fallback not yet covered by `design.md`.
7. If optimizing or reviewing a generated page, also read [references/quality-gates.md](references/quality-gates.md) and run the priority checks before final output.
8. Preserve the user's original text and information architecture unless they explicitly ask for content changes.
9. When outputting HTML or code, prefer resilient layout primitives: flex/grid, `box-sizing: border-box`, `min-height`, safe-area padding, and content-driven spacing.
10. Treat real images, course covers,作文 photos, icons, and report previews as primary content assets. Preserve them when provided; create meaningful fallbacks only when assets are unavailable.
11. When optimizing from a screenshot or existing UI, preserve the source illustration and icon style. If no bundled asset or clearly better product asset exists, extract/crop/trace the original illustration or icon from the source and place it back into the optimized UI; do not redraw a simplified replacement from scratch. For UI illustrations/icons, preserve shape/detail while recoloring warm non-content fills/strokes into cyan/blue tokens when the source palette conflicts with this skill.
12. Use the AI自主学习系统 status bar consistently. For ordinary light app pages, use bundled [assets/status-light.svg](assets/status-light.svg) at 390px by 44px. For full cyan/blue immersive header pages such as `历史批改记录`, use bundled [assets/status-white.svg](assets/status-white.svg) with the same geometry. Do not redraw the signal, Wi-Fi, battery, or `9:41` time when these assets are available. Do not invent yellow battery pills, mismatched icon weights, or alternate status chrome unless the source page explicitly requires a different shell.
13. Do not inherit color from arbitrary source/reference screenshots. Use the screenshot for content, layout, hierarchy, and asset extraction only; remap all UI fills, borders, gradients, badges, CTAs, and emphasis colors to this skill's AI自主学习系统 tokens, with a cyan/blue-dominant palette. Orange, brown, beige, peach, and warm gradients from the source are forbidden unless the target page section in this skill explicitly defines that exact warm token for that exact component.
14. If the source is a high-resolution screenshot, normalize it to a 375px or 390px CSS canvas before choosing font sizes, spacing, and icon sizes. Do not copy raw screenshot pixels as CSS pixels.
15. If a Figma node or screenshot is provided, treat every visible text string, tab, date, subject legend item, card count, and icon family as locked unless the user asks to redesign content. Treat source colors as unlocked unless the source is the explicit target Figma for this skill.
16. For APP learning-plan screens, preserve the foundational UI tokens from the Figma reference: top tab selected style, assistant avatar/bubble, collapsed calendar heights and date states, course-card anatomy, and right play button style.
17. For HTML/CSS output, run `node scripts/audit-ui-output.mjs <output-file>` before final delivery when the file is available, then fix any failures it reports.
18. Before final delivery, verify the screen at the target phone width and fix any oversized type, missing icons, overflow, clipping, hidden fixed-bar content, low-contrast text, tiny tap targets, source-color leakage, missing batch-statistics fields, or misaligned borders.

## Page Types

Use this skill for:

- Learning home with pending plan cards and history cards.
- Home recommendation pages with brand header, grade selector, welcome/plan setup card, AI学习工具 modules, and hot course recommendations.
- AI learning tool pages and overlays for作文批改, including monthly report cards, photo-correction entry cards, quota badges, quota-exhausted disabled entry states, full-score selection sheets, camera permission prompts, two-step photo capture, thumbnails, sorting, example overlays, photo order confirmation, OCR loading/review, benefit-consumption confirmation, correction loading, audio explanation walkthroughs, report generation, report preview/download, correction history records, monthly record filters, and feedback sheets.
- Composition score/rank summary pages, including single data display pages with a medal on the right, essay record lists with score/rank on the left and title/time on the right, one-to-five category tags, locked category states, valued/empty medal states, and no-content fallbacks.
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
- Treat source illustrations and icons as locked visual assets during UI optimization. Prefer source-cropped PNG/WebP assets, traced SVGs that faithfully match the source, or existing bundled assets. Only create a new self-drawn fallback when the source asset is absent/unusable and no better replacement exists; the fallback must stay visually subordinate and must not degrade the original icon/illustration style.
- Reuse bundled assets when available. For the APP learning-plan assistant avatar, use [assets/assistant-avatar.png](assets/assistant-avatar.png) at 40px visual size instead of redrawing a generic `AI` icon.

For home-like pages:

- Start with either a greeting row or a brand header plus grade selector.
- Use the Home page pattern for 首页 states: 未购课 welcome guide, 已购课待制定/有更新 pending plan card, and 完成全部计划 success card.
- Use a prominent blue-green gradient card for welcome, plan setup, pending plans, or completed-plan success.
- When present, place `AI学习工具` between the plan card and `热门推荐`; use it for focused utility cards such as作文批改 rather than marketing banners.
- Use white rounded cards for history and secondary content; use compact two-column cards for course recommendations.
- Keep filters small: white background, light border, 10px radius, text plus down arrow.
- Distinguish `首次` and `更新` badges in pending-plan rows.
- `热门推荐` course products use two columns with real course covers, red price, and orange `抢` badge; do not replace them with generic cards.

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
- For `批改统计`, 作文批改历史, report-list, or batch-correction management pages, do not inherit source orange. Use cyan/blue score pills, pale-blue category tags, blue outlined `查看报告` actions, and pale-blue detail borders unless the exact target Figma node says otherwise.
- For score/rank summary pages that match the Figma nodes `4424:491` or `5201:3715`, preserve the source style one-to-one: use bundled [assets/composition/badge-valued.svg](assets/composition/badge-valued.svg), [assets/composition/badge-empty.svg](assets/composition/badge-empty.svg), [assets/composition/empty-no-content.svg](assets/composition/empty-no-content.svg), [assets/composition/tag-locked.svg](assets/composition/tag-locked.svg), and rank tag assets [tag-rank-1.svg](assets/composition/tag-rank-1.svg) through [tag-rank-5.svg](assets/composition/tag-rank-5.svg). Do not replace these with CSS pills, emoji medals, or generic icons.
- For `历史批改记录`, use [assets/status-white.svg](assets/status-white.svg) and the reference screenshots [assets/composition/reference-history-records.png](assets/composition/reference-history-records.png) and [assets/composition/reference-history-empty.png](assets/composition/reference-history-empty.png) as visual anchors.

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

For UI generation and review, read:

- [references/design.md](references/design.md)
- [references/design.tokens.json](references/design.tokens.json)

For implementation work, also use when relevant:

- [references/tokens.css](references/tokens.css)
- [references/tailwind.config.ts](references/tailwind.config.ts)

For page-specific patterns, use:

- [references/page-patterns.md](references/page-patterns.md)
- [references/component-specs.md](references/component-specs.md)
- [references/ui-style-guide.md](references/ui-style-guide.md)

Before delivering an optimized or reviewed screen, read [references/quality-gates.md](references/quality-gates.md) and pass the critical layout, containment, and interaction checks.
