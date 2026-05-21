# AI自主学习系统 Component Specs

Use this file before generating or optimizing a page. It defines reusable component anatomy so the UI can be applied to arbitrary pages without losing the AI自主学习系统 style.

## Component Workflow

1. Identify which components exist in the target page.
2. Preserve the target page's original content and hierarchy.
3. Replace only the visual treatment with the closest component specs below.
4. After implementation, check containment, icon rendering, gradients, spacing, and state styles.

## Global Tokens

- Mobile canvas: 375px or 390px CSS width.
- Background: cool pale base `#ECEEF5`, `#F0F2FA`, or `#F7F8F9`.
- Top atmosphere: `#BFF9FF` fading to transparent, usually 224px to 256px tall.
- Primary text: `#071D39`, `#191C1E`, or near black.
- Muted text: `#77838B`, `#78818D`, `#8E9194`.
- Active cyan: `#47EFF9`.
- Learning active orange: `#FF6200`.
- Card fill: `#FFFFFF`.
- Thin border: `rgba(188,200,208,0.2)` or `#E9E8E8`.
- Main card radius: 12px to 18px.
- Compact tag radius: 4px to 8px.
- Default card shadow: subtle, around `0 1px 1px rgba(0,0,0,0.05)`.
- Blue card shadow: `0 9px 18px rgba(50,131,198,0.22)`.

## Color Remapping

Use for any optimization from an arbitrary screenshot.

- Source screenshots do not provide the palette. They provide structure, copy, and extractable assets only.
- Extracted UI icons and illustrations preserve shape/detail, not arbitrary warm palette. Recolor non-content warm fills/strokes to cyan/blue tokens unless the asset is real content media.
- Remap warm source UI colors to AI自主学习系统 tokens:
  - Orange primary tabs/buttons -> blue/cyan gradient or `#00639E`.
  - Orange score pills/category pills -> blue fill `#00A7D8` or pale blue fill `#CCE9FB` with blue text.
  - Peach/beige detail borders -> pale blue border `#CCE9FB` or `rgba(0,167,216,0.18)`.
  - Brown text -> primary text `#071D39` or secondary `#78818D`.
- Keep allowed warm tokens only where this spec explicitly names them, such as commerce sale badges, update badges, or APP bottom tab active orange.
- If the target page is a作文批改 statistics/history/report list page, score, category, and report actions default to the cyan/blue family, not orange.

## AssetColorPolicy

Use this policy whenever a source screenshot includes illustrations or icons.

- Content media keeps natural/source color: course covers, teacher/product photos,作文 photos, manuscript/report screenshots, and evidence images.
- Decorative UI assets keep source shape/detail but follow the skill palette: tabbar icons, report/list icons, empty-state illustrations, helper illustrations, decorative people/objects, and generated inline SVGs.
- If a decorative asset contains warm orange/peach/brown/beige colors, remap them to `#00639E`, `#00A7D8`, `#0EC5FF`, `#BFF9FF`, `#CCE9FB`, or gray-blue neutrals.
- Do not create a new simplified drawing to avoid recoloring. First extract/trace the source asset, then recolor it.

## Icon Library And Avatar Assets

Use this whenever a page needs structural icons, tabbar icons, row chevrons, locks, play buttons, search controls, or default user avatars.

Icon selection priority:

1. Source/Figma icon or product asset, if present and usable.
2. Bundled local asset in `assets/icons/` or `assets/avatars/`.
3. Mature open-source icon library match copied locally: Lucide first, then Tabler, Heroicons, Phosphor, MingCute, Iconoir, or Material Symbols.
4. Custom drawing only when none of the above can match the required metaphor.

Bundled Lucide-derived assets:

| Purpose | Asset | Notes |
|---|---|---|
| Home tab | [house.svg](../assets/icons/house.svg) | Use for `首页` tab or home action |
| Batch/correction tab | [file-check.svg](../assets/icons/file-check.svg) | Use for `批改` tab or report completion action |
| Profile tab | [circle-user-round.svg](../assets/icons/circle-user-round.svg) | Use for `我的` tab |
| Back | [chevron-left.svg](../assets/icons/chevron-left.svg) | Use for native back navigation |
| Drill-in | [chevron-right.svg](../assets/icons/chevron-right.svg) | Use for list row navigation |
| Dropdown | [chevron-down.svg](../assets/icons/chevron-down.svg) | Use for month/date/filter pills |
| Search | [search.svg](../assets/icons/search.svg) | Use for search controls |
| Lock | [lock-keyhole.svg](../assets/icons/lock-keyhole.svg) | Use for generic locked states when no custom asset exists |
| Play | [play.svg](../assets/icons/play.svg) | Use inside circular play controls |
| Calendar | [calendar-days.svg](../assets/icons/calendar-days.svg) | Use for date/calendar affordances |
| Checklist | [clipboard-list.svg](../assets/icons/clipboard-list.svg) | Use for tasks, records, or pending lists |
| User | [user-round.svg](../assets/icons/user-round.svg) | Use for simple inline user markers |

Default avatar:

- Use [assets/avatars/default-parent.svg](../assets/avatars/default-parent.svg) for parent/student/customer rows when no real avatar is available.
- Default size: 40px to 48px. Keep it circular, pale cyan/blue, and calm.
- Do not draw cartoon faces, sad faces, expressive mouths, emoji, random initials, or CSS-generated profile art.

SVG normalization:

- Store selected icons locally under `assets/icons/` before referencing them.
- Prefer `viewBox="0 0 24 24"`, `fill="none"`, `stroke="currentColor"`, `stroke-width="2"`, `stroke-linecap="round"`, and `stroke-linejoin="round"` for outline icons.
- Use `currentColor` so active/inactive states can be controlled by text color tokens.
- Keep one icon family per component group. Do not mix thick Material filled icons with thin Lucide outline icons in the same tabbar/list unless the source explicitly does so.
- Do not paste remote CDN URLs in generated UI. The skill must produce local, durable assets.

## SystemStatusBar

Use for normal AI自主学习系统 app pages. This component replaces ad hoc iOS-style status bars.

- Source asset: [assets/status-light.svg](../assets/status-light.svg).
- White source asset: [assets/status-white.svg](../assets/status-white.svg).
- Asset size: 390px by 44px.
- Use the SVG directly for light app pages instead of recreating its time, cellular, Wi-Fi, or battery parts.
- Use `status-white.svg` for full cyan/blue immersive header pages such as `历史批改记录`, where the status bar is white over a teal gradient.
- Height: 44px.
- Background: transparent over the page atmosphere or white/pale page surface; do not put it in a separate card.
- Time:
  - Text: `9:41`.
  - Position: left safe-area, about x 28px on 390px canvas.
  - Color: black on light pages, white on dark camera/correction pages.
  - Size: about 15px to 17px, semibold/bold.
- Right status group:
  - Cellular bars, Wi-Fi, and outlined battery.
  - Color: black on light pages, white on dark camera/correction pages.
  - Battery is an outline rounded rectangle with a right nub; no filled yellow battery pill.
  - Keep icon baseline, stroke/fill weight, and spacing consistent with the Figma status bar.
- On 390px pages, place the SVG at native width. On 375px pages, scale it proportionally to page width rather than altering internal icon positions.
- Do not use emoji, text glyphs, copied platform screenshots, yellow battery capsules, or mixed icon families.
- Browser/webview pages may preserve their source browser chrome when visible; otherwise use this component.

## CompositionCorrectionHistoryHeader

Use for the `历史批改记录` pages shown in reference assets [reference-history-records.png](../assets/composition/reference-history-records.png) and [reference-history-empty.png](../assets/composition/reference-history-empty.png).

- Canvas: 390px by 844px CSS frame.
- Header background: full-width cyan/teal gradient from about `#2EC0DC` at the top to `#10A5C8` lower left, with a pale mint/cyan glow on the upper-right. The gradient area extends to the white sheet at y 212px.
- Status bar: use `assets/status-white.svg` at 390px by 44px. Time and icons are white.
- Navigation title row: transparent over the gradient; white back chevron at x about 22px, centered title `历史批改记录`, 18px to 20px Semibold white.
- Monthly summary copy:
  - Left block begins around x 18px, y 122px.
  - With records: `本月已完成 5 篇作文练习` then `持续保持这个节奏~`.
  - Empty: `本月还没有进行作文练习` then `快练习批改下吧~`.
  - Text is white, 18px to 20px Semibold, line-height about 30px to 34px.
