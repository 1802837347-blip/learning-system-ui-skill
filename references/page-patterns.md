# AI自主学习系统 Page Patterns

Use this file to map arbitrary target pages into the AI自主学习系统 visual language. Preserve the source content hierarchy, then apply the closest page pattern and component specs.

## Page Adaptation Method

1. Identify the page's job: plan, course, practice,作文批改, report, auth, commerce, empty, or modal.
2. Keep the source page's information architecture unless the user explicitly asks for redesign.
3. Choose a page pattern below.
4. Build from shared components in `component-specs.md`.
5. Run `quality-gates.md` before delivery.

## Universal Style Principles

- The UI is functional and study-focused, not a marketing landing page.
- Use cool pale backgrounds, soft cyan atmosphere, white cards, compact tags, and purposeful gradients.
- Prefer dense but calm information layout over oversized hero text.
- Cards and controls should feel rounded and soft, but not childish: common radii are 8px, 10px, 12px, 16px, and 18px.
- Icons should be product-like SVG/assets, not emoji.
- Missing structural icons and default avatars must use the source/Figma asset, bundled `assets/icons/` or `assets/avatars/`, or a mature open-source icon library SVG copied locally. Do not hand-draw rough icons, expressive face avatars, emoji, or random initials as substitutes.
- Normal light app pages use `SystemStatusBar` from `component-specs.md`, backed by `assets/status-light.svg`; do not redraw or restyle the status bar.
- Arbitrary reference screenshots are not palette sources. Preserve their content and structure, but recolor UI fills, borders, CTAs, tabs, and badges with AI自主学习系统 cyan/blue tokens unless a page pattern explicitly defines another token.
- Do not invent new text, modules, or states when optimizing a Figma/screenshot target.

## Pattern: Home

Use for 首页 states: 未购课, 已购课-有更新, 已购课-完成全部计划, pending plan, history, and recommendation entry.

Required structure:

1. Status bar
2. `HomeHeader`
3. One primary home state card:
   - `HomeWelcomeGuideCard` for 未购课 / discovery state
   - `HomePendingPlanCard` for 已购课 with plans to create/update
   - `HomeSuccessPlanCard` for completed all plans
4. `热门推荐` section
5. `CourseProductGrid`
6. `BottomTabbar` with `首页` active

State rules:

- 未购课:
  - Use the 196px welcome guide card.
  - Show greeting, welcome title, and three-step value chain.
  - `热门推荐` starts around y 323px.
- 已购课-有更新 or pending:
  - Use the 305px pending plan gradient card.
  - Show season ribbon, AI greeting, 1 to 3 plan rows, `首次` or `更新` badges, and `去制定`.
  - `热门推荐` starts lower, around y 438px when the pending card has three rows.
- 完成全部计划:
  - Use the 211px success plan card.
  - Show central AI celebration, `太棒了!`, completion copy, and `去学习`.
  - `热门推荐` starts around y 347px.

Core rules:

- Home pages use a white page background, not the APP learning-plan pale sheet.
- Do not convert the home into a dashboard, calendar, or generic course list.
- Keep the brand header and grade selector visible.
- Recommendation products use two-column `CourseProductCard`s with real cover art or credible course-cover assets.
- Active bottom tab is `首页`, orange `#FF6200`; `学习` and `我的` are inactive.

## Pattern: APP Learning Plan

Use for daily plan, completed plan, no-plan, expanded calendar, login-required plan, and generated-plan handoff.

Required structure:

1. Status bar
2. `TopChannelTabs`
3. `AssistantBubble`
4. Month title and calendar action
5. `SubjectLegend`
6. `CollapsedWeekCalendar` or expanded month calendar
7. Course task cards, empty state, or login-required state
8. `BottomTabbar`

Core rules:

- `学习计划` is the active top tab unless the page is the all-courses tab.
- The `学习` bottom tab remains active for all learning-section pages.
- Calendar and task content sits on a pale `#F7F8F9` sheet.
- Incomplete state uses `CourseTaskCard`, not schedule cards.
- Empty/no-plan state is the only place to show a centered empty illustration and `今日无计划~`.

## Pattern: APP All Courses

Use for all-course catalog, course outline, module tabs, topic sidebar, and video list.

Required structure:

1. Status bar
2. Top tabs with `全部课程` active and `学习计划` secondary
3. Subject chips
4. Course-cover carousel
5. Course summary
6. Module tabs
7. Topic sidebar plus video list
8. Optional `上次学到` shortcut
9. Bottom tabbar with `学习` active

Core rules:

- Course covers are visual anchors; do not replace with blank flat cards.
- Left topic sidebar and right video list must use stable columns.
- Video cards use star difficulty, progress time, status tags, and orange play actions.

## Pattern: Knowledge-Point Study Overview

Use for exam knowledge-point pages such as `全考点学习` and `主观题专项`.

Required structure:

