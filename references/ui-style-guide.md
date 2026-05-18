# AI自主学习系统 UI Style Guide

## Layout

- Canvas: 375px or 390px wide mobile mini-program. Match the source product family; older commerce/recommendation home pages are commonly 375px, while newer learning-plan pages are commonly 390px.
- Page background: `#F0F2FA` or `#ECEEF5`; daily plan content area may use `#F7F8F9`.
- Auth/login background: `#F7F9FC` with soft cyan top gradient and optional blurred blue/purple ambient ellipses.
- Top atmosphere: vertical gradient from `#BFF9FF` to transparent, about 250px tall.
- Horizontal page margin: 14px to 16px.
- Main card width: about 347px on 375px screens; about 362px to 364px on 390px screens.
- Bottom tabbar: fixed, `rgba(255,255,255,0.88)`, top border `rgba(0,0,0,0.08)`, includes 34px iPhone home area.

Home page order:

1. Brand/header row or greeting row
2. Welcome/plan setup/pending-plan/success gradient card
3. Optional `AI学习工具` section, such as作文批改
4. Optional history or plan section, including empty state
5. `热门推荐` course grid
6. Bottom tabbar

Learning home state variants:

- Unpurchased/no-course: greeting row, history title, empty history illustration/text, two-item tabbar; omit pending task card.
- Purchased with first-time pending plans: greeting row, pending card with `首次` badges, history filters and history cards.
- Purchased with updated plans: greeting row, pending card with orange `更新` badges, spring date ranges, history filters and prior history cards.
- Pending completed: history list becomes primary; pending card disappears and filters move upward.
- Scrolled/sticky: greeting row and pending card are out of view; history title and filters sit near the top under the mini-program chrome.

Daily plan page order:

1. Top channel title
2. Assistant bubble
3. Month title and expand-calendar action
4. Subject legend
5. Collapsed week calendar or expanded full-month calendar
6. Task list or empty state
7. Bottom tabbar

All-courses page order:

1. Top channel title with `全部课程` active
2. Subject chips
3. Course-cover carousel
4. Course summary and utility actions
5. Module tabs
6. Left topic sidebar and right video list
7. Floating `上次学到` shortcut when useful
8. Bottom tabbar

Plan creation flow order:

1. Status bar and mini-program title bar
2. Three-step progress stepper
3. `伴学规划建议` gradient advice card
4. Step-specific form or selector: learning information, period setup, or knowledge-point selection
5. Date picker sheet or knowledge-point selection sheet when needed
6. Generation loading state
7. Generated plan overview and APP learning-plan handoff

Login page order:

1. Status bar
2. Centered brand logo/title/subtitle
3. Glass login card
4. Form fields
5. Agreement row
6. Primary login button
7. Guest mode

First-use setup modal order:

1. Dimmed current page background
2. Centered white modal
3. Modal title/subtitle
4. Grade selector
5. Province selector
6. Primary confirm button

## Color Tokens

- Main text: `#030409`, `#071D39`
- Secondary text: `#78818D`, `#828B94`, `#77838B`
- Muted text: `#A9B1B8`, `#8E9194`
- White card: `#FFFFFF`
- Glass card: `rgba(255,255,255,0.7)`
- Input fill: `#F1F4F7`
- Verification button fill: `#CCE9FB`
- Light border: `#E9E8E8`
- Calendar light gray: `#EBEEF1`
- Subject blue: `#00639E`
- Active tab orange: `#FF6200`
- Cyan underline: `#47EFF9`
- Dark action gradient: `#000000` to `#383838`
- Gold badge gradient: `#F1D79E` to `#E1B676`, text `#674B20`
- Update badge gradient: `#FFAA41` to `#FF811A`, text `#FFFFFF`
- Course price red: `#FF0000`
- Brand/header dark: `#1F242E`
- On-gradient supporting text: `#3E5A7D`, `#10424F`
- Login/page text: `#191C1E`, `#44474A`, `#4D535C`, `#5B5F61`
- Modal overlay: `rgba(38,38,38,0.5)`
- Validation red: `#E70000`
- Stepper active gradient: `#00B3E8` to `#0288FF`
- Stepper inactive fill: `rgba(18,128,162,0.14)`
- Stepper inactive text: `#2D5C78` and `#6F93A8`
- Stepper completed green: `#15C691`
- Advice note fill: `rgba(204,233,251,0.5)`, text `#00639E`
- Selection sheet background: `#F3F5F7`
- Recommendation card border: `rgba(0,203,249,0.6)`
- Knowledge-point selected blue: `#00639E`
- Learning-plan blue cell: `#F0F6FD`
- Learning-plan peach cell: `#FDEEEE`
- Difficulty colors: 1-star `#31B9FF`, 2-star `#46DBA0`, 3-star `#F3D335`, 4-star `#9082FF`

Subject colors:

- 语文: `#FF3333`
- 数学: `#338BFF`
- 物理: `#22C6DF`
- 化学: `#AE51FA`
- 生物: `#21CC75`

History subject tag colors:

- 数学: border `rgba(27,56,178,0.5)`, text `#1B38B2` or border `rgba(0,99,158,0.5)`, text `#00639E`.
- 物理: border `rgba(0,99,158,0.5)`, text `#00639E`.
- 化学: border `rgba(47,16,158,0.5)`, text `#4C32A8`.
- 语文: border `rgba(158,0,3,0.5)`, text `#9E2F31`.
- 生物: border `rgba(5,97,50,0.5)`, text `#067A3F`.

## Typography

- Primary Chinese font: PingFang SC.
- Numeric/supporting font: MiSans.
- Calendar numbers: Space Grotesk or Inter Bold.
- Display/title style: HYYakuHei or PingFang SC Semibold.
- Do not use negative letter spacing. Avoid viewport-scaled font sizes.

## Radius And Shadows

- Main gradient card: 16px to 18px.
- Login card: 20px.
- Setup modal: 16px.
- List card: 12px.
- Calendar date block: 8px.
- Filter button: 10px.
- Small tag: 4px to 8px.
- Capsule button: 14px to 15px.
- Main card shadow: `0 9px 18px rgba(50,131,198,0.22)`.
- Login card shadow: `0 20px 40px rgba(0,99,158,0.08)`.
- Course task card shadow: `0 1px 1px rgba(0,0,0,0.05)`.
- Dark selected date/action shadow: `0 10px 15px -3px rgba(0,102,134,0.2), 0 4px 6px -4px rgba(0,102,134,0.2)`.

## Components

### Brand Header And Grade Selector

- Some home/recommendation pages use a white top area instead of the full cyan atmosphere.
- Left side shows the product logo/brand mark, about 89px wide and 31px high.
- Right side uses a compact grade selector pill, about 66px by 27px, background `#F3F5F7`, radius 8px, text 12px Medium `#1F242E`, e.g. `高一`, with a small down arrow.
- Keep the header minimal; do not add search bars, large nav text, or extra controls.

### Login Page

- Use for phone verification and rights synchronization before entering the system.
- Canvas is commonly 390px wide and full-height.
- Background:
  - Base `#F7F9FC`.
  - Cyan top gradient from `#BFF9FF` to transparent.
  - Optional blurred ambient ellipses: blue `rgba(141,198,255,0.2)` near top and purple `rgba(193,172,255,0.1)` near bottom.
- Brand header:
  - Center app logo, about 48px square, radius about 9px.
  - Main brand title `领航伴学`, 36px display/heavy, dark `#191C1E`.
  - Subtitle `陪伴学习日常，助力学习跃升`, 16px Regular, `#5B5F61`.
  - Header block sits near top, roughly y 79px to 215px.
- Login card:
  - Width about 358px, height about 490px, radius 20px.
  - Background `rgba(255,255,255,0.7)`, backdrop blur 6px.
  - Padding about 24px, vertical gap about 24px.
  - Shadow `0 20px 40px rgba(0,99,158,0.08)`.
- Card title:
  - `登录`, 24px Semibold, line height 32px, `#191C1E`.
  - Helper copy 13px, line height 20px, `#5B5F61`: `为了同步您的课程权益，请务必使用购课时的手机号进行登录验证`.
- Form:
  - Label 15px Medium, `#5B5F61`, above each field.
  - Input height about 55px, radius 10px, fill `#F1F4F7`, horizontal padding 16px.
  - Input text 16px Medium, `#191C1E`.
  - Phone example: `134 2222 2222`; code example: `123456`.
  - Verification button lives inside the code field on the right: fill `#CCE9FB`, radius 8px, text `获取验证码`, 13px Medium, `#00639E`.
- Agreement row:
  - 22px checkbox/check icon on the left.
  - 12px text `#4D535C`; links `《服务条款》` and `《隐私政策》` use `#00639E`.
  - Copy: `登录即代表同意《服务条款》与《隐私政策》`.
- Primary login button:
  - Full card width about 310px, height about 49px.
  - Black to dark gradient, radius 10px.
  - Text `立即登录`, 16px Semibold, white, with a small right arrow.
  - Shadow `0 6px 7.5px rgba(23,166,210,0.2)`.
- Guest mode:
  - Centered text `游客模式`, 15px Regular, `#44474A`.
  - Keep it visually secondary; do not style it as a filled button.

### First-Use Setup Modal

- Use when the user must complete basic information before plan generation.
- Background is the current app page dimmed by a modal overlay `rgba(38,38,38,0.5)`.
- Modal card:
  - Width about 286px, height about 325px.
  - Centered vertically, radius 16px, white background.
  - No heavy shadow; the dim overlay provides separation.
- Header:
  - Title `开启伴学之旅`, 20px display/heavy, `#2D3338`, centered.
  - Subtitle `请完善您的基础信息，制定专属学习计划`, 13px Regular, `#8E9194`, centered.
