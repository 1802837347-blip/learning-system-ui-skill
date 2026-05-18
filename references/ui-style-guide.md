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
3. Optional history or plan section, including empty state
4. `热门推荐` course grid
5. Bottom tabbar

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
5. Week calendar
6. Task list or empty state
7. Bottom tabbar

Plan creation flow order:

1. Status bar and mini-program title bar
2. Three-step progress stepper
3. `伴学规划建议` gradient advice card
4. Learning information form: scores, target score, frequency, or period cards
5. Date picker sheet when selecting dates
6. Fixed bottom action button

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
- Advice note fill: `rgba(204,233,251,0.5)`, text `#00639E`

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
- Expand action: `展开日历`, 14px Medium, black, with small triangle.
- Subject legend: horizontal, 12px text, 4px square dots, about 13px gap.
- Week row: `周一` to `周日`, 14px Medium, `#737C82`; total width about 350px.
- Date blocks: 7 columns, 54px high, 6px gap, 8px radius.
- Normal date: background `#EBEEF1`, number 16px Bold, `#191C1D`.
- Selected date: dark gradient, white number, dark soft shadow.
- Disabled/no-plan date: no or pale background, number `#A9B1B8`.
- Subject dots: 4px squares under the number, 3px gap for multiple subjects.

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

- Section titles: `待办事项`, `各科历史计划`, `{年份}年{月份}月计划`, `热门推荐`.
- Plan titles: `{年份}{学科}{季节}学习计划`, `高中{学科}-学习计划制定`.
- Course titles: `{章节编号} {知识点名称}`.
- Course recommendation titles: `名师-高一{学科}`, `(25H2+26H1全年）...`.
- Buttons: `去制定`, `去学习`, `查看计划`, `查看详情`, `展开日历`.
- Auth/setup buttons: `获取验证码`, `立即登录`, `游客模式`, `开始使用`.
- Tags: `{年份}寒季`, `{年份}春季`, `{学科}`, `首次`, `更新`, `{年份}-寒季`, `{年份}-春季`, `已学习`.
- Hero/welcome copy: `欢迎进入领航甄选自主学习系统`, `开始定制你的学习计划吧`, `您已完成所有学习计划的制定~`, `太棒了!`.
- Auth copy: `领航伴学`, `陪伴学习日常，助力学习跃升`, `为了同步您的课程权益，请务必使用购课时的手机号进行登录验证`, `登录即代表同意《服务条款》与《隐私政策》`.
- Setup copy: `开启伴学之旅`, `请完善您的基础信息，制定专属学习计划`, `当前年级`, `高考省份`.
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
- Learning home variants correctly reflect purchase/state logic: no-course empty history, first-time pending, update pending, completed pending, and sticky history list.
- `首次` and `更新` badges are visually distinct and use the correct gold/orange treatments.
- History cards support multiple subject tag colors, not only blue.
- Success pages use the calm blue success card with `太棒了!`, not a loud marketing celebration.
- Daily plan screens include month title, subject legend, week calendar, date dots, and task cards or empty state.
- Incomplete, completed, and no-plan states are visually and textually distinct.
- Text fits within cards and does not collide with right-side buttons.
- Subject color is carried through legends, date dots, and tags.
- Course recommendation cards keep teacher/product imagery inspectable; do not blur, darken, or replace them with abstract placeholders when real covers are available.
- UI copy stays short, direct, and product-like.