1. Status/top controls
2. Grade/subject segmented control
3. Progress summary metrics
4. `推荐你学` card
5. `全考点学习` / `主观题专项` tabs
6. Expandable topic cards
7. Progress rail, dots, lock states

Core rules:

- Preserve compact mobile scale.
- Keep progress rail, lock icons, and right values aligned to a grid.
- Active tab uses cyan underline; inactive tab stays gray.
- Do not remove structural icons.

## Pattern: Short-Answer Challenge

Use for `简答题专项` or gated challenge pages.

Required structure:

1. Browser/webview or status chrome, if present
2. Back navigation and page title
3. Main challenge title and chips
4. White rounded content sheet
5. Level tabs
6. Gradient intro module
7. Section header
8. Left step rail and right learning cards
9. Fixed purchase CTA if present

Core rules:

- Preserve browser chrome and domain pill if visible.
- The step rail uses one x-axis.
- Gradient intro module keeps gradient, border, shadow, and decorative icon.
- Match CTA color family from source.

## Pattern: Plan Creation Flow

Use for learning information, knowledge-point selection, period planning, generation, and generated overview.

Required structure:

1. Status bar and title bar
2. Three-step progress stepper
3. Companion planning advice card
4. Step-specific form or selector
5. Bottom action
6. Bottom sheet or modal when needed

Core rules:

- Stepper is not a card.
- Advice card is a core visual anchor.
- Inputs and selectors use pale rounded fills.
- Bottom action stays fixed and respects safe area.

## Pattern: Composition Correction

Use for作文批改 entry, photo capture, OCR, correction loading, explanation walkthrough, report, and history.

Required structure varies by state:

- Entry/report pages use pale app backgrounds and white cards.
- Capture and expert-correction loading use dark camera-family UI.
- Explanation pages pair作文 image evidence with teacher commentary and fixed audio controls.

Core rules:

- 作文 photos are primary content assets.
- If real photo is unavailable, create a believable manuscript fallback, not gray skeleton bars.
- Audio/control bars must not hide content.
- Preserve annotation colors and report stages.

## Pattern: Composition Batch Statistics

Use for `批改统计`, 作文批改历史, report-list, and batch-correction management pages.

Required structure:

1. `SystemStatusBar` using `assets/status-light.svg`
2. Native title bar with back chevron, centered `批改统计`, and mini-program capsule when present
3. Segmented tabs for states such as `已领取15/分享30`, `待批改5`, `完成批改10`
4. Scrollable report list using `CompositionReportListCard`
5. Bottom tabbar when the source shell includes it

Card required structure:

1. Primary row: avatar, user name, phone number, and `查看报告` action when the report is available
2. Detail panel: `作文标题` and `提交时间`
3. Result row: score such as `42分` and category such as `3档`

Core rules:

- Preserve the source's visible names, phone numbers, counts, tab labels, titles, times, scores, and categories.
- Do not simplify cards to only avatar/name/phone. Missing `查看报告`, `作文标题`, `提交时间`, score, or category fails this pattern.
- Use `assets/avatars/default-parent.svg` when a real avatar is unavailable; do not invent decorative profile art.
- Bottom tabbar and row actions use local icon assets: `house.svg`, `file-check.svg`, `circle-user-round.svg`, `chevron-right.svg`, and `chevron-left.svg` as appropriate.
- Use cyan/blue palette mapping only: blue score pills, pale-blue category tags, blue outlined `查看报告`, and pale-blue detail borders.
- Do not inherit source orange, peach, beige, or brown colors into the list UI.
- Decorative icons, avatars, and empty-state illustrations should preserve source geometry or bundled assets, but any warm non-content fills/strokes must be recolored to cyan/blue tokens.
- Keep list card typography compact: names around 16px to 18px, phone/details around 13px to 15px, not oversized.

## Pattern: Composition Score Snapshot

Use when the page is close to the Figma score/rank pages `4424:491` or `5201:3715`, or when the source/product requirement is a single作文 metric, category result, rank summary, score snapshot, no-value score state, or locked score/category state.

Required structure:

1. `SystemStatusBar` using `assets/status-light.svg`
2. Native title bar if the source page has one
3. Cool cyan/blue page atmosphere
4. `CompositionSingleDataImmersiveCard`
5. Supporting detail rows/cards only when present in the source
6. No-content fallback using `assets/composition/empty-no-content.svg` when the source has no data

Core rules:

- Match the target page's calm cyan/blue system, compact type, white/pale card surfaces, soft shadows, and generous mobile spacing.
- Single data card layout is left title/data and right medal/badge. Do not convert it into a centered dashboard card.
- Use `badge-valued.svg` when the data has a value and `badge-empty.svg` when it has no value.
- Use rank assets `tag-rank-1.svg` through `tag-rank-5.svg` for `一类` to `五类`; use `tag-locked.svg` for `待解锁`.
- Preserve exact visible labels, numbers, scores, dates, and explanatory copy from the source.
- Warm colors inside these SVG assets are allowed as target assets; surrounding UI remains cyan/blue.