- Selector groups:
  - Width about 254px, label 13px Regular, `#191C1E`.
  - Option row height 40px, fill `#F1F4F7`, radius 10px.
  - Left value 15px Regular, `#191C1E`; right chevron 16px.
  - Typical fields:
    - `当前年级`: `高二`
    - `高考省份`: `北京`
- Primary button:
  - Width about 254px, height 40px, radius 10px.
  - Black to `#252525` gradient.
  - Text `开始使用`, 15px Semibold, `#F7F9FF`.
- Do not overcrowd the modal with explanation; it should feel like a required, lightweight setup step.

### Plan Creation Title Bar

- Use for the plan creation flow after a user taps `去制定`.
- Canvas is commonly 390px wide with white page background and a cyan top atmosphere about 224px high.
- Title bar sits below the status bar, height about 48px.
- Left control is a 24px back arrow around x 14px.
- Center title is 17px Medium `#191C1E`, e.g. `高二数学-春季自主计划` or `高二数学-寒季计划`.
- Right side keeps the mini-program capsule: 28px high, rounded 56px, translucent white with white border, close/more icons and a subtle divider.

### Progress Stepper

- Use the exact three steps: `学习信息`, `计划考点`, `生成计划`.
- Place around y 92px, full width 390px, horizontal padding 24px, vertical padding 16px.
- Step item uses a 22px numbered circle, 6px gap to label, and 16px Medium label.
- Active step:
  - Circle uses vertical gradient `#00B3E8 -> #0288FF`.
  - Number is white, 13px Semibold.
  - Add halo/shadow: `0 0 0 4.9px rgba(19,196,242,0.2)` plus soft blue shadow.
  - Label color `#008EBA`.
- Inactive step:
  - Circle fill `rgba(18,128,162,0.14)`.
  - Number color `#2D5C78`.
  - Label color `#6F93A8`.
- Dividers between steps are 2px high, `#C4C7CA`, inset by about 8px.
- Keep the stepper light; do not wrap it in a card.
- Completed steps:
  - Replace the number with a 14px white check icon.
  - Circle fill becomes `#15C691`.
  - Label returns to main text `#191C1E`.
  - In step 2, step 1 is completed; in final result pages, all three steps are completed.

### Companion Planning Advice Card

- Use at the top of plan creation forms, under the progress stepper.
- Width about 362px, height about 217px, x 14px, y about 154px to 156px.
- Radius 14px, white 1px border, backdrop blur 6px, shadow `0 4px 24px rgba(50,131,198,0.16)`.
- Background uses the same calm blue gradient family as the main home card, with about 80% opacity.
- Title `伴学规划建议`: 20px display/heavy, `#071D39`, around x 30px.
- Right context text appears on the title line: `{季节}学季 · 在读 {n} 科`, 14px Medium `#071D39`; the number uses MiSans 16px Demibold.
- Body copy:
  - Intro line: `接下来两步即可生成学习计划：`
  - Bullet 1: `当前为第1步，请填写{学科}可学习周期与每日课时`
  - Bullet 2: `第2步将根据这些信息给出建议规划的视频数量`
  - Use 14px Regular `#071D39`, 4px dot bullets, 8px gap.
- Recommendation panel:
  - White translucent block, about 330px by 66px, radius 10px.
  - Single-subject spring can show two columns: `2 课时 / 周一至周五上限` and `4 课时 / 周末上限`.
  - Multi-subject or simplified season can show one centered metric: `4 课时 / 建议单日上限`.
  - Metric number uses MiSans 22px Demibold `#071D39`; unit/label uses PingFang SC 13px `#2E3641`.

Step 2 planning advice variant:

- Use when the user has completed learning information and is selecting knowledge points.
- Height grows to about 306px; width remains about 362px.
- Subtitle can be `已匹配 2026年3~6月春季 学习节奏` or `已匹配 2026年1~2月寒季 学习节奏`.
- Keep the season/enrollment context on the title line, e.g. `春季学季 · 在读 1 科` or `寒季学季 · 在读 2 科`.
- Replace the first-step bullet copy with outcome-oriented guidance:
  - `根据你目前的在读学科数量，和当前所在学季周期，建议该学季学习课时40-60个，且建议学习的课时数大约覆盖考点数13-20个`
  - `目前成绩为89分，希望提升到120分，建议春季重点学习2~3星难度的视频，先把核心基础打牢！按照节奏推进，很有希望达到心仪分数，加油！`
- Metric panel:
  - About 320px by 75px, translucent white, radius 10px.
  - Two columns: `40-60 个 / 建议学习课时`, `13-20 个 / 建议学习考点`.
  - 寒季 two-month multi-subject examples can use smaller ranges such as `30-40 个 / 建议学习课时` and `10-13 个 / 建议学习考点`.
  - Use a 28px vertical divider between metric columns.
- Use small decorative bullet/quote marks at the start of explanatory lines; text remains 14px `#071D39`.

Previous-season review card:

- Use on season update flows when there is previous learning data.
- White or pale gray card, width about 362px, height about 270px, radius 16px.
- Header title: `上学季学习情况回顾`, 20px display/heavy.
- Subtitle: `已完成 8 个考点 · 24 个视频`, 13px Regular.
- Inner white translucent panel about 330px by 129px, radius 10px.
- Metrics: three equal columns with MiSans 22px numbers and 13px labels:
  - `1 个 / 未完成专题`
  - `1 个 / 未完成考点`
  - `1 个 / 未完成视频`
- Under metrics, show short bullet insights, e.g. `未完成考点：集合的概念与基本性质`.
- Bottom recommendation note: fill `rgba(204,233,251,0.8)`, radius 8px, copy `建议本学季优先补齐未完成考点（下方可一键勾选）`.

### Learning Information Form

- Form starts around y 393px, x 14px, width 362px.
- Use vertical spacing of 24px between major groups and 12px between label and control.
- Labels are 16px Medium `#191C1E`.
- Score pair:
  - Label: `最近一次{学科}考试成绩`.
  - Two inputs, each 168px wide and 52px high, radius 8px, fill `#F1F4F7`.
  - Place a centered `/` between inputs; the right input represents full score and may show helper suffix `/ 150`.
  - Placeholder `请输入` uses 16px Medium `#A9ABAE`; entered values use `#191C1E`.
- Target score:
  - Label `目标分数`.
  - Single input, 362px by 52px, radius 8px, fill `#F1F4F7`.
- Study frequency:
  - Label `{学科}可学习频率`.
  - Four horizontal chips, each about 83px by 40px, radius 100px, 10px gap.
  - Default chip fill `#F1F4F7`, text 16px Regular `#44474A`.
  - Selected chip is white with 1px `#00639E` border and blue text.
  - Common options: `每周`, `每双周`, `每三周`, `每四周`.
- Recommendation note:
  - Fill `rgba(204,233,251,0.5)`, radius 6px, padding 10px.
  - Text 14px `#00639E`; key subject and hour numbers are Medium.
  - Copy examples:
    - `建议数学周中单日2课时以内，周末单日4课时以内`
    - `建议数学单日学习课时4课时以内`
    - `当前在读学科共2科，其余学科还未规划`
- 寒暑季 multi-subject learning information variant:
  - Use period planning instead of weekday frequency chips.
  - Advice card context commonly reads `寒季学季 · 在读 2 科`.
  - Score pair can start empty on the left and prefill the full score `150` on the right; filled examples use `89 / 150`.
  - Target score starts as `请输入` and filled examples use `120`.
  - The bottom `下一步` stays visible; when score, target, dates, or hours are incomplete, apply 50% opacity to the bottom action container/button.
- Day/hour rows:
  - Use a 362px-wide vertical list, 8px gap.
  - Each row is 64px high, fill `#F1F4F7`, radius 8px, padding 16px.
  - Left label: `周一` to `周日`, or `每日可学课时`, 16px Medium `#191C1E`, tracking about 0.6px.
  - Right control: minus button, numeric value, unit, plus button.
  - Minus button: 24px circle, white fill, 1px `#00639E` border, 12px minus icon.
  - Plus button: 24px circle, fill `#00639E`, 12px plus icon in white.
  - Number uses MiSans 22px Demibold `#191C1E`; unit `课时` is 13px Regular.
  - Default empty values can be `0`; filled weekend examples use `2`.

### Period Planning Card

- Use when the learning information step asks for one or more learning periods instead of weekly frequency chips.
- Section label: `计划学习周期和每日课时`.
- Put the blue recommendation note above period cards.
- Default state:
  - First period title is `计划学习周期一`.
  - Date values show `请选择日期` on both start and end sides.
  - Daily hour value can be `0 课时`.
  - Do not show `删除` when there is only one empty period.
- Filled/removable state:
  - Date values use MiSans 16px Demibold, e.g. `2026.01.01` to `2026.01.15`.
  - Multiple periods are stacked with 12px gap; titles increment as `计划学习周期一`, `计划学习周期二`.
  - Show a red `删除` action in the card header when the period can be removed.
  - Hour values can differ by period, e.g. `2 课时` for the first and `1 课时` for the second.
- Period card:
  - White card, width 362px, radius 10px.
  - Border `#F2F2F2` or `rgba(195,197,216,0.1)`.
  - Shadow `0 8px 24px -4px rgba(0,81,224,0.08)`.
  - Padding about 17px horizontal and 21px vertical, 16px internal gap.
  - Header row uses an 8px dot `#0086AE` plus title `计划学习周期一`, 16px Medium `#181C21`.
- Date range selector:
  - Fill `#F1F4F7`, radius 8px, padding `12px 16px`.
  - Left group: label `开始日期`, placeholder/value below.
  - Right group: label `结束日期`, placeholder/value below, right aligned.
  - Middle uses a small arrow/connector icon.
  - Labels are 14px Regular `#5B5F61`; placeholders use 16px Medium `#A9ABAE`.