- Right monthly badge: use `badge-valued.svg` for count > 0 and `badge-empty.svg` for count 0; place it around x 260px, y 94px, about 104px by 108px. Do not redraw the hexagon or laurels.

## CompositionCorrectionHistorySheet

Use below `CompositionCorrectionHistoryHeader`.

- White sheet starts at y 212px on a 390px canvas and fills to the bottom.
- Top corners: 20px radius. Bottom corners are square/off-canvas.
- Header row inside sheet:
  - `批改记录` at x 16px, y about 236px, 20px Semibold/Bold `#1F242E`.
  - Month filter pill on the right at x about 274px, y about 232px, width about 100px, height 26px, radius 13px, fill `#F5F7FC`, text `2026年4月` 15px Medium `#4D535C`, small down chevron.
- Records list starts around y 286px. Use `CompositionEssayRecordListItem` rows with dividers.
- Empty state keeps the same sheet header and month filter. Center `empty-no-content.svg` around y 444px to 500px, then `暂无批改记录` below in 16px `#8E9194`.

## HomeHeader

Use for 首页 states.

- Canvas is commonly 375px wide.
- Status bar height: 44px.
- Header row height: 44px below status bar.
- Brand logo:
  - Left aligned around x 18px.
  - About 89px wide and 31px high.
  - Preserve the source logo asset or use a close bitmap/SVG; do not replace with plain text.
- Grade selector:
  - Right aligned around x 294.5px, y 52.5px on 375px canvas.
  - Size about 66.5px by 27px.
  - Fill `#F3F5F7`, radius 8px.
  - Text `高一` about 12px Medium, `#1F242E`.
  - Small down chevron around 9px.
- Header background is white and calm; no search bar, no big greeting headline.

## HomeWelcomeGuideCard

Use for 首页-未购课 discovery state.

- Position: x 14px, y 96px on 375px canvas.
- Size: 347px by 196px.
- Radius: 18px.
- Background: soft cyan/blue radial gradient, roughly `#D9F6FC` -> `#B0EFFA` -> `#A3DDFA`.
- Main assistant icon:
  - Centered near top, about 44px.
  - Use brand AI asset or a faithful source asset.
- Greeting:
  - `你好，{学生名}同学`, about 15px, `#071D39`, centered.
  - Main welcome line: `欢迎进入领航甄选自主学习系统`, about 16px Semibold, centered.
- Value chain:
  - Three icons in glassy circles/squares around 40px to 46px.
  - Labels: `自主学习计划`、`甄选内容`、`检测和提升`.
  - Labels are 13px Regular, `#3E5A7D`.
  - Dotted/segmented connectors between icons.
- Do not add CTA buttons to this card unless source has them.

## HomePendingPlanCard

Use for 首页-已购课-有更新 or pending plan creation/update states.

- Position: x 14px, y about 104px; outer effect can extend a little beyond the card due to glow.
- Size: 347px by about 305px.
- Radius: 18px.
- Border: 1px white.
- Shadow: `0 7px 18px rgba(50,131,198,0.22)`.
- Background: blue-green radial gradient, roughly `#C7F6FF` -> `#96E5F2` -> `#77CBF7`.
- Season ribbon:
  - Top-right, about 84px by 26px.
  - White text 13px Semibold.
  - Examples: `2026-寒季`, `2026-春季`.
- Header:
  - AI icon 44px near x 30px, y 122px.
  - Text block near x 71px, y 123px.
  - Greeting 14px regular; main line 16px Demibold, `#071D39`.
  - Example main line: `开始定制你的学习计划吧`.
- Plan rows:
  - Row width about 315px, height 64px.
  - Radius 12px.
  - Border 1px white.
  - Fill is white translucent to white gradient.
  - Internal icon: glass square 36px, radius 10px, with subject icon 20px.
  - Title: 15px Medium `#071D39`, e.g. `高中物理-学习计划制定`.
  - Subtitle: 12px Regular `#78818D`, e.g. `2026年寒季｜1～2月`.
  - Right CTA: black gradient pill, about 54px by 24px, radius 14px, text `去制定`, 13px Semibold white.
  - Badge: top-right corner badge `首次` or `更新`, 12px Medium.
