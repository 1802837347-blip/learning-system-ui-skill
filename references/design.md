# AI自主学习系统 Design Guidelines

## Design Sources

- Figma: [学习计划入口](https://www.figma.com/design/RbXpJaiNDZs1jwLQCWznDT/AI%E8%87%AA%E4%B8%BB%E5%AD%A6%E4%B9%A0%E7%B3%BB%E7%BB%9F?node-id=581-3019&t=lP0XhkmnxVv0D0nA-0)
- Figma: [作文批改流程](https://www.figma.com/design/RbXpJaiNDZs1jwLQCWznDT/AI%E8%87%AA%E4%B8%BB%E5%AD%A6%E4%B9%A0%E7%B3%BB%E7%BB%9F?node-id=4283-6137&p=f&t=lP0XhkmnxVv0D0nA-0)
- UI Skill: [learning-system-ui-skill](https://github.com/1802837347-blip/learning-system-ui-skill/tree/main)

This document covers:

- `学习计划专项 / 1.入口`
- `学习计划专项 / 2.制定计划流程`
- `学习计划专项 / 3.学习计划日历与全部课程`
- `作文批改 / 作文批改`
- `作文批改 / 分数档次与列表` using Figma nodes `4424:491` and `5201:3715`

## AI Agent Compliance Protocol

Agents must treat this file as an implementation contract, not inspiration. Before writing UI code, the agent must identify the target page family and extract only the relevant page section plus `Core Tokens`, `Global Components`, `Implementation Guardrails`, and `QA Checklist`.

Required agent behavior:

1. State the target page family and the exact sections read.
2. List hard constraints before implementation, including page width, required order, required copy, forbidden additions, and key dimensions.
3. Do not invent brand names, subtitles, extra navigation, hero copy, feature explanations, decorative logos, cartoon avatars, or promotional components not listed in the target page section.
4. Preserve required Chinese copy exactly where this document gives exact copy.
5. Use exact dimensions when this document says `must`, `exact`, or gives a single value.
6. If a required real image asset is unavailable, use a neutral placeholder with the same size and layout, and label it as an asset placeholder in code comments only. Do not replace it with a different brand, mascot, cartoon person, or unrelated illustration.
7. Treat source illustrations, icons, tabbar icons, course covers, photos, and report previews as locked visual assets when optimizing an existing screenshot or Figma node. If no bundled asset or clearly better product asset exists, crop, extract, or faithfully trace the source asset and place it back into the optimized UI instead of drawing a simplified replacement from scratch.
8. Use the AI自主学习系统 status bar component for normal light app pages by placing [assets/status-light.svg](../assets/status-light.svg) at the top of the canvas. Do not substitute generic iOS status bars, yellow battery pills, or mismatched signal/Wi-Fi/battery drawings.
9. Do not inherit colors from arbitrary reference screenshots. Source screenshots provide layout, information, and extractable assets only. UI colors must come from this document's tokens and stay cyan/blue-dominant unless this document explicitly assigns a warm token to that exact component.
10. For source illustrations/icons, preserve geometry/detail but remap non-content warm fills/strokes to cyan/blue tokens when they conflict with the target system. Preserve natural colors only for real content media such as photos, course covers,作文 manuscript images, report previews, and other evidence-like assets.
11. After implementation, run the QA checklist and explicitly fix all failed items before final output.

For tests, a result should be considered failed if it uses an unlisted brand name, adds a subtitle not present in the source page, changes the required page order, replaces real course covers with generic cartoon cards, redraws source illustrations/icons into lower-fidelity substitutes, uses a non-system status bar on normal app pages, inherits orange/brown/warm source colors into a cyan/blue target page, or hides any bottom content behind the tabbar.

## Product Character

The interface is a mobile-first learning mini-program for high-school students. It should feel calm, precise, trustworthy, and study-focused. The first viewport should always show useful learning content or the current task state, not a marketing landing page.

Use a pale cool system background, blue-cyan atmosphere, soft gradient cards, white content cards, compact status tags, and direct action copy. Visual polish comes from containment, spacing, state clarity, and subject-specific color, not from decorative density.

## Color Source Policy

- This design system is color-authoritative. When optimizing from an arbitrary screenshot, never use the screenshot's palette as input for UI colors.
- Preserve screenshot content, layout hierarchy, component count, and extractable image/icon assets, but remap all UI colors to AI自主学习系统 tokens.
- For decorative/source UI illustrations and icons, extract the original shapes/details first, then recolor any warm non-content fills/strokes into the cyan/blue token family. Do not keep orange/peach/brown illustration colors just because they appear in the source screenshot.
- Default target palette is cyan/blue dominant: pale cyan top atmosphere, white cards, blue/cyan selected states, blue gradient primary tabs/CTAs, blue outlined secondary actions, and gray-blue muted text.
- Forbidden source-color leakage: orange, brown, beige, peach, amber, warm cream, and warm gradients copied from a reference screenshot into cards, borders, score pills, category pills, or CTAs.
- Warm tokens in this file are exceptions, not defaults. Use them only for the specific components that explicitly require them, such as existing commerce/update badges, course price/sale badges, or APP bottom-tab active orange where that page pattern says so.
- For作文批改 statistics, history, report-list, and batch-correction management pages, score pills, category tags, segmented controls, report buttons, and card detail borders should use the cyan/blue token family unless the exact target Figma node says otherwise.
- If a source UI uses orange to indicate a score or action, map it to a skill token such as `#00639E`, `#00A7D8`, `#0EC5FF`, `#CCE9FB`, or the stepper/action blue gradient instead of preserving the warm color.
- Exception: bundled composition rank assets (`tag-rank-1.svg` through `tag-rank-5.svg`, `tag-locked.svg`, `badge-valued.svg`, `badge-empty.svg`) preserve their own target colors. Do not reuse those warm/gold rank colors for surrounding UI.

## Screen Model

- Primary canvas widths: `375px` for older home/recommendation pages, `390px` for newer APP learning-plan, plan-creation, and composition flows.
- Use safe-area padding for iPhone status/home areas.
- Keep fixed bottom tabbars or action bars from covering scroll content.
- Prefer flex/grid layout, content-driven spacing, and `min-height` over tight fixed heights.
- Use absolute positioning only for camera overlays, decorative glows, fixed bars, and intentionally layered media.

## Core Tokens

### Color

| Role | Value |
|---|---|
| Page background | `#F0F2FA`, `#ECEEF5`, `#F7F8F9` |
| White card | `#FFFFFF` |
| Glass card | `rgba(255,255,255,0.7)` |
| Input fill | `#F1F4F7` |
| Main text | `#030409`, `#071D39`, `#191C1E` |
| Secondary text | `#78818D`, `#828B94`, `#77838B` |
| Muted text | `#A9B1B8`, `#8E9194` |
| Subject blue | `#00639E` |
| Active tab orange | `#FF6200` |
| Cyan underline | `#47EFF9` |
| Dark action gradient | `#000000` to `#383838` |
| Stepper active gradient | `#00B3E8` to `#0288FF` |
| Completed green | `#15C691` |
| Validation red | `#E70000` |
| Course price red | `#FF0000` |
| Gold badge gradient | `#F1D79E` to `#E1B676` |
| Update badge gradient | `#FFAA41` to `#FF811A` |
| Modal overlay | `rgba(38,38,38,0.5)` |

### Subject Colors

| Subject | Color |
|---|---|
| 语文 | `#FF3333` |
| 数学 | `#338BFF` |
| 物理 | `#22C6DF` |
| 化学 | `#AE51FA` |
| 生物 | `#21CC75` |

Carry these colors through calendar dots, subject tags, legends, and knowledge/course states.

### Typography

- Primary Chinese font: `PingFang SC`.
- Numeric/supporting font: `MiSans`.
- Calendar numbers: `Space Grotesk`, `Inter`, or closest available bold numeric font.
- Display/title fallback: `PingFang SC Semibold/Heavy`.
- Do not use negative letter spacing.
- Do not use viewport-scaled font sizes.
- Do not bundle custom font files unless licensing is confirmed.

### Radius And Shadow

| Element | Radius / Shadow |
|---|---|
| Main gradient card | `16px` to `18px` |
| List card | `12px` |
| Input / selector | `8px` to `10px` |
| Small tag | `4px` to `8px` |
| Capsule button | `14px` to `15px` |
| Main blue card shadow | `0 9px 18px rgba(50,131,198,0.22)` |
| Plan creation card shadow | `0 4px 24px rgba(50,131,198,0.16)` |
| Course task card shadow | `0 1px 1px rgba(0,0,0,0.05)` |

## Global Components

### Asset Fidelity

- Preserve source visual assets before improving them. Original screenshots and Figma nodes can contain product-specific illustration systems, tabbar icons, course covers, decorative module icons, and expand/play/status icons that are part of the UI language.
- Asset replacement priority: source-cropped/extracted bitmap asset, existing bundled product asset, mature open-source icon library asset copied locally, faithful traced SVG/vector, then a neutral placeholder only when the source asset is absent or unusable.
- Do not hand-draw a new simplified icon or illustration when the source already provides one and the replacement is not clearly better. Low-fidelity redraws, mismatched stroke styles, generic cartoons, emoji, or unrelated icon families fail the design contract.
- When extracting from a screenshot, keep the source asset's proportions, opacity, geometry, and visual weight. Clean cropping or light retouching is allowed; changing the asset's style family is not. For decorative UI icons/illustrations, recolor conflicting warm fills/strokes into cyan/blue tokens while preserving detail.

### Icon Library Assets

Structural icons are product infrastructure. Do not improvise them from rough CSS or hand-drawn paths when a mature library match exists.

Use this order:

1. Source/Figma icon or product asset when visible and usable.
2. Bundled local icon/avatar asset.
3. Mature open-source icon library asset copied into this skill: Lucide first, then Tabler, Heroicons, Phosphor, MingCute, Iconoir, or Material Symbols.
4. Custom drawing only when none of the above matches the needed metaphor.

Bundled local assets:

- `assets/icons/house.svg`: home tab or home action.
- `assets/icons/file-check.svg`: `批改`/report/check tab.
- `assets/icons/circle-user-round.svg`: `我的`/profile tab.
- `assets/icons/chevron-left.svg`: back navigation.
- `assets/icons/chevron-right.svg`: row drill-in navigation.
- `assets/icons/chevron-down.svg`: dropdown/date/month controls.
- `assets/icons/search.svg`: search controls.
- `assets/icons/lock-keyhole.svg`: locked state when no custom rank asset is required.
- `assets/icons/play.svg`: circular play controls.
- `assets/icons/calendar-days.svg`: calendar/date affordances.
- `assets/icons/clipboard-list.svg`: task/report/pending list affordances.
- `assets/icons/user-round.svg`: compact inline user markers.
- `assets/avatars/default-parent.svg`: default parent/student/customer avatar for list rows without real photos.

SVG icon contract:

- Prefer `viewBox="0 0 24 24"`, `fill="none"`, `stroke="currentColor"`, `stroke-width="2"`, and rounded caps/joins for outline icons.
- Use one icon family per component group. Bottom tabbar icons must share weight, size, baseline, and active/inactive color behavior.
- Default avatars should be 40px to 48px, circular, calm cyan/blue, and asset-based. Do not draw expressive faces, emoji, random initials, or CSS-generated profile art.

### Composition Rank Assets

Use the bundled assets for作文 score/rank pages:

- `assets/composition/badge-valued.svg`: 104px by 108px valued medal.
- `assets/composition/badge-empty.svg`: 104px by 108px no-value medal.
- `assets/composition/empty-no-content.svg`: 132px by 74px no-content fallback.
- `assets/composition/tag-locked.svg`: 40px by 44px `待解锁`.
- `assets/composition/tag-rank-1.svg` to `tag-rank-5.svg`: 40px by 18px `一类` to `五类`.
- `assets/composition/reference-history-records.png` and `assets/composition/reference-history-empty.png`: visual references for `历史批改记录` records and empty states.

Rank tag visual contract:

- `一类`: 40px x 18px, 9px radius, dark charcoal gradient `#44454F -> #2A2B32`, gold gradient text `#FFD9AB -> #FFCBA5`.
- `二类`: 40px x 18px, 9px radius, gold gradient `#FFD887 -> #ECC26C`, dark brown text `#4C2900`.
- `三类`: 40px x 18px, 9px radius, warm beige gradient `#F0E3D3 -> #DCCAB6`, dark brown text `#4C2900`.
- `四类`: 40px x 18px, 9px radius, pale cyan gradient `#D4F1F5 -> #A3CED4`, teal text `#1D444A`.
- `五类`: 40px x 18px, 9px radius, blue-gray gradient `#DAE2F0 -> #A3B6D8`, navy text `#1F3865`.
- `待解锁`: 40px x 44px full asset, with 20px lock icon at top and 40px x 18px label capsule at y 26px. Do not split the lock and label into separate ad hoc components.

Do not redraw these assets or replace them with CSS pills. Their exact gradient, compact shape, and text treatment are part of the page style extracted from the target Figma nodes.

### Composition Score And List Layout

- Single data display pages use an immersive card: left side contains the title, metric, and supporting copy; right side contains the medal/rank asset.
- The card uses a cool white or pale cyan-white surface, 16px to 20px radius, soft cool shadow, 16px to 20px horizontal padding, and 12px to 18px gap between text and medal.
- Typography is compact: labels 12px to 14px, titles 15px to 17px Semibold, metric numbers 28px to 36px bold when they are the primary data.
- `历史批改记录` uses a full cyan/teal header and white rounded-top sheet, not a normal card stack.
- 作文列表 uses a two-column list item: left column is score plus rank tag; right column is title plus time.
- List item title uses 14px to 16px Semibold, time uses 12px to 13px gray-blue, score uses 22px to 28px bold numeric style.
- Preserve source title/time/score/category copy exactly. Do not swap left and right columns.

### Composition History Records Page

Use this exact page family when the source or product requirement resembles Figma `4424:491` or `5201:3715`: `历史批改记录`, monthly作文 history, scored essay records, empty monthly history, or locked report rows.

- Canvas: 390px x 844px.
- Page background: vertical gradient `#28BEE3` at top to `#129CC6` around 32%, then white sheet covers the lower page.
- Top status/navigation: use `assets/status-white.svg` at x 0, y 0, 390px x 44px. Title bar occupies y 46px to y 94px. Back chevron is white, about 25px, x 14.5px. Center title is `历史批改记录`, 17px Medium white.
- Header summary block: starts around x 18px, y 121px, width about 213px. First line is 19px MiSans Demibold white with 22px line height. Second line is 17px MiSans Demibold white with 22px line height and 6px vertical gap.
- Header copy:
  - Records state: `本月已完成 5 篇作文练习` and `持续保持这个节奏～`.
  - Empty state: `本月还没有进行作文练习` and `快练习批改下吧～`.
- Monthly medal: use `badge-valued.svg` when the count is greater than 0 and `badge-empty.svg` when the count is 0. Medal visual area sits in the upper-right, with the count number around 44px Space Grotesk Bold and `本月批改` label 11px.
- Content sheet: white, x 0, y 212px, width 390px, min-height to bottom, top-left/top-right radius 20px.
- Sheet header: `批改记录` at x 16px, y about 232px, 18px Semibold `#1F242E`, line-height 26px. Month pill at x about 275px, y about 232px, fill `#F5F7FC`, radius 32px, padding 8px x 4px, text 13px Medium `#4D535C`, 16px down chevron.
- Records list: x 16px, y 266px, width 358px. Rows are not independent cards; they are plain list rows on the sheet with 20px vertical padding and a 1px bottom divider `#F1F1F1`.
- Record row layout: content width 330px plus 20px right chevron. Left score/rank block width about 40px to 52px, then 14px gap, then flexible title/time block.
- Score row: score number 18px MiSans Demibold `#191919`, suffix `分` 12px PingFang Medium black, score and suffix baseline-aligned. Rank asset sits 2px below score.
- Title/time block: title 16px PingFang Medium black; subtitle 13px PingFang Regular `#77838B`; vertical gap 6px.
- Example record content to preserve when present: `52分` `一类` `突破锁链，找寻自我` `批改时间：4月11日 14:55`; `44分` `二类` `在变化中守住不变`; `32分` `三类` `快与慢之间，见人生分寸` `你的作文分析报告待领取`.
- Locked row: replace score/rank with `tag-locked.svg`, then keep title 16px black and subtitle `完成讲解即可解锁完整批改报告`; keep the far-right chevron.
- Empty state: keep the same header, white sheet, `批改记录` title, and month pill. Place `empty-no-content.svg` centered around x 129px, y 441px, 132px x 74px, opacity 80%; text `暂无批改记录` centered around y 535px, 16px `#8E9194`.

### System Status Bar

- Use this status bar on normal AI自主学习系统 app pages, including home, learning-plan, all-courses, plan creation, knowledge-point, report, history, auth, and modal states.
- Light status bar asset: [assets/status-light.svg](../assets/status-light.svg). This 390px by 44px SVG is the source of truth for the normal app status bar.
- White status bar asset: [assets/status-white.svg](../assets/status-white.svg). Use this for full cyan/blue immersive header pages such as `历史批改记录`.
- Place the SVG at the top of the canvas at full width on 390px pages. On 375px pages, scale proportionally to 375px width and preserve its 44px vertical area relationship.
- It sits at the top safe area and overlays or precedes the page's pale cyan atmosphere. It should not be placed inside a card.
- The SVG already includes `9:41`, black cellular bars, black Wi-Fi, and black battery. Do not redraw or restyle those sub-icons when the asset is available.
- Do not use yellow battery pills, emoji/text glyphs, platform-default pasted icons, mixed stroke weights, or a different time unless the source explicitly locks another time.
- Dark camera/correction screens may use the same geometry in white. Browser/webview challenge pages may preserve their shown browser chrome, but ordinary app pages should still use this system status bar.

### Bottom Tabbar

- Fixed bottom area with `rgba(255,255,255,0.88)`, top border `rgba(0,0,0,0.08)`, plus 34px iPhone home area.
- Common tabs: `首页`, `学习`, `我的`.
- Icon size about `27px`; label size `11px`.
- Active tab uses `#FF6200`; inactive tab uses `#7C88B4`.
- On daily plan and all-courses pages, `学习` remains the active bottom tab.

### Buttons

- Primary page actions use black/dark gradient with white text.
- Disabled primary actions keep the same gradient and dimensions but reduce opacity, commonly to `50%` or `40%`.
- Compact row actions use rounded capsules, not large rectangular blocks.
- Right-side CTAs must reserve layout width and stay inside the parent card padding.

### Badges And Tags

- `首次`: gold gradient, text `#674B20`.
- `更新`: orange gradient, white text.
- `已学习`: blue border/text, compact outlined tag.
- Tags use one fill/border strategy. Avoid double outlines, clipped strokes, or pseudo-element borders unless visually verified.

### Cards

- Cards must fully contain titles, metrics, tags, icons, and buttons.
- Use `box-sizing: border-box`.
- Use `min-height` when real content can wrap.
- Do not hide required text with `overflow: hidden`; reserve enough space instead.
- White list cards usually use 12px radius; main blue cards use 16-18px radius.

## 学习计划专项

### 1.入口

Use this page when the user enters the learning system and needs to see pending study-plan setup, AI learning tools, and course recommendations.

Hard acceptance criteria for this page:

- Page family: `375px` mobile recommendation/home page.
- Required page order is fixed: status/header, plan setup card, `热门推荐`, bottom tabbar. Include `AI学习工具` only if explicitly requested.
- Header must not introduce a new product title/subtitle. Do not use names such as `名师领学堂`, `AI自主学习系统`, or any invented brand line in visible UI.
- If the real logo asset is unavailable, render a simple wordmark text `领航伴学` in the logo slot. Do not create a square app icon beside a title.
- The grade selector copy is `高一`.
- The plan setup card must contain exactly three rows in this default entry state: `高中物理-学习计划制定`, `高中数学-学习计划制定`, `高中化学-学习计划制定`.
- Default entry state badges are `首次`. Use `更新` only when the prompt explicitly asks for update state.
- Course recommendation covers must use real provided cover images when available. If no cover assets are available, render same-size subject cover placeholders without cartoon faces or invented teacher portraits.
- The bottom tabbar must not cover the first row of course prices or the `抢` buttons.

Page order:

1. Brand/header row or greeting row.
2. Gradient plan setup or pending card.
3. Optional `AI学习工具`.
4. Optional history/plan section.
5. `热门推荐` course grid.
6. Bottom tabbar.

Header:

- On 375px recommendation pages, use a white top header with logo at left, about `89px x 31px`.
- Grade selector is a compact pill, about `66px x 27px`, fill `#F3F5F7`, radius `8px`, text 12px Medium.
- Do not add search bars or heavy navigation to this header.
- Do not add a visible subtitle under the logo.
- Do not add a separate square app icon unless it exists in the source design for the target page.

Plan setup card:

- Width must be about `347px`, height about `305px`, radius `18px`.
- Blue-green gradient background with white border and soft blue shadow.
- Top-right season ribbon: `2026-寒季`, about `84px x 26px`.
- Header includes a 44px AI icon and copy:
  - `你好，{学生名}同学`
  - `开始定制你的学习计划吧`
- Task rows:
  - Width about `315px`, height about `64px`, radius `12px`.
  - Left 36px glass subject icon.
  - Title pattern: `高中{学科}-学习计划制定`.
  - Subtitle pattern: `2026年寒季｜1～2月` or `2026年春季｜3～6月`.
  - Gold `首次` or orange `更新` badge at row top-right.
  - CTA: dark capsule `去制定`.

AI learning tools:

- Section title: `AI学习工具`, 20px Semibold, aligned to page margin.
- Composition monthly report card width about `358px`, height about `270px`, radius `20px`.
- Entry card title: `高考语文作文批改`.
- Entry copy: `随学随练，有效提升，拍照上传后即可生成批改结果。`
- CTA: `拍照批改`.
- Quota ribbon: `可用 2/10`.

Course recommendations:

- Section title: `热门推荐`, 20px Semibold.
- Use two-column course grid.
- Course cover card is about `169px x 110px`, radius `7px`.
- Product/teacher imagery must remain inspectable when assets are available.
- If assets are unavailable in a no-image test, use flat subject cover placeholders that preserve source cover proportions, subject title placement, and soft subject colors. Do not use cartoon headshots, fake teacher portraits, or unrelated illustrations.
- Course title pattern: `名师-高一{学科}` and `(25H2+26H1全年）...`.
- Price: `￥799`, red.
- Sale action can use a small orange `抢` circle.

### 2.制定计划流程

Use this flow after tapping `去制定`.

Page order:

1. Status bar and mini-program title bar.
2. Three-step progress stepper.
3. `伴学规划建议` card.
4. Step-specific form or selector.
5. Date picker or knowledge-point bottom sheet when needed.
6. Generation loading state.
7. Generated plan overview and APP handoff.

Title bar:

- Canvas usually `390px`.
- Title bar height about `48px` below status bar.
- Center title: `{年级}{学科}-{季节}自主计划` or `{年级}{学科}-{季节}计划`.
- Left: 24px back arrow.
- Right: mini-program capsule, 28px high, rounded.

Progress stepper:

- Steps: `学习信息`, `计划考点`, `生成计划`.
- Place around y `92px`, full width with 24px side padding.
- Active step uses 22px gradient circle and label `#008EBA`.
- Inactive step uses translucent blue-gray circle and muted label.
- Completed step uses green circle with check.
- Keep the stepper directly on the page; do not wrap it in a card.

Planning advice card:

- Width about `362px`, height about `217px` in step 1.
- Radius `14px`, white border, blue shadow, blue gradient background.
- Title: `伴学规划建议`.
- Context: `{季节}学季 · 在读 {n} 科`.
- Body explains the next two steps with short bullet lines.
- Recommendation panel uses translucent white block with recommended hours.

Learning information form:

- Starts below the advice card, usually x `14px`, width `362px`.
- Use 24px spacing between major groups and 12px between label/control.
- Score inputs:
  - Two `168px x 52px` inputs with `/` between them.
  - Placeholder `请输入`; full score may show `150`.
- Target score:
  - Single `362px x 52px` input.
- Frequency chips:
  - Options: `每周`, `每双周`, `每三周`, `每四周`.
  - Selected: white fill, 1px `#00639E` border, blue text.
- Day/hour rows:
  - Height `64px`, fill `#F1F4F7`, radius `8px`.
  - Minus button: white circle with blue border.
  - Plus button: blue circle with white icon.
  - Number: MiSans 22px Demibold.

Period planning:

- Section label: `计划学习周期和每日课时`.
- Period card width `362px`, white fill, radius `10px`, subtle blue shadow.
- Default dates show `请选择日期`.
- Filled dates use `YYYY.MM.DD`.
- Multiple periods show `删除` in red when removable.
- Add row: `＋ 添加时间段`, bordered blue, height about `58px`.

Validation:

- Invalid controls keep pale fill plus 1px `#E70000` border.
- Helper text is 14px red directly below the field.
- Examples: `得分不能超过满分`, `目标分不能超过满分`.
- Bottom `下一步` remains visible but disabled when required fields are incomplete.

Knowledge-point step:

- Step 1 is completed green; step 2 is active.
- Advice card height can grow to about `306px`.
- Selector label: `计划学习{学科}考点（多选）`.
- Empty selector: `请选择`.
- Selected selector: `已选{n}个考点，{n}个视频`.
- Bottom action: `开始生成学习计划`.

Knowledge-point bottom sheet:

- Sheet starts near y `72px`, width `390px`, height about `739px`, background `#F3F5F7`, top radius `16px`.
- Header summary: `已选 9 个考点，30 个视频`.
- Topic/subtopic rows support expand/collapse and `全选`.
- Knowledge rows show title, difficulty stars, optional `已学习` tag, and circular check control.
- Fixed bottom action: black-gradient `确认`.
- Show `上学季未学习推荐` and `一键勾选未学习` only when previous unfinished content exists.

Generation loading:

- Background `#F0F2FA` with cyan top atmosphere.
- Center assistant/robot glow.
- Title: `正在生成学习计划`.
- Helper: `整合学习节奏与知识点分布，生成专属学习计划`.
- No bottom CTA.

Generated plan overview:

- All stepper items are green completed checks.
- Sync success card:
  - Text: `计划已同步至“领航伴学APP-学习计划”`.
  - Right CTA: `去学习`.
- Overview card includes:
  - `知识点总览`.
  - Metrics: `模块`, `专题`, `考点`, `视频`.
  - Difficulty distribution bar and legend.
- Month preview uses compact calendar cells with planned course labels and difficulty/subject colors.

### 3.学习计划日历与全部课程

Hard acceptance criteria for `学习计划-未完成`:

- Page family: `390px` APP learning-plan page, not the 375px home/recommendation page.
- Required visible order is fixed: status bar, top channel tabs, assistant bubble, month block, subject legend, collapsed week calendar, task section, bottom tabbar.
- Top channel must show `学习计划` active and `全部课程` secondary. The active underline is cyan and sits under `学习计划`.
- Assistant copy must be `{学生名}同学，请完成今天的学习计划吧`; do not rewrite it as a generic motivational sentence.
- Month title must use `{年份}年{月份}月计划`. The collapsed action is `展开日历`; only expanded state may use `收起日历`.
- The default unfinished state uses collapsed week calendar, not a full-month calendar, unless the prompt explicitly asks for expanded calendar.
- Collapsed week calendar must show exactly 7 weekday columns and 7 date cells.
- Subject legend must include `语文`, `数学`, `物理`, `化学`, `生物` in the subject colors defined in this file.
- Task section title should be `今日任务`.
- Task cards must keep all content inside the white rounded card, including progress text, progress bar, and play button.
- Task cards must use the subject tag color for the subject. Do not use a single generic blue tag for every subject.
- The active bottom tab must be `学习`, not `首页`.
- Bottom tabbar must not cover the final task card, progress row, or play button. Reserve scroll padding at the bottom.

Daily learning-plan page order:

1. Top channel tabs.
2. Assistant bubble.
3. Month title and `展开日历`.
4. Subject legend.
5. Collapsed week calendar or expanded month calendar.
6. Task list or empty state.
7. Bottom tabbar.

Top channel:

- `学习计划` active with cyan underline.
- `全部课程` secondary on the right.
- In all-courses page, swap active state: `全部课程` active, `学习计划` muted.

Assistant bubble:

- 40px assistant icon.
- White bubble, radius `8px` to `10px`.
- Text 14px Medium `#071D39`.
- State copy:
  - Incomplete: `{学生名}同学，请完成今天的学习计划吧`.
  - Completed: `{学生名}同学，今日计划全部完成啦！真棒！`.
  - No plan: `{学生名}同学，今日暂无学习计划，有余力的话可以前往课程继续充充电哟~`.

Month calendar:

- Title: `{年份}年{月份}月计划`.
- Actions: `展开日历` / `收起日历`.
- Subject legend uses exact subject colors.
- Week row: `周一` to `周日`.
- Date cells: 7 columns, about `54px` high, 6px gap, 8px radius.
- Selected date: dark gradient with white number.
- Planned dates show subject dots under number.
- Expanded calendar shows month switch controls and full 7-column grid.
- Expanded state must push task cards down; task cards cannot overlap the calendar.

Task card:

- White card width about `362px`, height about `124px`, radius `12px`.
- Top row has subject tag and knowledge point.
- Title example: `3.1.1.1 导数的概念与计算(一轮)`.
- Progress text examples: `12:30/37:01`, `00:00/37:01`, `37:01/37:01`.
- Completed state shows `已学习`.
- Right action is a 32px circular play button.

Empty/login states:

- `今日无计划~` empty state keeps the calendar context visible.
- Login-required state preserves top channel and active `学习` tab.
- Copy: `请登录查看学习计划`.
- CTA: `立即登录`.

All-courses catalog:

- Subject chips sit below tabs. Selected chip uses black gradient; unselected chips are white.
- Course-cover carousel appears in the top atmosphere; center cover is primary and side covers are partially visible/faded.
- Content sheet starts around y `316px`, with white-to-light-gray gradient.
- Course summary includes:
  - Title, e.g. `领航培优灵活学·高一数学(下)`.
  - Metadata: `{n}模块｜{n}专题｜{n}考点｜{n}视频`.
  - Teacher avatar/name.
  - Utility icons and `知识图谱` pill.
- Module tabs use `模块一`, `模块二`, `模块三`, `模块四`.
- Left topic sidebar width about `83px`.
- Right video list width about `284px`.
- Video rows include title, difficulty stars, progress time, status tags, and orange play button.
- Optional floating shortcut: `上次学到`.

## 作文批改

### Entry And Score Sheet

Composition entry should live in `AI学习工具`, not as a separate marketing hero.

Full-score sheet:

- Dim current page behind the sheet.
- Bottom sheet width `390px`, height about `332px`, top radius `16px`.
- Title: `请选择本次作文满分`.
- Helper: `请选择作文满分，后续会按照该满分对应的高考评分规则进行批改`.
- Options: `50 北京`, `60 全国/天津`, `70 上海`.
- Selected option uses blue border/text.
- Bottom buttons:
  - `取消`: white with dark border.
  - `开始拍照`: black gradient; disabled at reduced opacity until score is selected.

### Capture Flow

Use a dark camera-first interface.

Overall:

- Canvas `390px`, black base.
- Status bar icons/text are white.
- Camera preview starts around y `96px`, width `390px`, height about `520px`, radius `12px`.
- Add subtle cyan/blue glows at top and bottom.

Header:

- Title bar y `48px`, height about `48px`.
- Back icon at x `16px`.
- Center two-step progress:
  - `1 拍题目`
  - `2 拍作文`
- Active step: cyan-blue circle and label `#0EC5FF`.
- Completed step: green circle/check and white label.
- Future step: translucent circle and low-opacity label.

Step 1:

- Main overlay: `第1步：拍题目`.
- Helper: `尽量把作文题干、材料和写作要求完整拍进去`.
- Keep text readable over preview with shadow.

Step 2:

- Main overlay: `第2步：拍作文（可多张）`.
- Helper:
  - `拍作文正文，不一定一张拍完可连续拍多张，直到整篇都拍清楚`.
  - For grid paper: `作文格通常分左、中、右三块。请一“块”一拍，每块单独一张照片。`
- Optional guidance pill: `查看示例` / `收起示例`.

Permission prompt:

- Center modal width about `285px`, white, radius `16px`.
- Title: `请允许访问相机`.
- Body: `为正常使用批改功能，请允许领航伴学使用相机`.
- Buttons: `暂不开启` and `去开启`.

Bottom controls:

- Center shutter: 66px circle around x `195px`, y `737px`, blue glow/gradient.
- Gallery button: 44px circle around x `63px`, y `748px`.
- Flashlight button: 44px circle around x `283px`, y `748px`.
- Thumbnail strip sits above controls, height about `111px`.
- Thumbnail size about `60px x 80px`, radius `7.5px`.
- Labels: `题目`, `第1页`, `第2页`, `第3页`.
- Delete corner: red 18px square at top-right.
- Multiple pages can show `去排序`.

### Order Confirmation And OCR

Order confirmation:

- Keep dark camera background.
- Title: `确认作文顺序`.
- Preview card: about `366px x 492px`, x `12px`, y `96px`, radius `8px`.
- Helper: `拖拽可调整图片顺序`.
- Selected thumbnail uses 2px `#07A0FF` border.
- Bottom buttons:
  - `继续补拍`: translucent white.
  - `开始识别`: bright blue gradient.
- Confirmation modal copy:
  - `请确认作文页面顺序是否正确`
  - `按住拖拽可调整页面顺序`
  - `错误的顺序会影响最终的批改结果`
  - `请仔细核对哦～`

OCR loading:

- Background returns to light app system with soft top atmosphere.
- Main copy: `正在将作文图片识别为文字，请耐心等待～`.
- Show countdown such as `15s` and a soft blue progress bar.
- No bottom CTA.

OCR review:

- Title: `核对识别文字`.
- Assistant reminder tells users to check incorrect or missing OCR text.
- Sections:
  - `题目识别结果`.
  - `作文正文识别结果`.
  - Subsections `作文标题`, `作文正文`.
- Recognized text cards are white with pale inner text areas.
- Bottom actions:
  - `返回拍照`.
  - `确认文字并批改`.

### Correction Loading

Before consuming quota:

- Modal title: `确认开始批改？`.
- Body: `本次批改将消耗 1 次批改次数。`
- Buttons: `退出批改`, `确认批改`.

Expert correction loading:

- Return to dark camera-family background.
- Dim the作文 preview in a rounded `366px x 492px` card.
- Add scan/progress treatment over preview.
- Status: `作文批改中，请耐心等待(60s)`.
- Headline: `专家正在进行作文批改....`.
- Supporting copy: `将按照高考作文阅卷的完整流程及标准，对作文进行批改`.
- Do not show exit/retry/CTA while correction is in progress.

### Explanation Walkthrough

- Title: `作文讲解`.
- Optional right pill: `跳过`.
- Left side shows real annotated作文 photos, not generic placeholders.
- Right side is a narrow teacher commentary card.
- Bottom audio controls are fixed and preserve the home indicator.
- Stage colors:
  - Intro/final summary: cool pale card.
  - 起评分/审题立意: pale blue card, blue annotations.
  - 加分项/作文亮点: cream/orange card, yellow annotations.
  - 扣分项: pale red card, red annotations.
- Audio button copy progresses through:
  - `开始讲解`
  - `讲解中...`
  - `继续分析作文亮点`
  - `继续分析扣分点`
  - `进入作文总评`
  - `查看批改报告`

### Report, History, Feedback

Report flow:

- Intro title: `领航甄选作文 精批`.
- Generation copy: `正在为你生成专属批改报告～`.
- Preview title: `作文批改报告`.
- Sections include `题目解析`, `批改笔记`, `作文详解`, `老师点评`.
- Bottom actions: `重看讲解`, `下载报告`.

History:

- Title: `历史批改记录`.
- Monthly summary:
  - With records: `本月已完成 5 篇作文练习`.
  - Empty: `本月还没有进行作文练习`.
- Record rows show score/category, correction time, locked/unlocked state.
- Month selector sheet title: `选择查看的月份`.

Feedback sheet:

- Title: `您的反馈会让我们变得更好`.
- Chips: `打分不准`, `讲解的不对`, `文字识别不准`, `批改时间太长`, `报告生成时间太长`, `其他`.
- Include optional screenshot upload and textarea.
- CTA: `提交`.

## Copy Rules

- Use the product's short task-oriented copy.
- Preserve existing Chinese punctuation and terminology from Figma/UI skill.
- Avoid explanatory in-app text unless the flow requires instruction or confirmation.
- Do not invent new labels when an existing copy pattern exists.
- Common actions:
  - `去制定`
  - `下一步`
  - `开始生成学习计划`
  - `去学习`
  - `确认`
  - `展开日历`
  - `收起日历`
  - `拍照批改`
  - `开始拍照`
  - `开始识别`
  - `确认文字并批改`
  - `确认批改`
  - `查看批改报告`

## Implementation Guardrails

- Match the project UI skill before inventing new visual patterns.
- Keep every visible child inside its card, sheet, modal, calendar cell, or fixed bar.
- Use `box-sizing: border-box` globally.
- Use flex/grid for card internals and reserve columns for right-side actions.
- Avoid nested cards unless the source design explicitly uses an inner panel.
- Do not let fixed bottom actions hide scroll content.
- Do not rely only on color to convey selected, disabled, completed, locked, or loading states.
- Keep real course covers and作文 photos inspectable.
- Use dark camera UI only for composition capture/order/correction-loading flows; do not leak the dark style into normal learning-plan pages.

## QA Checklist

- The screen uses the correct 375px or 390px family.
- The first viewport shows useful learning or composition workflow content.
- Top atmosphere, page background, cards, tags, and tabbar match the relevant flow.
- No text, badge, metric, button, icon, or calendar dot is clipped.
- CTAs sit inside their cards or fixed action bars.
- Fixed tabbars and action bars do not cover scroll content.
- `首次`, `更新`, `已学习`, selected, disabled, loading, locked, and completed states are distinct.
- Subject colors match legends, date dots, tags, and course states.
- Calendar expansion/collapse changes layout without overlap.
- Composition capture uses dark camera chrome, two-step progress, thumbnails, and fixed controls.
- OCR/correction/report states follow the required sequence.
- Course recommendation and作文 imagery remains readable and specific.
- The page has been visually checked at the target phone width.