- Add period row:
  - Width 362px, height 58px, white fill, radius 10px.
  - Border `rgba(0,99,158,0.31)`, same soft blue shadow.
  - Center text `＋ 添加时间段`, 16px Medium `#00639E`.

### Date Picker Bottom Sheet

- Use when selecting `开始日期` or `结束日期`.
- Keep the current page visible behind a dim overlay.
- Overlay: `rgba(38,38,38,0.4)` plus optional backdrop blur 6px.
- Bottom sheet:
  - Anchored to bottom, width 390px, height about 481px.
  - White fill, top-left and top-right radius 20px.
  - Header starts around y 355px in the full canvas.
  - Title `选择开始日期` or `选择结束日期`, 16px Medium, black, left padding 24px.
  - Close icon 16px at right around x 350px.
- Calendar:
  - Container width about 362px, x 14px, y about 401px.
  - Header height about 52px, center month/year text like `一月 2026`.
  - Month/year text uses about 18px; weekday row uses 18px to 23px depending on implementation.
  - Date cells are about 31px square with 2px radius.
  - Disabled adjacent-month dates use `rgba(0,0,0,0.25)`.
  - Normal dates use `rgba(0,0,0,0.85)`.
  - Selected date uses fill `#00639E`, white number, 2px radius.
- Fixed bottom action inside the sheet:
  - Container has translucent white fill and blur.
  - Button width 342px, height 44px, x 24px, radius 8px.
  - Button text `确认`, 17px Medium, white.

### Validation And Disabled States

- Validation errors are inline and immediate.
- Invalid input keeps its normal pale fill but adds a 1px red border `#E70000`.
- Red helper text is 14px Regular `#E70000`, full field width, directly below the invalid control.
- Examples:
  - `得分不能超过满分`
  - `目标分不能超过满分`
- When errors exist or required fields are incomplete, the fixed `下一步` button remains visible but uses 50% opacity.
- Disabled bottom button should still preserve the black gradient, dimensions, and shadow relationship; change opacity rather than introducing a gray replacement style.

### Knowledge-Point Selection Field

- Use in step 2 under the planning advice card.
- Group starts with label `计划学习{学科}考点（多选）`, 16px Medium, `#191C1E`.
- Selector row:
  - Width 362px, height 56px, fill `#F1F4F7`, radius 10px, padding 16px.
  - Empty state: `请选择`, 16px Medium `#A9ABAE`.
  - Selected state: `已选24个考点，79个视频`, 16px Medium `#191C1E`.
  - Right chevron is 24px, rotated to indicate drill-in.
- Bottom action for step 2 is `开始生成学习计划`, 17px Medium, black gradient button.
- If previous-season recommendations exist, the selector can appear below a review card around y 770px; otherwise it can sit directly below the advice card around y 487px.
- First-submit selector often remains empty (`请选择`) until the bottom sheet confirms selected points.

### Knowledge-Point Selection Sheet

- Use after tapping the knowledge-point selector.
- It is a bottom sheet over a dimmed background, with the sheet starting around y 72px, width 390px, height about 739px, fill `#F3F5F7`, top radius 16px.
- Header:
  - Top summary around x 24px, y 97px: `已选 9 个考点，30 个视频`.
  - Numbers use blue `#00A7D8`; surrounding text is 16px Medium black.
  - Close icon is 16px at the right.
- Recommended unfinished card:
  - White card, width 362px, radius 16px, border `rgba(0,203,249,0.6)`, shadow `0 4px 20px rgba(0,99,158,0.08)`.
  - Title `上学季未学习推荐`, 17px display/heavy `#00639E`.
  - Subtitle `优先补齐未完成考点`, 12px `#5B5F61`.
  - Right pill `一键勾选未学习`, height 36px, radius 100px, pale blue fill, blue text.
- First-submit sheet variant:
  - Omit the recommendation card when there is no previous-season unfinished content.
  - Start with a white rounded topic tree card around y 143px, width 362px, radius 16px.
  - Additional collapsed topic cards can appear below as separate white cards, also radius 16px.
  - Top summary still shows selected counts, e.g. `已选 9 个考点，30 个视频`.
- Topic sections:
  - Topic row uses 24px expand/collapse icon, 16px Medium title, and right `全选` pill.
  - Subtopic row uses 24px expand/collapse icon, 16px Medium title, and right `全选` pill.
  - Selected `全选` pill is fill `#00639E`, white text; unselected is pale blue fill with blue text.
  - Use thin divider lines `#E6E8EA` between groups.
- Knowledge-point rows:
  - Indent to x about 60px, width about 300px, height about 69px.
  - Title 15px Regular `#191C1E`, e.g. `2.1.1.1 圆锥曲线标准方程与解答`.
  - Show star difficulty under the title, about 56px wide.
  - Optional `已学习` tag: 16px high, 0.5px blue border, 11px blue text.
  - Selection control at right is 22px circle:
    - Selected: fill `#00639E`, white check.
    - Unselected: white fill, 1.5px `#00639E` border.
- Bottom sheet action:
  - Fixed translucent white container.
  - Button width 342px, height 44px, radius 8px, black gradient, text `确认`.
- Keep content scrollable; the first recommendation card may stay near top while topic groups continue below.

### Generation Loading

- Use immediately after `开始生成学习计划`.
- Page background `#F0F2FA`, cyan top atmosphere height about 256px.
- Keep the normal title bar with the plan title.
- Center a 170px circular glow around y 109px; inside place a 56px assistant/robot mark.
- Main title: `正在生成学习计划`, 20px MiSans Demibold, centered.
- Under the title, add a 320px horizontal cyan gradient divider, 2px high, about 40% opacity.
- Helper copy: `整合学习节奏与知识点分布，生成专属学习计划`, 14px Regular `#5B5F61`, centered.
- Do not show bottom CTA or tabbar in this transient state.

### Generated Plan Overview

- Use after plan generation completes.
- Stepper shows all three steps completed with green check circles.
- Title bar changes from `{年级}{学科}-{季节}自主计划` to `{年级}{学科}-{季节}计划`.
- Sync success card:
  - Width 362px, height about 92px, x 14px, y about 154px.
  - Blue gradient, radius 14px, white border, blue shadow.
  - Text: `计划已同步至“领航伴学APP-学习计划”`, 14px Medium `#071D39`.
  - Helper: `当前仅展示首月明细，更多月份计划请查阅“学习计划”完整内容。`, 13px `#2F5079`.
  - Right black pill button `去学习`, about 74px by 36px.
- Plan overview card:
  - Blue-green gradient card, width about 361px, height about 354px, radius 16px.
  - Use concise explanatory paragraphs with bold inline numbers/terms: `4大核心模块`, `24个高频考点`, `占比超 85%`.
  - Inner glass/white panel shows `知识点总览`.
  - Metric strip: four columns `4 模块`, `11 专题`, `24 考点`, `79 视频`.
  - Difficulty overview:
    - Stacked 8px rounded bar with 1-star blue, 2-star green, 3-star yellow, 4-star purple.
    - Legend examples: `1星 25%`, `2星 35%`, `3星 25%`, `4星 15%`.
- Month arrangement section:
  - Section title `3月学习安排` with a 3px x 20px blue vertical accent.
  - Large white card, radius 16px, containing a month calendar preview.
  - Calendar cells are compact rectangles; planned days show small course labels, star marks, and color by difficulty/type.
  - This is a generated-plan preview, so it can be denser than the daily learning-plan week strip.

### APP Learning Plan Handoff Page

- Use for the APP-side learning plan after a generated plan is synced.
- It follows the regular daily plan style but can start without the plan-generation stepper.
- Top channel tabs:
  - `学习计划` active with the cyan underline and gradient title.
  - `全部课程` secondary at the right.
- Assistant bubble copy uses the student name and daily plan state, e.g. `刘佳宁同学，请完成今天的学习计划吧`.
- Month block may omit subject legend if only one subject is shown.
- Week strip has weekday row, then 7 date blocks; selected date uses black gradient, planned dates show blue/green dots.
- Expanded month view keeps the same top channel but changes `展开日历` to `收起日历`, reveals month-switch controls, restores the full subject legend, and pushes task cards lower.
- Scrolled expanded view can remove the assistant bubble and clip the month header/legend upward under the top channel; keep enough visible date rows to make the scroll position clear.
- Login-required APP plan states still preserve the top channel and active bottom tab; use the shared login-required empty-state system instead of inventing a new auth page.
- Task cards follow the normal course task card pattern.
- Bottom tabbar active item is `学习`, color `#FF6200`.

### APP All-Courses Catalog Page

- Use for the `全部课程` tab inside the APP learning section.
- Top channel:
  - `全部课程` is active, 18px Semibold black with cyan underline.
  - `学习计划` becomes secondary, 17px Regular `#6F7D7F`.
  - Bottom tabbar still keeps `学习` active because this page lives inside the learning section.
- Subject chips:
  - Sit below the channel tabs around y 101px.
  - Selected chip uses the black action gradient, 14px Semibold white, 13px radius.
  - Unselected chips are white with `#7D898C` text.
  - Typical order: `数学`, `物理`, `化学`.
- Course-cover carousel:
  - Lives in the top atmosphere before the white content sheet begins.
  - Center book cover is largest and fully opaque; side covers are partially visible at left/right and can use about 40% opacity.
  - Covers use subject color, book-like bevel/shadow, vertical brand text, and teacher/subject art; do not replace them with flat generic cards.
  - Add a small centered carousel indicator at the bottom edge of the carousel/content seam.
