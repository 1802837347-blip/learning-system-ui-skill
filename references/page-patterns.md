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
- Normal light app pages use `SystemStatusBar` from `component-specs.md`, backed by `assets/status-light.svg`; do not redraw or restyle the status bar.
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
- Dialog/picker -> Modal And Sheet.

When uncertain, use shared tokens and components, but keep the source hierarchy. The goal is style transfer, not content redesign.