- Badge variants:
  - `首次`: gold gradient `#F1D79E` -> `#E1B676`, text `#674B20`.
  - `更新`: orange gradient `#FFAA41` -> `#FF811A`, white text.
- Do not convert this card to a generic task list or calendar.

## HomeSuccessPlanCard

Use for 首页-已购课-完成全部计划.

- Position: x 14px, y about 104px.
- Size: 347px by about 211px.
- Radius: 18px.
- Border: 1px white.
- Shadow: `0 9px 17.9px rgba(50,131,198,0.2)`.
- Background: same blue-green gradient family as pending card.
- Season ribbon:
  - Top-right, about 84px by 26px.
  - Example: `2026-春季`.
- Center content:
  - AI celebration illustration around 64px, centered near y 134px.
  - Title `太棒了!`: about 18px display/heavy, `#072F3A`.
  - Copy `您已完成所有学习计划的制定~`: 13px Regular, `#10424F`.
  - Primary button `去学习`: black pill, about 88px by 32px, radius 48px, 15px Semibold white.
- Keep celebratory sparkles subtle and inside the card.

## CourseProductGrid

Use for 首页 `热门推荐`.

- Section title:
  - `热门推荐`, 20px Semibold, `#1F242E`.
  - x about 13.5px.
  - y depends on top state: about 323px for welcome card, 438px for pending card, 347px for success card.
- Grid:
  - Two columns.
  - Left x about 13.5px, right x about 191.5px.
  - Card cover width 169px, height 110px.
  - Horizontal gap about 9px.
  - Vertical product pitch about 220px.
- Product cover:
  - Radius 7px.
  - Must use real course cover art or a credible subject-specific cover.
  - Do not replace with flat placeholder rectangles.
  - Covers use subject-tinted gradients and teacher imagery.
- Product text:
  - Title block below cover, width 169px.
  - 15px Medium `#292929`.
  - Line-height about 19.89px.
  - Clamp/truncate like the source; do not let text collide with price or badge.
- Price:
  - Red `#FF0000`.
  - Yuan symbol about 16px, number about 20px MiSans Medium.
- Buy badge:
  - Orange/red circular `抢` badge, about 30px.
  - White bold text around 19px.
  - Sits near the price row on the right side of each product.

## TopChannelTabs

Use for APP learning section pages.

- Container lives in the top atmosphere, not inside a white card.
- Active label:
  - Text around 19px, display/heavy or Semibold.
  - Gradient text from black to `#1251A9` when supported.
  - Tracking about 1px.
  - Active underline is a thick cyan rounded capsule, about 53px by 8px, radius 4px.
- Inactive label:
  - 17px Regular, `#6F7D7F`.
  - Plain text only; no pill, card, or underline.
- Typical APP learning-plan positions on 390px canvas:
  - Active `学习计划`: x about 23px, y about 56px.
  - Inactive `全部课程`: x about 124px, y about 61px.
- Do not add search, greeting headline, task counter, or extra nav unless present in the source.

## AssistantBubble

Use for AI study reminders.

- Asset:
  - Prefer `assets/assistant-avatar.png`.
  - Source asset is 80px transparent PNG for 2x density; display at 40px by 40px.
- Avatar:
  - Place around x 12px, y 96px on the APP learning-plan page.
  - Do not replace with a text `AI` square.
- Bubble:
  - Compact one-line pill/vector bubble.
  - Starts around x 45px, y 102px.
  - Reference size is about 267.5px wide by 30px high.
  - Has a small left notch/point toward the avatar.
  - Text 14px Medium, `#071D39`, line-height 28px.
- Copy:
  - Preserve source copy exactly when optimizing from Figma or screenshot.
  - Do not append task counts, duration, or motivational copy unless source includes it.

## SubjectLegend