- Content sheet:
  - White-to-`#F3F5F7` vertical gradient, starts around y 316px, full width.
  - Header summary area is about 103px tall with a bottom divider.
  - Course title example: `领航培优灵活学·高一数学(下)`, 17px to 18px Medium `#1F242E`.
  - Metadata line example: `4模块｜6专题｜18考点｜58视频`, 12px to 13px Regular `#696C6F`.
  - Teacher row uses a 20px avatar and 14px teacher name, e.g. `冯雪`.
  - Right utility icons are 29px square; the `知识图谱` pill is about 121px by 31px, rounded, gray fill, icon plus 14px text.
- Module tabs:
  - Horizontal row inside a 54px strip.
  - Active module chip uses pale orange fill `#FFEDE2`, orange border `#FFA167`, text `#FF6200`.
  - Inactive module chips use `#E8EBED`, text `#4D535C`.
  - Labels use `模块一`, `模块二`, `模块三`, `模块四`.
- Topic sidebar:
  - Left column width about 83px.
  - Active topic uses white background, right-side rounded corners, and a 4px orange vertical indicator.
  - Topic item contains a 12px label like `专题一` and a 13px topic name; allow two or three lines without crowding.
  - Inactive topics use `#F3F5F7` or white depending on scroll grouping, with `#4D535C` text.
- Video list:
  - Right column starts around x 94px and width about 284px.
  - Group titles use 16px to 17px Medium `#1F242E`, e.g. `1.1.1 集合的概念`.
  - White rounded list cards use 14px to 15px radius, 0.5px `#E3E3E3` border, and subtle blue-gray shadow.
  - Each video row is about 95px high, separated by thin dividers except after the last row.
  - Video title uses 15px to 16px Regular `#1F242E`.
  - Difficulty stars sit under the title; progress time uses 12px `#A9B1B8`, e.g. `29:16/36:58`.
  - Status tags include orange `上次学到`, blue `已学习`, and purple `目标专属`.
  - Right action is a 29px peach/orange circular play button.
- Floating shortcut:
  - A vertical `上次学到` button may stick to the right edge, blue gradient `#00B3E8 -> #0288FF`, about 44px by 50px, left rounded corners.

### Greeting Row

- Icon/avatar about 50px, rounded about 14px, light shadow.
- Text: `你好，{学生名}同学`, 20px Medium, `#071D39`.

### Assistant Bubble

- 40px assistant icon.
- White bubble, rounded 8px to 10px.
- Text: 14px Medium, `#071D39`, line height about 28px.
- Bubble can be 30px high for one line or 52px high for two lines.

### Welcome Guide Card

- Use this on first-entry or discovery-oriented home pages.
- Card width about 347px on 375px screens, height about 196px, radius 18px.
- Background is a soft blue radial/linear gradient, approximately `#D9F6FC` to `#B0EFFA` to `#A3DDFA`.
- Center the AI assistant icon near the top, about 44px to 46px.
- Greeting copy:
  - Small line: `你好，{学生名}同学`, about 15px, `#071D39`.
  - Main line: `欢迎进入领航甄选自主学习系统`, about 16px Semibold, `#071D39`.
- Below the greeting, show a three-step value chain:
  - Icon 1: `自主学习计划`
  - Icon 2: `甄选内容`
  - Icon 3: `检测和提升`
- Step icons sit in glassy rounded squares/circles about 40px to 46px, connected with dotted or segmented lines.
- Step labels are 13px Regular, `#3E5A7D`.

### Plan Setup Compact Card

- Use when the home page needs to prompt users to create study plans while also showing recommendations below.
- Card width about 347px, height about 305px, radius 18px, white border, blue shadow.
- Background uses the same blue-green gradient family as the main pending-task card.
- Top right season ribbon: `2026-寒季` or similar, 84px by 26px, white text.
- Header row contains 44px AI icon and two-line greeting:
  - `你好，{学生名}同学`
  - `开始定制你的学习计划吧`
- Task rows are more compact than the full home pending card:
  - Width about 315px, height about 64px, radius 12px.
  - Background white with slight transparency gradient.
  - Left icon glass square about 36px with subject icon.
  - Title 15px Medium `#071D39`, subtitle 12px Regular `#78818D`.
  - Gold `首次` badge at row top right.
  - Dark capsule CTA `去制定`, about 13px Semibold.

### Success Plan Card

- Use when all learning plans have been created.
- Card width about 347px, height about 211px, radius 18px, white border, blue shadow.
- Background uses the blue-green gradient family, with a celebratory but still restrained center composition.
- Top right season ribbon uses the active term, e.g. `2026-春季`.
- Center area:
  - AI assistant illustration about 64px.
  - Title `太棒了!`, about 18px bold, dark teal `#072F3A`.
  - Message `您已完成所有学习计划的制定~`, 13px Regular, `#10424F`.
  - Primary button `去学习`, black capsule, 15px Semibold, white text, padding about 22px horizontal and 6px vertical.
- Keep celebration effects light: small sparkles/dots are fine; avoid confetti-heavy marketing visuals.

### Pending Task Card

- Width about 364px, height about 300px.
- Blue-green gradient using `#C7F6FF`, `#96E5F2`, `#77CBF7`.
- White border and soft blue shadow.
- Title: `待办事项`, 20px, dark blue-black.
- Season ribbon: e.g. `2026-寒季`, white text.
- Task rows: 3 rows, each about 72px high, 10px spacing.
- Row content: subject icon, title, season/time, gold status badge, dark capsule CTA.
- Row title pattern: `高中{学科}-学习计划制定`.
- Row subtitle pattern: `2026年寒季｜1～2月`.
- CTA: `去制定`.
- Badge variants:
  - `首次`: gold gradient `#F1D79E -> #E1B676`, text `#674B20`.
  - `更新`: orange gradient `#FFAA41 -> #FF811A`, white text.
- Season/range variants:
  - 寒季: ribbon `2026-寒季`, row subtitle `2026年寒季｜1～2月`.
  - 春季更新: ribbon `2026-春季`, row subtitle `2026年春季｜3～6月`.
- If there is no pending item, remove the pending card entirely and let the history section move upward.

### AI Learning Tools Section

- Use on the home entry page after the plan setup/pending card and before `热门推荐`.
- Section title: `AI学习工具`, 20px Semibold, `#1F242E`, aligned to the same 14px to 16px page margin.
- The section can contain a large monthly summary card and an embedded tool entry card.
- Composition monthly report card:
  - Width about 358px, height about 270px, radius 20px.
  - Background uses a light blue/white gradient with a subtle cyan radial glow; keep it airy, not dark.
  - Top-left pill: `作文练习月报`, about 16px icon plus 12px Medium blue text, translucent white fill and white border.
  - Main title: `本月已完成 5 篇作文练习`, 18px Semibold black.
  - Supporting copy: `作文批改记录会自动沉淀，方便你持续复盘表达问题。`, 14px Regular `#738494`, about 204px wide.
  - Right side shows an illustrated badge/medal and a large number such as `5`, Space Grotesk Bold, blue gradient text; label `本月批改` sits nearby.
  - CTA link: `查看所有批改结果`, 14px Medium `#00639E`, with a 16px chevron.
  - Status pill: `作文徽章已点亮`, 10px Medium `#0096D2`, pale cyan fill.
- Composition correction entry card inside the monthly card:
  - Width about 326px, height about 79px, radius about 15px.
  - Background pale blue gradient, with a 42px camera/tool icon at left.
  - Title `高考语文作文批改`, 15px Medium `#1B233E`.
  - Copy: `随学随练，有效提升，拍照上传后即可生成批改结果。`, 12px Regular `#4D535C`.
  - Primary action `拍照批改`: black pill, white 14px Medium text.
  - Quota ribbon at the top-right of the entry card: `可用 2/10`, gold gradient, 11px Medium `#7E4F0F`.
- This section should remain a practical tool surface; do not turn it into a promotional hero.

### Composition Full-Score Sheet

- Use before starting photo作文批改 when the user must choose the essay full score.
- Background:
  - Keep the current home page visible behind the overlay.
  - Apply black overlay about `rgba(0,0,0,0.24)` and dim the page image/content to about 30% opacity.
- Bottom sheet:
  - Width 390px, height about 332px, anchored to bottom.
  - White fill with top-left and top-right radius 16px.
  - Add subtle backdrop blur 5px and shadow `0 20px 28px rgba(19,28,67,0.32)`.
- Header:
  - Title `请选择本次作文满分`, 20px Medium black, x about 17px, y about 27px.
  - Helper copy `请选择作文满分，后续会按照该满分对应的高考评分规则进行批改`, 14px Regular `#828B94`, about 353px wide.
- Score options:
  - Three equal option cards, each about 112px by 74px, radius 10px, fill `#F1F5F9`, arranged horizontally with about 9px gap.
  - Options: `50 / 北京`, `60 / 全国/天津`, `70 / 上海`.
  - Number uses MiSans 24px Demibold; region uses 14px PingFang SC.
  - Selected option changes to fill `#F1F5FC`, 1px border `#0195F0`, and blue text `#0195F0`; selected region uses Medium.
- Bottom action area:
  - Fixed white area with blur, 60px high plus iPhone home area.
  - Left button `取消`: white fill, 0.5px dark border `#44474A`, 172px by 44px, radius 10px, black text.
  - Right button `开始拍照`: 172px by 44px, radius 10px.
  - Default/no score selected: black gradient button at 40% opacity.
  - After selecting a score: full black-to-`#252525` gradient with white text.

### Composition Capture Flow

- Use after the user taps `开始拍照` for作文批改.
- Overall frame:
  - Full 390px camera interface with black base.
  - Add subtle blue/cyan ambient glows at the top and bottom edges; do not use the pale app background here.
  - Status bar text/icons are white.
  - Main camera preview starts around y 96px, width 390px, height about 520px, radius 12px.
  - Bottom control area sits over black with blue glow; keep it fixed.