## Pattern: Composition Correction History Records

Use when the target is `历史批改记录`, monthly作文批改 records, month-filtered correction history, or when the UI closely matches [reference-history-records.png](../assets/composition/reference-history-records.png) / [reference-history-empty.png](../assets/composition/reference-history-empty.png).

Required structure:

1. Full cyan/teal gradient header, 390px wide, down to y 212px
2. White `SystemStatusBar` using `assets/status-white.svg`
3. Transparent title bar with white back chevron and centered `历史批改记录`
4. Monthly summary: left white copy, right monthly badge (`badge-valued.svg` or `badge-empty.svg`)
5. White rounded-top sheet starting at y 212px
6. Sheet header: `批改记录` left, month pill `2026年4月` right
7. Records state: list rows using `CompositionEssayRecordListItem`
8. Empty state: centered `empty-no-content.svg` and `暂无批改记录`

Record row rules:

- Use the image's exact hierarchy: left score plus rank/locked asset, right title plus time/state, far-right chevron.
- Rows are separated by 1px dividers and sit directly on the white sheet, not inside independent rounded cards.
- Score text is black and compact; category labels must use the bundled SVG assets.
- Locked row replaces score/category with `tag-locked.svg` and uses subtitle `完成讲解即可解锁完整批改报告` when present.
- Do not add avatars, phone numbers, or `查看报告` buttons to this page.
- Keep the month filter visible even when there are no records.

Exact layout anchors from Figma `4424:491` / `5201:3715`:

- Canvas is 390px wide. Header gradient runs behind the status/title/summary area; the white sheet begins at y 212px with 20px top radius.
- Header summary text starts near x 18px, y 121px. Use two white MiSans Demibold lines, 19px then 17px, both 22px line-height.
- Records-state header uses `本月已完成 5 篇作文练习` / `持续保持这个节奏～`; empty-state header uses `本月还没有进行作文练习` / `快练习批改下吧～`.
- Sheet header begins at y about 232px. The month pill stays on the right in both records and empty states.
- List rows start at y about 266px, width 358px, x 16px. Row padding is 20px vertical; left score/rank block and right title/time block are horizontally aligned.
- Empty illustration is centered in the sheet, not in the gradient header.

## Pattern: Composition Essay Record List

Use when the source/product requirement is a作文列表, 作文批改列表, 历史作文记录, report/essay record list, or repeated items where each row contains a score/category plus title/time.

Required structure:

1. `SystemStatusBar` using `assets/status-light.svg`
2. Native title/filter/tab area when present
3. Scrollable list using `CompositionEssayRecordListItem`
4. Empty state using `assets/composition/empty-no-content.svg` when the list has no records

Card/list item structure:

1. Left column: score such as `42分` plus rank tag `一类` to `五类` or `待解锁`
2. Right column:作文标题/title on top and提交时间/time below

Core rules:

- Match the exact left-score/right-title-time hierarchy. Do not use avatar/name/phone or report-button hierarchy unless the source actually contains it.
- Keep score/rank on the left and title/time on the right.
- Use bundled rank SVGs for category tags; do not draw CSS text pills.
- Preserve exact titles, scores, categories, and times.
- Use cool white cards, gray-blue detail text, and blue/cyan score emphasis.

## Pattern: Modal And Sheet

Use for setup, score selection, date picker, knowledge-point selection, confirmations, and feedback.

Core rules:

- Dim current page behind the modal/sheet.
- Bottom sheets have rounded top corners and fixed bottom action if needed.
- Center modals are compact, white, and action-focused.
- Do not over-explain inside modals.

## Pattern Selection For Arbitrary Pages

If the source page is not one of the known screens:

- Product landing/home/recommendation entry -> Home.
- Learning dashboard or schedule -> APP Learning Plan.
- Course catalog or curriculum -> APP All Courses.
- Exam knowledge list -> Knowledge-Point Study Overview.
- Gated practice/challenge -> Short-Answer Challenge.
- Multi-step setup/form -> Plan Creation Flow.
- Photo/report/writing feedback -> Composition Correction.
- `历史批改记录` or monthly correction records -> Composition Correction History Records.
- Single作文 score/category summary -> Composition Score Snapshot.
- 作文列表 or repeated title/time rows with score/category -> Composition Essay Record List.
- Dialog/picker -> Modal And Sheet.

For `批改统计`, 作文批改历史, report-list, or batch-correction management screens, map to Composition Batch Statistics.
If a作文 page has no avatar/phone/report action and instead shows score/category with title/time, map to Composition Essay Record List instead of Composition Batch Statistics.

When uncertain, use shared tokens and components, but keep the source hierarchy. The goal is style transfer, not content redesign.