- Used below month title.
- Starts around x 20px, y 202px on APP learning-plan page.
- Items use 4px square dots and 12px text.
- Order for daily plan: `语文`、`数学`、`物理`、`化学`、`生物`.
- Subject colors:
  - 语文: `#FF3333`
  - 数学: `#338BFF`
  - 物理: `#22C6DF`
  - 化学: `#AE51FA`
  - 生物: `#21CC75`
- Do not omit a subject, reorder the legend, or use large circular dots when the reference uses squares.

## CollapsedWeekCalendar

Use for daily learning-plan pages.

- The collapsed calendar lives directly on the pale content sheet, not inside a separate white card.
- Weekday row:
  - y about 234px.
  - Width about 350px.
  - Seven equal columns.
  - 14px Medium `#737C82`.
  - For the APP learning-plan reference, order is `周一` to `周日`.
- Date row:
  - Starts around y 262px.
  - Cell height 54px.
  - Cell width about 43px to 44px.
  - Gap 6px.
  - Radius 8px.
  - Default fill `#EBEEF1`.
  - Date number uses Space Grotesk/Inter Bold, 16px.
- Planned day:
  - Same gray cell as default.
  - 4px subject dot or multiple 4px dots below number.
- Selected day:
  - Same 54px height and 8px radius.
  - Black-to-`#383838` gradient.
  - White date number.
  - Subject dot remains visible underneath.
  - Soft shadow: `0 10px 15px -3px rgba(0,102,134,0.2), 0 4px 6px -4px rgba(0,102,134,0.2)`.
- Failure cases:
  - Wrapping the whole week in a white rounded calendar card.
  - Using Sunday-first order when the reference is Monday-first.
  - Stretching date cells into large cards.
  - Removing subject dots or using random colors.

## CourseTaskCard

Use for daily learning-plan unfinished course cards.

- Size:
  - Width about 362px.
  - Height about 124px.
  - Radius 12px.
  - Fill white.
  - Border `rgba(188,200,208,0.2)`.
  - Shadow `0 1px 1px rgba(0,0,0,0.05)`.
  - Vertical gap between cards: 10px.
- Layout:
  - Top metadata row at about 20px from card top.
  - Lower row starts around 53px from card top.
  - Left content column about 268px.
  - Right action column reserves 32px to 40px.
- Metadata row:
  - Subject tag then knowledge point text.
  - Subject tag example `数学`: about 37px wide, 21px high, fill `#D1E5FF`, radius 4px, text `#2361B2`, 13px Medium.
  - Knowledge text: 14px Regular, `#77838B`.
- Title:
  - 16px Medium, black.
  - Preserve exact source title.
  - Must stay inside card width and wrap only if necessary.
- Progress row:
  - About 8px below title.
  - Star asset or five compact star glyphs, about 66px by 15px.
  - Progress time 14px, `#77838B`, e.g. `12:30/37:01`.
  - Do not replace with explanatory text like `难度 3 星`.
- Right play button:
  - 32px circle.
  - Pale gray-blue circular fill.
  - Small dark play triangle centered.
  - Do not use a black circular play button on this card.
- Forbidden:
  - Time-slot schedule row like `11:00-11:25`.
  - Status badges like `学习中` or `未开始`.
  - `今日任务` or progress header inserted above the cards when not in the source.

## BottomTabbar

- Fixed to bottom.
- Height includes 54px content area plus 34px iPhone home area.
- Fill `rgba(255,255,255,0.88)` with blur.
- Top border `rgba(0,0,0,0.08)`.
- Uses exactly three items: `首页`、`学习`、`我的`.
- Active item uses orange `#FF6200`; on home pages active item is `首页`, on learning pages active item is `学习`.
- Inactive text color `#7C88B4`.
- Icons are product assets or close SVG/CSS reproductions, not emoji.

## CompositionReportListCard

Use for `批改统计`, 作文批改历史, report-list, and batch-correction management cards.

- Source screenshots may define card order and copy, but not palette. Recolor to cyan/blue tokens.
- Card fill: white, radius 16px to 18px, subtle cool shadow, width about 362px on a 390px canvas.
- Primary row:
  - Avatar is 40px to 44px, left aligned.
  - User name uses 16px to 18px Semibold, `#071D39`.
  - Phone number uses 13px to 15px, `#78818D`.
  - `查看报告` action sits in this first-level row on available report cards; it must not be buried below the detail panel.