- Capture title/stepper:
  - Title bar height about 48px at y 48px.
  - Back icon at x 16px, white.
  - Center two-step progress: `1 拍题目` then `2 拍作文`.
  - Active step uses 20px cyan-blue gradient numbered circle and label `#0EC5FF`.
  - Completed step uses green `#15C691` circle with white check and white label.
  - Inactive future step uses translucent blue circle and low-opacity label.
  - Use a short 20px divider line between steps.
- Camera permission prompt:
  - Center modal width about 285px, white, radius 16px.
  - Title `请允许访问相机`, 16px Medium `#1F242E`.
  - Body `为正常使用批改功能，请允许领航伴学使用相机`, 15px Regular `#5B5F61`, line height 21px.
  - Buttons row has 9px gap, 16px side padding.
  - Secondary `暂不开启`: white fill, 0.5px `#44474A` border, 40px high, radius 10px.
  - Primary `去开启`: black fill, 40px high, radius 10px, 15px MiSans Demibold white.
- Step 1: 拍题目:
  - Active header: `1 拍题目`; `2 拍作文` remains inactive.
  - Center overlay copy in preview: `第1步：拍题目`, 20px Semibold white with black text shadow.
  - Helper: `尽量把作文题干、材料和写作要求完整拍进去`, 16px white.
  - Preview can show a rule-of-thirds grid and a scanned prompt image; keep instructional text readable over it.
- Step 2: 拍作文:
  - Header shows `拍题目` completed and `2 拍作文` active.
  - Center overlay copy: `第2步：拍作文 (可多张)` or `第2步：拍作文（可多张）`.
  - Helper variants:
    - General: `拍作文正文，不一定一张拍完可连续拍多张，直到整篇都拍清楚`.
    - Grid-paper guidance: `作文格通常分左、中、右三块。请一“块”一拍，每块单独一张照片。`
  - Add `查看示例` as a black translucent pill near the lower part of preview when example guidance is available.
- Example overlay:
  - When opened, dim the camera UI to about 40% opacity behind the example.
  - Show a large centered example image/card over the preview; dark backdrop stays visible.
  - Replace `查看示例` with `收起示例`.
  - Keep the header, shutter, gallery, flashlight, thumbnails, and sort controls visible but subdued.
- Bottom controls:
  - Large shutter button: 66px circle centered around x 195px, y 737px; blue glow/gradient center with ring.
  - Left gallery button: 44px circle around x 63px, y 748px.
  - Right flashlight button: 44px circle around x 283px, y 748px.
  - Home indicator remains white or `rgba(255,255,255,0.2)`.
- Captured thumbnails:
  - Horizontal strip above controls, around bottom 117px, height about 111px.
  - Thumbnail card about 60px by 80px, radius 7.5px; label below uses 12px Medium `rgba(255,255,255,0.7)`.
  - First thumbnail label for prompt is `题目`;作文 pages use `第1页`, `第2页`, `第3页`.
  - Each captured thumbnail has a red delete corner, 18px square, top-right, with white close mark.
  - For overflow, mask/clip the strip horizontally so more thumbnails imply scroll.
  - When multiple作文 pages exist, show a `去排序` pill on the right, about 62px by 28px, rounded 14px, bright blue gradient; disabled/subdued versions can use gray/translucent styling.

### Composition Order Confirmation

- Use after the user has captured the prompt and作文 pages and needs to verify page order before OCR/correction.
- Keep the dark camera-family background with a subtle blue glow at the top.
- Top bar:
  - Title `确认作文顺序`, centered, 17px Medium white.
  - Back icon at the left; status bar and home indicator stay white.
- Main preview:
  - Centered card about 366px by 492px on a 390px canvas, x about 12px, y about 96px.
  - Radius 8px, dark gray fallback fill, showing the currently selected photo.
  - Switching thumbnails changes the preview without changing the page chrome.
- Thumbnail strip:
  - Place below the preview, above the fixed action area.
  - Helper text `拖拽可调整图片顺序`, 13px Medium `rgba(255,255,255,0.7)`.
  - Thumbnail labels follow `题目`, `第1页`, `第2页`, `第3页`, `第4页`.
  - Selected thumbnail uses a 2px `#07A0FF` border; unselected thumbnails have no bright outline.
  - The strip supports horizontal scrolling and drag sorting.
- Bottom actions:
  - Fixed blurred dark action area.
  - Left `继续补拍`: about 174px by 44px, radius 10px, translucent white fill `rgba(255,255,255,0.2)`, white text.
  - Right `开始识别`: about 174px by 44px, radius 10px, bright blue gradient, 1px `#95DCFF` border, black MiSans Demibold text, optional sparkle icon.
- Order confirmation modal:
  - Use after `开始识别` when the app wants one more order check.
  - Dim current page with the modal overlay.
  - Centered white modal about 285px wide, radius 16px.
  - Title `请确认作文页面顺序是否正确`, 16px Medium `#1F242E`.
  - Body, 15px `#5B5F61`, line height about 23px:
    `按住拖拽可调整页面顺序`
    `错误的顺序会影响最终的批改结果`
    `请仔细核对哦～`
  - Buttons: secondary `返回调整`, primary `开始批改`.

### Composition OCR Loading

- Use immediately after order confirmation while images are recognized as text.
- Background is `#F7F8F9` with a soft blue/purple top atmosphere about 261px tall.
- Center an AI animation/icon around 128px square near the middle of the screen.
- Main copy: `正在将作文图片识别为文字，请耐心等待～`, centered, 15px MiSans Demibold, black-to-blue gradient text.
- Show countdown such as `15s`, 14px Medium `#0CA8E6`, centered below the main copy.
- Progress bar:
  - Width about 328px, height 4px, centered.
  - Use a soft blue glow and linear progress treatment.
- Do not add a bottom CTA; this is a passive waiting state.

### Composition OCR Review

- Use after OCR recognition and before consuming a correction quota.
- Background: `#F7F8F9` with the same soft top atmosphere.
- Top bar:
  - Title `核对识别文字`, centered, 17px Medium `#191C1E`.
  - Back icon on the left; keep mini-program status conventions.
- Assistant reminder:
  - 40px assistant avatar/icon on the left.
  - Speech bubble about 331px by 52px, white or very light fill.
  - Copy: `请重点检查识别错误的文字，以及漏识别的段落。修改后的文字会作为本次批改的作文内容。`
  - Use 12px Medium `#071D39`; keep it compact and readable.
- Content sections:
  - Start content around x 16px, width about 358px, with 24px section gap.
  - Section header uses a 3px by 18px cyan accent `#47BCFE` and 17px Medium title.
  - `题目识别结果` section uses a white card, radius 12px, with an inner pale text box fill `#FAFAFA`, border `#EAEAEA`, padding 12px.
  - `作文正文识别结果` section uses a white card with subsections `作文标题` and `作文正文`.
  - Subsection labels use 14px Semibold `#0990CB`.
  - Recognized text uses 15px line height about 24px; allow long text to scroll naturally.
- Bottom actions:
  - Fixed white action area with subtle top border.
  - Left `返回拍照`: white button with light border.
  - Right `确认文字并批改`: black gradient primary button.

### Composition Benefit Confirmation And Correction Loading

- Use before starting expert correction if the action consumes作文批改 quota.
- Benefit modal:
  - Dim the OCR review page behind it.
  - Centered white modal about 285px wide, radius 16px.
  - Title `确认开始批改？`, 16px Medium `#1F242E`.
  - Body: `本次批改将消耗 1 次批改次数。`
  - Emphasize the number `1` with MiSans Demibold 17px `#1F242E`; rest of the body is 15px `#5B5F61`.
  - Buttons: secondary `退出批改`, primary `确认批改`.
- Expert correction loading:
  - Return to a dark camera-family background with the作文 preview dimmed in a rounded 366px by 492px card.
  - Overlay a scanning animation/component over the preview.
  - Add a progress bar around y 614px, width about 317px, gray track plus cyan/purple gradient progress and glow.
  - Small decorative/progress icon may sit at the progress head.
  - Status copy: `作文批改中，请耐心等待(60s)`, 14px `#AAD9FC`.
  - Main headline: `专家正在进行作文批改....`, about 28px display font, cyan-to-purple gradient.
  - Supporting copy: `将按照高考作文阅卷的完整流程及标准，对作文进行批改` and `请耐心等待～`, 12px `#AAD9FC` at about 70% opacity.
  - Do not show an exit, retry, or primary CTA while correction is in progress.

### Composition Explanation Walkthrough

- Use after correction when the product plays a teacher-style作文讲解 before showing the final report.
- Canvas is commonly 390px wide with a white background.
- Top bar:
  - Title `作文讲解`, centered, 17px Medium `#191C1E`.
  - Back icon on the left.
  - Optional right skip pill `跳过` with a small play/next icon, about 60px by 28px, border `rgba(0,0,0,0.08)`, radius 40px.
- Main layout:
  - Left side shows stacked作文 photo cards, x about 16px, width about 206px, top about 95px or 104px.
  - First photo height about 300px, second about 322px to 324px; radius 7px to 8px.
  - Photos keep the real作文 texture visible; do not blur or replace them with generic placeholders.
  - Right side uses a narrow commentary card, x about 230px, width about 144px, padding 12px.
  - Commentary card radius: top-left 4px, other corners 16px, like a speech panel docked to the photo column.
  - Text in the card is dense but readable: 13px to 15px body, 20px to 24px line height.
  - Use bold/darker inline emphasis for key score, category, or diagnosis words.
- Stage color system:
  - Intro/system-sound and final overall summary: cool pale card `#F7F8FC`, gradient title from green/cyan/purple.
  - 起评分/审题立意: pale blue card gradient `#EDF5FF` to `#FAFCFF`, title `#2352D8`, blue annotation lines and numbered markers.
  - 加分项/作文亮点: warm cream/orange card `#FFF7F0` to `#FFFBF7`, title `#D67A00`, yellow annotation lines and markers.
  - 扣分项: pale red card `#FFF2F0` to `#FFFAFC`, title `#E0422D`, red correction circles/characters and red headings.
- Photo annotation marks:
  - Blue lines/markers identify审题、立意 or theme keywords.
  - Yellow underlines and numbered dots identify亮点 or加分依据.
  - Red circles and small red replacement characters identify错别字/扣分点.
  - Numbered dots are about 14px, with white border; blue dots use white numbers, yellow dots use black numbers.
  - Final overall page can show combined blue/yellow/red annotations plus a large handwritten score such as `44`.
- Audio control bar:
  - Fixed at the bottom with a white-to-transparent gradient mask above it so content fades behind controls.
  - Left speed button: `1.0x`, about 64px by 52px, glass white rounded 12px.
  - Center primary audio button: about 222px by 44px, black fill/gradient, radius 12px, white 16px MiSans Demibold.
  - Center button states/copy include `开始讲解`, `讲解中...`, `继续分析作文亮点`, `继续分析扣分点`, `进入作文总评`, `查看批改报告`.
  - Right pause button: about 64px by 52px, glass white rounded 12px, cyan pause icon.
  - Keep iPhone home indicator visible.
- Walkthrough copy progression:
  - Start with system-sound guidance: `你好呀同学～ 请先确认手机系统声音已打开，点击下方 “开始讲解”按钮，听我的讲解吧~`.
  - 起评分 card can introduce `咱们先看下作文的起评分～`, mention `43分`, then split into `首先在审题方面` and `其次在立意方面`.
  - 加分项 card can introduce `咱们再瞧瞧作文亮点！`, analyze `观点、结构、素材、语言等模块`, and state加分 result such as `最终给你在语言表达部分加了2分`.
  - 扣分项 card can introduce `一起来看下扣分点～`, call out `两个错别字`, and move to overall evaluation.
  - Overall card can state final scoring math: `起评分...43分，素材运用加2分，错字病句扣了1分，最终给到你44分`, then hand off to `批改报告`.

### Composition Report Intro And Generation

- Report intro/landing:
  - Use when selling or introducing the作文精批 report before generation.
  - Title bar: centered `领航甄选`, white top chrome.
  - Background uses a bright cyan/blue gradient with angled glass shapes and stacked report screenshots.
  - Hero title: `领航甄选作文 精批`; keep `精批` in a blue/purple gradient.
  - Show social proof such as `5168用户` near the top.
  - Use three floating callout chips beside the report mockup:
    - `逐句批注，精准定位`
    - `多维点评，深入解析`
    - `个性建议，针对提升`
  - Add a lower feature card titled `为什么选择领航甄选?` with three columns: `专业权威`, `深度讲解`, `持续进步`.
  - Bottom fixed primary CTA: `一键生成你的专属报告`, black gradient, 44px high, radius 12px.
- Report generation loading:
  - Title bar: `批改报告`; right icons can include help and share/open.
  - Background `#F7F8F9`.
  - Center AI icon about 128px at y around 272px.
  - Main copy: `正在为你生成专属批改报告～`, 15px MiSans Demibold gradient text.
  - Countdown example: `30s`, 14px `#0CA8E6`.
  - Progress bar about 328px by 4px, centered.
  - No bottom CTA while generating.

### Composition Report Preview

- Use when the generated report is ready.
- Page background: `#F1F5F9`.
- Top bar:
  - Title `批改报告`, centered.
  - Back icon left; right side has help and share/open icons.
- Report document:
  - Scrollable stack starts around x 8px, y 104px, width about 374px, 8px vertical gap.
  - Each report page is a rounded 4px sheet with subtle shadow `0 4px 8px #D8E2EC`.
  - Cover page height about 528px; red lower block `#B83C2E`; top pale red illustration area.
  - Cover title `作文批改报告`, large white display text; metadata rows: `学生 王小明`, `年级 高一`, `地区 北京`.
  - Directory page uses a pink/red gradient sheet with title `目录`, large translucent page numbers, and entries:
    `题目解析`, `批改笔记`, `作文详解`, `老师点评`.
  - Keep report pages visually document-like, not ordinary app cards.
- Bottom actions:
  - Fixed white blurred action area.
  - Left `重看讲解`: white button with 0.5px dark border, radius 12px.
  - Right `下载报告`: black button, radius 12px.
  - Preserve iPhone home indicator.

### Composition Report Feedback Sheet

- Use from the report page when the user taps feedback/help or needs to report quality issues.
- Dim the current report with a black overlay; keep the report visible behind the sheet.
- Bottom sheet:
  - White, full width 390px, rounded top corners 20px.
  - Height about 451px in the captured filled state; allow scrolling if content grows.
  - Title `您的反馈会让我们变得更好`, 20px Medium `#1F242E`, near x 16px.
  - Close icon: 28px circle at top-right.
- Problem-type chips:
  - Label `问题类型`, 15px `#828B94`.
  - Chips wrap with 8px gap, height about 40px, radius 10px.
  - Selected chip is white with black border and 15px Medium black text.
  - Unselected chips have `#E4E4EB` border and regular `#1F242E` text.
  - Options: `打分不准`, `讲解的不对`, `文字识别不准`, `批改时间太长`, `报告生成时间太长`, `其他`.
- Screenshot upload:
  - Label `上传截图 (选填)`.
  - Existing thumbnail about 84px by 83px, radius 8px, with a 24px delete control.
  - Add tile is 83px square, dashed border `rgba(0,0,0,0.18)`, `#F6F7F9` fill, centered image-plus icon.
- Text area:
  - Fill `#F6F7F9`, radius 16px, width about 358px, height about 84px or more.
  - Placeholder `请留下您的问题或建议`, 16px `#828B94`.
- Bottom action:
  - Fixed white action area with primary `提交`, black, 44px high, radius 12px.

### Composition Quota-Exhausted Entry State

- Use on the home `AI学习工具` card when作文批改 quota is depleted.
- Keep the normal作文练习月报 card and report summary layout intact.
- Quota badge changes to `可用 0/10`.
  - Keep the small gold badge shape and placement at the upper-right of the entry card.
  - Text remains 11px Medium, but the depleted count should be obvious.
- The `拍照批改` pill becomes disabled:
  - Fill `rgba(149,157,186,0.45)` or another muted gray-blue overlay.
  - Text stays white, 14px Medium.
  - Do not show a loading spinner or error state inside the button.
- The rest of the home page can continue to `热门推荐`; do not block the page with a modal just because quota is 0.

### Composition Correction History

- Use when the user taps `查看所有批改结果` or enters the作文 correction history.
- Page background:
  - Top gradient from `#28BEE3` to `#129CC6`, occupying roughly the first 270px.
  - Main content is a white rounded-top sheet beginning around y 212px, radius top 20px.
- Top bar:
  - Transparent/blue bar with white status icons and title `历史批改记录`, centered.
  - Back icon is white.
- Monthly summary header:
  - Left copy, white MiSans Demibold:
    - With records: `本月已完成 5 篇作文练习` and `持续保持这个节奏～`.
    - Empty: `本月还没有进行作文练习` and `快练习批改下吧～`.
  - Right badge shows `本月批改` and the count.
  - Count badge is bright blue when count is `5`; muted gray-blue when count is `0`.
- Records sheet:
  - Header row: title `批改记录`, 18px Semibold `#1F242E`.
  - Month filter pill on the right, e.g. `2026年4月`, fill `#F5F7FC`, radius 32px, 13px Medium `#4D535C`, with down chevron.
  - List width about 358px, x 16px.
  - Each row uses 20px vertical padding, bottom divider `#F1F1F1`.
  - Score block:
    - Score number 18px MiSans Demibold black plus `分` 12px Medium.
    - Category pill below, height about 18px, radius 12px.
    - Category colors:
      - `一类`: dark charcoal gradient with gold gradient text.
      - `二类`: gold gradient fill, dark brown text.
      - `三类`: warm beige gradient, dark brown text.
      - `四类`: pale cyan gradient, teal text.
      - `五类`: pale blue gradient, navy text.
  - Main row content:
    - Essay title 16px Medium black, e.g. `突破锁链，找寻自我`.
    - Subtitle 13px `#77838B`: `批改时间：4月11日 14:55`, `你的作文分析报告待领取`, or other state text.
    - Right chevron indicates drill-in.
- Locked record row:
  - Use a lock icon above a `待解锁` pill when report is not available yet.
  - Subtitle: `完成讲解即可解锁完整批改报告`.
  - Keep title active-looking, but the score/category area is replaced by the lock state.
- Empty state:
  - Keep the same gradient header and white rounded sheet.
  - Inside the sheet, show a light empty illustration about 132px by 74px, opacity 80%, centered.
  - Text `暂无批改记录`, 16px `#8E9194`, centered.
  - Keep the month filter visible; do not remove the records header.

### Composition History Month Selector

- Use when the user taps the `2026年4月` filter in history.
- Dim the current history page with a black overlay; the underlying list can remain visible.
- Bottom sheet:
  - Height about 369px, white, rounded top corners 16px.
  - Small drag handle at y about 12px.
  - Header area at x 16px, y about 28px:
    - Title `选择查看的月份`, 18px Medium `#1F242E`.
    - Subtitle `可切换不同年份，选择具体月份查看`, 12px `#828B94`.
    - Right action `全部记录`, 14px Medium `#0195F0`, with a small clock/history icon.
  - Year switch row around y 80px:
    - Center `2026年`, 18px Medium.
    - Left/right 28px circular arrow icons.
  - Month grid:
    - 4 columns, 8px gaps, x 16px, width 358px.
    - Month cells use fill `#F4F7FA`, radius 10px, padding 11px vertical.
    - Selected month, e.g. `4月`, has 1px `#0195F0` border and blue text.
    - Available unselected months use `#1F242E`; unavailable future months use `#A9B1B8`.
  - Keep iPhone home indicator in the sheet.