- Detail panel:
  - Contains `作文标题` and `提交时间` rows.
  - Sits below the primary row.
  - Uses pale blue border `#CCE9FB` or `rgba(0,167,216,0.18)`, not peach/orange.
- Result row:
  - Score pill such as `42分` uses cyan/blue fill `#00A7D8` or the blue action gradient, with white text.
  - Category/dang tag such as `3档` uses pale blue fill `#F0F6FD` or `#CCE9FB`, blue/primary text.
  - The row sits below the detail panel with compact spacing.
- Required content per completed report card: avatar, user name, phone, `查看报告`, `作文标题`, `提交时间`, score, category/dang.
- Do not use orange score pills, beige category pills, peach borders, brown labels, or orange report actions unless the exact target Figma node explicitly contains those tokens.
- If card icons or empty-state illustrations are extracted from a warm source, recolor decorative warm fills/strokes to cyan/blue tokens while preserving their geometry.
- If no real user avatar is provided, use [assets/avatars/default-parent.svg](../assets/avatars/default-parent.svg) at 40px to 48px. Do not generate a new face, emoji, initials badge, or ad hoc CSS avatar.
- Use local mature-library icons for row actions: [chevron-right.svg](../assets/icons/chevron-right.svg) for drill-in, [file-check.svg](../assets/icons/file-check.svg) for report/completed actions, and [circle-user-round.svg](../assets/icons/circle-user-round.svg) only for profile/tab contexts.
- Do not enlarge names or phone numbers into display-scale text; this is a dense management list, not a profile card.

## CompositionRankAssets

Use these bundled assets when a page shows作文档次, score category, unlock state, medal state, or a no-content fallback. These assets are the visual source of truth for the Figma nodes around `4424:491` and `5201:3715`.

| Asset | File | Size | Use |
|---|---|---:|---|
| Valued medal | [badge-valued.svg](../assets/composition/badge-valued.svg) | 104x108 | Single-data card when score/rank has a value |
| Empty medal | [badge-empty.svg](../assets/composition/badge-empty.svg) | 104x108 | Single-data card when score/rank has no value |
| No-content fallback | [empty-no-content.svg](../assets/composition/empty-no-content.svg) | 132x74 | Empty list/data area |
| Locked tag | [tag-locked.svg](../assets/composition/tag-locked.svg) | 40x44 | Locked score/category state |
| 一类 tag | [tag-rank-1.svg](../assets/composition/tag-rank-1.svg) | 40x18 | Rank/category label |
| 二类 tag | [tag-rank-2.svg](../assets/composition/tag-rank-2.svg) | 40x18 | Rank/category label |
| 三类 tag | [tag-rank-3.svg](../assets/composition/tag-rank-3.svg) | 40x18 | Rank/category label |
| 四类 tag | [tag-rank-4.svg](../assets/composition/tag-rank-4.svg) | 40x18 | Rank/category label |
| 五类 tag | [tag-rank-5.svg](../assets/composition/tag-rank-5.svg) | 40x18 | Rank/category label |

Rank tag rules:

- Use the SVG asset directly at native size or proportional size. Default rank tag size is 40px by 18px with 9px radius.
- Do not recreate `一类` to `五类` as plain text pills. Their gradients, text treatment, and compact capsule shape are part of the target style.
- `待解锁` uses the 40px by 44px locked asset, not a generic lock icon plus text.
- Warm gold/cream inside rank assets is allowed because these assets are explicit target components. Do not reuse those warm colors elsewhere.
- If the page has no rank value, use the empty medal/no-value asset and preserve the no-content illustration where appropriate.

## CompositionSingleDataImmersiveCard

Use when the source or product requirement is a single作文数据展示页, score/rank snapshot, category summary, monthly rank result, or any page dominated by one primary metric plus a medal/badge.

Layout:

- Canvas: 390px mobile page with `SystemStatusBar` and a cool cyan/blue background atmosphere.
- Main card: immersive rounded card, usually 16px to 20px radius, white or pale cyan-white gradient, cool soft shadow, horizontal content.
- Card interior: left side is title/data copy; right side is a medal/badge asset.
- Left column: title uses 15px to 17px Semibold, primary text `#071D39`; secondary explanatory text uses 12px to 14px gray-blue. The primary number/score can use 28px to 36px bold numeric type when it is the main data point.
- Right column: use `badge-valued.svg` for valued state, `badge-empty.svg` for no-value state, or a rank/locked asset when the page's primary state is category/locked.
- Spacing: card horizontal padding about 16px to 20px; vertical padding about 18px to 22px; left/right gap about 12px to 18px. The badge should align visually to the vertical center of the card and must not overlap text.
- Typography: compact mobile hierarchy; avoid oversized hero text. Chinese labels stay 12px to 17px, metric numbers can be larger but must remain inside the card.
- Empty state: use `empty-no-content.svg` centered in the content area with muted gray-blue copy below if the source includes empty copy.

Do not:

- Put the medal below the text when the source is a single data card with left-title/right-medal structure.
- Replace the medal/rank assets with emoji, CSS gradients, generic trophies, or hand-drawn badges.
- Sample source screenshot orange/brown colors for the card background. The page background and card surfaces stay in the cyan/blue system.

## CompositionEssayRecordListItem

Use when the source or requirement is a作文列表, history list, report record list, or any repeated essay item with score/category plus title/time.

Layout:

- In `历史批改记录`, list rows are not separate cards. They sit on the white sheet with bottom dividers `#F1F1F1`, width about 358px, x 16px, and about 86px row height.
- Internal grid: two columns. Left column is fixed around 52px to 58px for score and rank; right column fills remaining width with title and time; a chevron sits at the far right.
- Left column: score such as `52分` is the primary visual. Use about 20px MiSans/PingFang Semibold black `#191C1E`; the `分` glyph is smaller, about 12px to 13px. Place the rank SVG below with about 4px to 6px gap.
- Right column:作文标题 uses about 17px Semibold black `#030409`; subtitle/time uses about 13px to 14px `#77838B`. Keep exact source strings such as `批改时间：4月11日 14:55` and `你的作文分析报告待领取`.
- Locked state: left column uses `tag-locked.svg` or an explicit locked asset state; do not show fake scores.
- Empty list: use `empty-no-content.svg`, not a generic blank illustration.

Do not:

- Use the user/avatar/phone/report-action hierarchy from `CompositionReportListCard` for this structure.
- Move score/rank to the right side. For作文列表, score and rank stay on the left; title and time stay on the right.
- Rebuild rank tags as CSS text pills.

## PrimaryActionButton

- Main black action:
  - Black to `#252525` or `#383838` gradient.
  - Radius 8px to 12px for rectangular buttons; 28px to 30px for large pills.
  - Text white, 15px to 17px Medium/Semibold.
- Some commerce/challenge pages use blue gradient CTA instead of black.
  - Match the skill's target page color family before applying the generic black button. Do not inherit warm CTA colors from arbitrary source screenshots.

## TagsAndBadges

- Small subject tags use one fill and no doubled border.
- Height usually 18px to 24px.
- Radius 4px to 8px.
- Text must be vertically centered.
- Stage/outline tags need `box-sizing: border-box` and a single clean stroke.

## GradientAdviceCard

- Use for plan creation advice, recommendation banners, and challenge intro modules.
- Preserve gradient direction, light border, radius, and decorative icon.
- Do not flatten into a plain pale rectangle.
- Text must have enough padding and line-height; it cannot touch borders or overlap the decorative icon.

## IconFallbacks

- Structural icons are content, not optional decoration.
- First use source/Figma icons, bundled `assets/icons/`, or a mature open-source library SVG copied locally. Only draw inline SVG/CSS fallback when no appropriate asset exists for:
  - back chevron
  - dropdown caret
  - play
  - lock
  - expand/collapse
  - status battery/wifi/cell
  - tabbar icons
- For parent/student/customer default avatars, use `assets/avatars/default-parent.svg`; do not draw a custom face fallback.
- Keep stroke caps/joins rounded where the reference uses rounded icons.
- Keep one stroke style within the same screen.