### Lightweight Pending Home

- Use when the home page only needs to show the greeting and pending-task card, without history plans or recommendations.
- Keep top mini-program status/capsule controls visible.
- Greeting row begins around y 85px on 390px screens.
- Pending card begins around y 145px, width about 362px, height about 302px.
- Leave the rest of the page as quiet pale background until the fixed bottom tabbar.
- Bottom tabbar may use only two entries: `学习` and `我的`.
- This variant should feel intentionally sparse, not unfinished.

### Unpurchased Or No-History Home

- Use when the user has no purchased course/plan archive yet.
- Keep the greeting row around y 85px and section title `各科历史计划` around y 150px.
- Do not show filters when there are no history records.
- Empty illustration sits centered under the section title:
  - Illustration about 132px wide by 74px high, opacity about 80%.
  - Text `暂无历史计划档案`, 16px Regular, line height 24px, `#8E9194`.
- Leave large quiet space to the bottom tabbar.
- Bottom tabbar can remain two items: `学习` and `我的`.

### Course Recommendation Grid

- Section title: `热门推荐`, 20px Semibold, `#1F242E`.
- Use a two-column grid.
- On 375px screens:
  - Left column x about 14px, right column x about 192px.
  - Card image width about 169px, height about 110px, radius 7px.
  - Row vertical rhythm: image, title, price/action; next row starts about 220px lower.
- Course cover image style:
  - Pastel subject gradient background.
  - Teacher portrait on the right.
  - Bold subject title on the left, e.g. `高考 数学`, `高考物理`, `高一化学(全年)`.
  - Small supporting copy such as `视频教辅+伴学指导` and teacher name.
  - Use subject-specific pastel backgrounds: math cyan, physics green, Chinese peach, chemistry blue-violet.
- Product title below image:
  - 15px Medium, `#292929`, two lines max, line height about 20px.
  - Pattern: `名师-高一{学科}` and `(25H2+26H1全年）...`.
- Price:
  - Red `￥799`, MiSans; currency 16px, number 20px Medium.
- Purchase action:
  - 30px circular red/orange badge, often text `抢` in white bold.
  - Place at the lower right of the product cell aligned with price.
- This grid may coexist below welcome, plan setup, or success cards; never let the fixed tabbar cover key price/action controls.

### Filters

- White background, light border, 10px radius, height 36px.
- Text 15px Regular, `#030409`.
- Use text plus 16px chevron-down.
- Typical filters: subject and year/season.
- In history sections, filter examples include:
  - Subject: `数学`, `全部`
  - Season: `2026年寒季`, `2026年春季`
- Normal position when pending card exists: below `各科历史计划`, around y 513px on 390px screens.
- When pending card is completed/absent: filters move directly below the history title, around y 181px.
- Sticky scrolled state: history title moves near y 106px and filters near y 128px; list content begins clipped beneath, implying scroll continuity.

### History Plan Card

- White card, width about 362px, radius 12px.
- Padding: 16px horizontal, 12px vertical.
- Top tags:
  - Season tag: gray-blue border, text `#34455B`.
  - Subject tag: blue border, text `#00639E`.
- Height is typically 93px to 100px depending on list density.
- Title: 16px Medium, `#030409`, 24px line height.
- Subtitle: 13px, `#828B94`, pattern `学习计划周期： 2026.01.01-2026.02.28`.
- Right action: pale gray-blue capsule `#E9EBF3`, 13px Medium, `查看计划` or `查看详情`.
- Dense completed-pending history list:
  - Use 358px width, 100px height, 10px vertical gap, padding 16px horizontal and 9px vertical.
  - Supports five or more subject cards.
  - Spring plan title pattern: `2026{学科}春季学习计划`.
  - Spring period: `2026.03.01-2026.06.30`.
  - Season tag: `2026春季`.
- If using a sticky/scrolling frame, allow the first card to be partially clipped at the top to indicate scroll position.

### Month Calendar

- Month title: `{年份}年{月份}月计划`, 18px Semibold.
- Expand action: `展开日历`, 14px Medium, black, with small down triangle.
- Collapse action in expanded state: `收起日历`, 14px Medium, black, with small up triangle.
- Month switch controls in expanded state: 24px square rounded buttons near the title, light gray fill, left/right arrow icons for previous/next month.
- Subject legend: horizontal, 12px text, 4px square dots, about 13px gap.
- Week row: `周一` to `周日`, 14px Medium, `#737C82`; total width about 350px.
- Date blocks: 7 columns, 54px high, 6px gap, 8px radius.
- Normal date: background `#EBEEF1`, number 16px Bold, `#191C1D`.
- Selected date: dark gradient, white number, dark soft shadow.
- Expanded date emphasis can use pale blue fill `rgba(204,233,251,0.7)` with border `rgba(0,99,158,0.3)` for focused days, or blue number `#0072B5` when the current scrolled state needs a lighter selection.
- Disabled/no-plan date: no or pale background, number `#A9B1B8`.
- Subject dots: 4px squares under the number, 3px gap for multiple subjects.
- Full-month expanded grid shows leading/trailing month dates when needed and normally occupies multiple rows before the task list.

### Expanded APP Calendar

- Use when the user taps `展开日历` on APP learning-plan pages.
- Keep the page background `#ECEEF5` with the daily-plan content area `#F7F8F9`; the top tabs stay fixed visually above the calendar.
- Month title and switch controls sit above the legend; the action on the right is always `收起日历`.
- Legend colors must match the subject tokens exactly: 语文 red, 数学 blue, 物理 cyan, 化学 purple, 生物 green.
- Calendar grid uses 7 columns, 54px cells, 6px gaps, and 8px radius; planned days use the subject dots under the number.
- Full expansion moves the first course task card to roughly the lower half of the screen; do not overlap task cards with the calendar.
- Scrolled expansion may clip the month title, legend, or first calendar rows above the visible content frame; this should look like scroll continuity, not a broken layout.

### Login-Required APP Plan State

- Use when the user is not logged in but enters `学习计划`.
- Preserve the top channel tabs: active `学习计划`, secondary `全部课程`.
- Preserve the fixed bottom tabbar with `学习` active; do not replace this with a full login screen.
- Contextual variant:
  - Show assistant copy `同学，登录后能查看更多计划~`.
  - Keep the month title, subject legend, weekday row, and collapsed week strip visible above the empty state.
  - Use the normal selected-date black gradient if a date is highlighted.
- Minimal variant:
  - Omit assistant bubble and calendar when the entry point should not reveal plan context.
  - Place the empty state higher, directly in the quiet content area below the top tabs.
- Empty content:
  - Illustration about 132px by 74px, opacity about 80%.
  - Text `请登录查看学习计划`, 16px Regular, line height 24px, `#8E9194`.
  - Primary button `立即登录`, about 122px by 40px, radius 9px, black gradient, 15px Medium white text.

### Course Task Card

- White card, width about 362px, height about 124px, radius 12px.
- Border: `rgba(188,200,208,0.2)`.
- Padding: about 15px.
- Top row:
  - Subject tag, e.g. math: background `#D1E5FF`, text `#2361B2`, 13px Medium, 4px radius.
  - Knowledge point: 14px Regular, `#77838B`, e.g. `考点3.1.1 导数的基本概念`.
- Main title: 16px Medium, black, e.g. `3.1.1.1 导数的概念与计算(一轮)`.
- Progress row: star/progress icon, time text, optional status tag.
- Time format: `12:30/37:01`, `00:00/37:01`, or `37:01/37:01`.
- Completed tag: `已学习`, blue border `#00639E`, text `#00639E`, height about 18px, radius 2px.
- Right action: 32px circular play button.

### Empty State

- Keep the calendar context visible.
- Center a light illustration around 200px by 112px, opacity about 80%.
- Text: `今日无计划~`, 16px Regular, line height 24px, `#8E9194`.
- Do not add a large CTA in the empty area.

### Bottom Tabbar

- Home page may use 2 items; daily plan page uses 3 items: `首页`、`学习`、`我的`.
- Icon size about 27px.
- Label size 11px.
- Active tab often uses `#FF6200`, Medium; on home recommendation pages `首页` is active.
- Inactive tabs: `#7C88B4`, Regular.
- Two-item learning home variant uses wide item slots around 175px each: `学习` active and `我的` inactive.

## Copy Patterns

- Section titles: `待办事项`, `各科历史计划`, `{年份}年{月份}月计划`, `热门推荐`, `AI学习工具`, `伴学规划建议`, `上学季学习情况回顾`, `计划学习{学科}考点（多选）`, `{月份}月学习安排`.
- Plan titles: `{年份}{学科}{季节}学习计划`, `高中{学科}-学习计划制定`, `{年级}{学科}-{季节}自主计划`, `{年级}{学科}-{季节}计划`.
- Course titles: `{章节编号} {知识点名称}`.
- APP all-courses copy: `全部课程`, `学习计划`, `知识图谱`, `模块一`, `模块二`, `模块三`, `模块四`, `上次学到`, `目标专属`.
- APP all-courses metadata: `{n}模块｜{n}专题｜{n}考点｜{n}视频`.
- Knowledge-point titles: `专题一 集合与常用逻辑用语`, `1.1.1 集合的概念`, `1.1.1.1 集合的概念与基本性质`.
- Course recommendation titles: `名师-高一{学科}`, `(25H2+26H1全年）...`.
- Buttons: `去制定`, `下一步`, `开始生成学习计划`, `去学习`, `确认`, `查看计划`, `查看详情`, `展开日历`, `收起日历`, `全选`, `一键勾选未学习`, `拍照批改`, `开始拍照`, `取消`, `暂不开启`, `去开启`, `查看示例`, `收起示例`, `去排序`, `继续补拍`, `开始识别`, `返回调整`, `开始批改`, `返回拍照`, `确认文字并批改`, `退出批改`, `确认批改`, `开始讲解`, `继续分析作文亮点`, `继续分析扣分点`, `进入作文总评`, `查看批改报告`, `一键生成你的专属报告`, `重看讲解`, `下载报告`, `提交`, `全部记录`.
- Auth/setup buttons: `获取验证码`, `立即登录`, `游客模式`, `开始使用`.
- Tags: `{年份}寒季`, `{年份}春季`, `{学科}`, `首次`, `更新`, `{年份}-寒季`, `{年份}-春季`, `已学习`.
- Hero/welcome copy: `欢迎进入领航甄选自主学习系统`, `开始定制你的学习计划吧`, `您已完成所有学习计划的制定~`, `太棒了!`.
- AI learning tool copy: `作文练习月报`, `本月已完成 5 篇作文练习`, `本月批改`, `查看所有批改结果`, `作文徽章已点亮`, `高考语文作文批改`, `随学随练，有效提升，拍照上传后即可生成批改结果。`, `可用 2/10`.
- Composition score sheet copy: `请选择本次作文满分`, `请选择作文满分，后续会按照该满分对应的高考评分规则进行批改`, `50 北京`, `60 全国/天津`, `70 上海`.
- Composition capture copy: `拍题目`, `拍作文`, `请允许访问相机`, `为正常使用批改功能，请允许领航伴学使用相机`, `第1步：拍题目`, `尽量把作文题干、材料和写作要求完整拍进去`, `第2步：拍作文 (可多张)`, `作文格通常分左、中、右三块。请一“块”一拍，每块单独一张照片。`, `题目`, `第1页`, `第2页`, `第3页`.
- Composition order/OCR/correction copy: `确认作文顺序`, `拖拽可调整图片顺序`, `请确认作文页面顺序是否正确`, `按住拖拽可调整页面顺序`, `错误的顺序会影响最终的批改结果`, `请仔细核对哦～`, `正在将作文图片识别为文字，请耐心等待～`, `核对识别文字`, `请重点检查识别错误的文字，以及漏识别的段落。修改后的文字会作为本次批改的作文内容。`, `题目识别结果`, `作文正文识别结果`, `作文标题`, `作文正文`, `确认开始批改？`, `本次批改将消耗 1 次批改次数。`, `作文批改中，请耐心等待(60s)`, `专家正在进行作文批改....`, `将按照高考作文阅卷的完整流程及标准，对作文进行批改`, `请耐心等待～`.
- Composition explanation copy: `作文讲解`, `跳过`, `你好呀同学～`, `请先确认手机系统声音已打开，点击下方 “开始讲解”按钮，听我的讲解吧~`, `咱们先看下作文的起评分～`, `首先在审题方面`, `其次在立意方面`, `咱们再瞧瞧作文亮点！`, `一起来看下扣分点～`, `最后，一起来看整体评价～`, `44分`, `三类文`.
- Composition report copy: `领航甄选作文`, `精批`, `5168用户`, `逐句批注，精准定位`, `多维点评，深入解析`, `个性建议，针对提升`, `为什么选择领航甄选?`, `专业权威`, `深度讲解`, `持续进步`, `正在为你生成专属批改报告～`, `批改报告`, `作文批改报告`, `目录`, `题目解析`, `批改笔记`, `作文详解`, `老师点评`.
- Composition history copy: `历史批改记录`, `本月已完成 5 篇作文练习`, `持续保持这个节奏～`, `本月还没有进行作文练习`, `快练习批改下吧～`, `本月批改`, `批改记录`, `2026年4月`, `一类`, `二类`, `三类`, `四类`, `五类`, `待解锁`, `完成讲解即可解锁完整批改报告`, `暂无批改记录`, `选择查看的月份`, `可切换不同年份，选择具体月份查看`.
- Composition feedback copy: `您的反馈会让我们变得更好`, `问题类型`, `打分不准`, `讲解的不对`, `文字识别不准`, `批改时间太长`, `报告生成时间太长`, `其他`, `上传截图 (选填)`, `请留下您的问题或建议`.
- Auth copy: `领航伴学`, `陪伴学习日常，助力学习跃升`, `为了同步您的课程权益，请务必使用购课时的手机号进行登录验证`, `登录即代表同意《服务条款》与《隐私政策》`.
- APP login-required copy: `同学，登录后能查看更多计划~`, `请登录查看学习计划`, `立即登录`.
- Setup copy: `开启伴学之旅`, `请完善您的基础信息，制定专属学习计划`, `当前年级`, `高考省份`.
- Plan creation copy:
  - Steps: `学习信息`, `计划考点`, `生成计划`.
  - Matched rhythm: `已匹配 2026年3~6月春季 学习节奏`.
  - Cold-season matched rhythm: `已匹配 2026年1~2月寒季 学习节奏`.
  - Selector empty: `请选择`.
  - Selector selected: `已选24个考点，79个视频`.
  - Period planning: `计划学习周期和每日课时`, `计划学习周期一`, `计划学习周期二`, `开始日期`, `结束日期`, `每日可学课时`, `＋ 添加时间段`, `删除`.
  - Loading: `正在生成学习计划`, `整合学习节奏与知识点分布，生成专属学习计划`.
  - Sync success: `计划已同步至“领航伴学APP-学习计划”`.
  - Generated overview: `这份计划聚焦4大核心模块`, `知识点总览`, `视频难度总览`.
- Full date range: `2026.01.01-2026.02.28`.
- Short season range: `1～2月`.
- Spring season range: `3～6月`.
- Course progress: `已学时长/总时长`.
- Course price: `￥799`.
- Empty history: `暂无历史计划档案`.

## Quality Checklist

- The first screen is a useful product interface, not a landing page.
- The layout clearly belongs to a 390px mobile mini-program.
- The top atmosphere, pale page background, white cards, compact tags, and fixed tabbar are present.
- Login pages use a centered brand header, glass card, pale rounded inputs, agreement row, black primary button, and secondary guest mode.
- First-use setup appears as a centered modal over a dimmed app page and contains only essential selector fields.
- Lightweight pending homes are allowed to have large quiet empty space below the pending card.
- Home recommendation pages preserve the brand header, grade selector, gradient hero card, and `热门推荐` two-column product grid.
- Home pages with AI tools place `AI学习工具` between the plan card and `热门推荐`, and keep tool cards action-oriented with visible quotas and CTAs.
- Composition full-score sheets include dimmed current-page background, three score options, disabled/enabled `开始拍照` state, and a `取消` secondary button.
- Composition capture flows use the dark camera interface, two-step `拍题目`/`拍作文` progress header, permission modal when needed, fixed shutter/gallery/flashlight controls, thumbnail strip, optional `去排序`, and example overlay states.
- Composition post-capture flows include `确认作文顺序`, draggable thumbnail order, selected-photo preview, `继续补拍`/`开始识别`, order-check modal, OCR loading, `核对识别文字`, benefit-consumption modal, and dark expert-correction loading.
- Composition explanation walkthroughs keep the annotated作文 photos inspectable, use stage-specific blue/yellow/red markings, show a narrow right commentary card, and keep the bottom audio controls fixed.
- Composition report flows include intro/landing, report-generation loading, scrollable document preview, `重看讲解`/`下载报告`, and a complete feedback sheet with chips, screenshot upload, textarea, and `提交`.
- Composition history flows include quota-exhausted entry state, gradient monthly summary header, scored record rows, `待解锁` rows, empty records, and the month selector bottom sheet.
- Learning home variants correctly reflect purchase/state logic: no-course empty history, first-time pending, update pending, completed pending, and sticky history list.
- `首次` and `更新` badges are visually distinct and use the correct gold/orange treatments.
- History cards support multiple subject tag colors, not only blue.
- Success pages use the calm blue success card with `太棒了!`, not a loud marketing celebration.
- Daily plan screens include month title, subject legend, week calendar, date dots, and task cards or empty state.
- Expanded APP calendars include month switch controls, `收起日历`, full-month 7-column grid, subject legend, date dots, and task cards pushed below the calendar.
- Scrolled expanded APP calendars can clip the month header/legend/upper rows, but the remaining visible content must still read as a continuous calendar.
- Login-required APP plan states support both contextual calendar preview and minimal empty-area variants; both keep the top channel and active `学习` bottom tab.
- Plan creation step 2 includes completed-step green checks, a taller planning advice card, suggested lesson/knowledge ranges, and a knowledge-point selector.
- 寒暑季 plan creation supports multi-period cards with placeholder dates, filled dates, removable periods, per-period hour steppers, and disabled/enabled bottom action states.
- Knowledge-point selection sheets include selected-count summary, expandable topic/subtopic groups, `全选`, star difficulty, `已学习` tags, and circular selection controls; recommendation cards and `一键勾选未学习` appear only when previous unfinished content exists.
- Generation loading screens are simple and centered, with no bottom CTA.
- Generated plan overview pages include sync success, `去学习`, knowledge-point overview metrics, difficulty distribution, and first-month calendar preview.
- APP learning-plan handoff pages preserve the daily plan tab/channel structure and active `学习` bottom tab.
- APP all-courses pages use the `全部课程` active channel, subject chips, book carousel, course summary, module tabs, left topic sidebar, right grouped video list, and active `学习` bottom tab.
- Incomplete, completed, and no-plan states are visually and textually distinct.
- Text fits within cards and does not collide with right-side buttons.
- Subject color is carried through legends, date dots, and tags.
- Course recommendation cards keep teacher/product imagery inspectable; do not blur, darken, or replace them with abstract placeholders when real covers are available.
- UI copy stays short, direct, and product-like.
