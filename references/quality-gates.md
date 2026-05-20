# AI自主学习系统 UI Quality Gates

Use this file as the final review pass before delivering optimized UI. These gates prevent common failures such as escaped buttons, clipped metrics, broken tag borders, unsafe fixed bars, and low-polish interactions.

## Priority Gates

| Priority | Gate | Must Pass | Avoid |
|---|---|---|---|
| 1 | Layout containment | Every card, sheet, modal, calendar cell, and list row contains its visible children | Buttons, badges, metrics, or icons floating outside their parent |
| 2 | Content capacity | Cards use enough `min-height`, padding, and gaps for the real text and metric rows | Tight fixed heights that crop `正确率`, time, progress, or status labels |
| 3 | Touch and fixed bars | Primary actions are easy to tap and not hidden behind tabbars, home indicator, or sticky footers | CTA bars covering scroll content or buttons too close to screen edges |
| 4 | Badge and border quality | Tags use one clean fill/border treatment with consistent radius and centered text | Double borders, offset pseudo-elements, clipped strokes, or border/text collision |
| 5 | Typography fit | Text wraps or truncates intentionally and stays readable at the target width | Accidental clipping, squeezed font sizes, broken line-height, or overlapping rows |
| 6 | State clarity | Loading, disabled, selected, completed, locked, and error states are visually distinct | Controls that look tappable when disabled, or state shown only by color |
| 7 | Product consistency | Colors, shadows, radii, icons, and spacing follow `ui-style-guide.md` | Random per-screen colors, mixed icon styles, excessive decoration |
| 8 | Content asset fidelity | Core images, source illustrations, and original icons remain visually meaningful, inspectable, and style-faithful | Replacing source assets with abstract placeholders, repeated gray bars, generic cartoons, or lower-fidelity redraws |
| 9 | Interaction polish | Tappable elements have feedback, disabled semantics, and stable layout bounds | No tap feedback, layout-shifting press states, or fake disabled controls |
| 10 | Icon completeness | Structural icons render with the right size, stroke, and alignment | Missing back, lock, expand, play, tabbar, or status icons |
| 11 | Pixel-scale normalization | Screenshot-derived UI is scaled to 375px/390px CSS width | Copying raw 2x/3x screenshot pixels into CSS sizes |
| 12 | Domain fidelity | Learning-plan pages preserve education copy, task structure, and APP navigation | CRM/work dashboard copy, office task tabs, customer communication cards |
| 13 | Chrome/navigation fidelity | Browser chrome, status icons, and back navigation match the visible source shell | Generic status bars, boxed back arrows, emoji icons, or missing domain pills |
| 14 | Gradient/module fidelity | Gradient panels and decorative learning modules keep their color, border, icon, and depth | Flattening gradient modules into plain pale rectangles |
| 15 | Step rail alignment | Timeline/step nodes, lock nodes, vertical line, and cards share a stable grid | Nodes drifting away from cards or locks not centered on the rail |
| 16 | Accessibility basics | Meaningful controls have labels; contrast is readable; touch targets are not tiny | Icon-only controls without labels or low-contrast gray-on-gray text |
| 17 | System status bar | Normal light app pages use bundled `assets/status-light.svg` at 390px by 44px or proportional width | Yellow battery pills, generic iOS bars, self-redrawn status icons, mismatched icon weights, or wrong status-bar chrome |
| 18 | Palette lock | Arbitrary screenshot colors are remapped to AI自主学习系统 cyan/blue tokens | Orange/brown/beige/peach source-color leakage into badges, borders, CTAs, cards, or tabs |
| 19 | Composition batch card completeness | Completed report cards include avatar, name, phone, report action, title, submit time, score, and category | Simplified avatar/name/phone-only cards or missing second-level report details |

## Output Workflow

1. Identify the closest page pattern from `page-patterns.md`.
2. List the components used and check their specs in `component-specs.md`.
3. Build or revise the UI with normal flow layout first: flex/grid, clear gaps, `box-sizing: border-box`, and semantic sections.
4. Reserve space for fixed headers, bottom tabbars, sticky CTA bars, and the iPhone home indicator before placing scroll content.
5. Review each card from outside to inside: parent size, padding, row gaps, text wrapping, metrics, badges, action buttons.
6. Review source visual assets before replacing them: keep screenshot/Figma illustrations, tabbar icons, decorative icons, course covers, photos, and report previews by cropping/extracting or faithfully tracing them when no better product asset is available.
7. Review color mapping: source screenshot colors must not survive unless they are explicit skill target tokens. Replace warm source colors with cyan/blue semantic tokens.
8. Test the narrow target width first: 375px for compact pages, 390px for newer APP learning-plan pages.
9. If any required text or control is clipped, increase container space or adjust layout. Do not hide the issue with `overflow: hidden`.
10. Check interaction states: pressed, selected, disabled, loading, locked, expanded, and empty.
11. For HTML output, visually inspect the rendered page before final delivery whenever a browser is available.

## Hard Failures

If any item below occurs, revise before delivery:

- Text escapes a card, button, tag, date cell, tab, modal, or fixed bar.
- A source icon is missing, replaced by emoji, or replaced by a visibly unrelated shape.
- A source illustration, tabbar icon, decorative module icon, course cover, photo, or report preview is replaced by a lower-fidelity self-drawn substitute when the original asset could have been cropped, extracted, or faithfully traced.
- A normal light app page uses a generic, mismatched, or self-redrawn status bar instead of bundled `assets/status-light.svg`.
- Orange, brown, beige, peach, amber, or warm gradients from an arbitrary source screenshot appear in a cyan/blue target page's score pills, category pills, report buttons, card detail borders, tabs, or primary CTAs.
- A `批改统计` completed-report card omits `查看报告`, `作文标题`, `提交时间`, score, or category/dang when that information exists in the source.
- A gradient panel, CTA, or selected state is flattened into a plain block when the source uses gradient/depth.
- A component listed in `component-specs.md` has obviously wrong size, radius, spacing, or state treatment.
- Course cards become schedule cards, CRM cards, or generic task cards.
- Calendar cells lose their selected/default/planned states or become a different component.
- Fixed tabbars or CTAs cover scroll content.
- The implementation changes source text, data, card count, or information order without user instruction.

## Professional UI Baseline

- Use one visual language per screen. Do not mix unrelated icon styles, shadows, gradients, or border treatments.
- Use semantic tokens from `ui-style-guide.md` before inventing new colors, and do not sample colors from arbitrary source screenshots.
- Keep elevation consistent: cards, sheets, modals, sticky bars, and floating controls should not each use unrelated shadow styles.
- Use vector icons or existing product icons for structural controls. Do not use emoji as navigation, tabbar, toolbar, or action icons.
- Keep icon stroke width consistent within the same hierarchy, usually 1.5px to 2px.
- When source material is a screenshot, estimate its scale factor and normalize to the intended mobile CSS canvas before choosing font sizes or coordinates.
- Use color, opacity, or shadow for press feedback; do not animate size or position in a way that shifts surrounding layout.
- Each screen should have one clear primary action. Secondary actions must be visually quieter.
- Use functional decoration only: atmosphere, gradients, and illustrations should support hierarchy or state, not compete with content.

## Typography Scale QA

- Do not size UI text from the raw screenshot pixel dimensions. Normalize to 375px or 390px CSS width first.
- Ordinary mobile body/list text should usually be 15px to 17px.
- Small labels, metadata, tags, and status text should usually be 12px to 15px.
- Card titles and section titles should usually be 18px to 24px.
- Large active tabs may reach 24px to 26px when the reference clearly uses display emphasis.
- Metric numbers may reach 28px to 36px. Their labels must stay much smaller.
- If every text element looks bold and oversized, the output fails even when it technically fits.

## Alignment Grid QA

- Use explicit grid/flex columns for repeated structures. Do not manually eyeball each row independently.
- In topic cards, keep the left progress rail, expand/collapse icon, dots, and vertical line on one shared x-axis.
- Row text, dividers, tags, progress numbers, and lock icons must align to stable column edges.
- Tab labels that sit on one row must share a baseline; underline should attach to the active label, not float.
- Metric summary columns must have equal widths and aligned baselines.
- Right-side values and icons should align to the same right edge across rows.

## Icon Completeness QA

- Structural icons are required content, not optional decoration.
- If the original has an icon, the output must render an equivalent: back chevron, dropdown caret, sparkle/diamond, expand/collapse circle, vertical progress dots, lock, play, status battery/wifi/cell, tabbar icons, help/share/close icons.
- Prefer the original source icon when optimizing from screenshot/Figma. Use a cropped/extracted bitmap, existing project icon, or faithful traced SVG before using a simple CSS/SVG fallback. Never leave a blank space because the asset was unavailable.
- Do not redraw source tabbar icons, expand/play buttons, or decorative module icons into a different style family unless the replacement is a clearly better product asset.
- Icon size should follow the reference scale: small inline icons around 12px to 16px, control icons around 20px to 28px, large assistant/tool icons around 40px.
- Icons must be centered within their hit areas and aligned to nearby text.

## Browser Chrome And Navigation QA

- Normal light AI自主学习系统 app pages must use the system status bar asset from `component-specs.md`: `assets/status-light.svg`, 390px by 44px.
- Do not redraw the asset's `9:41`, cellular bars, Wi-Fi, or battery when the SVG is available.
- Do not use yellow battery pills, platform-default pasted status icons, emoji/text status glyphs, or mismatched signal/Wi-Fi/battery stroke weights.
- Dark camera/correction pages may use the same status-bar geometry in white.
- If the reference shows a browser/webview chrome row, reproduce that shell: time, domain pill, ellipsis, Wi-Fi, battery, and home indicator.
- Do not replace a browser domain pill such as `uinotes.com` with a native mini-program capsule or a generic iOS status bar.
- Back controls must match the source container. A plain chevron should remain a plain chevron; do not invent a square/circle button background.
- Use vector/CSS icons for Wi-Fi, battery, ellipsis, and back. Emoji, text glyphs, or thick default browser arrows fail this gate.
- Status and navigation icons must share baseline, stroke style, and safe-area spacing; they should not look pasted in at different scales.

## Gradient Module QA

- Any target-system gradient card, intro module, recommendation banner, or CTA must preserve the skill's hue direction, border, radius, and shadow relationship. Do not preserve arbitrary source screenshot hue when it conflicts with cyan/blue target tokens.
- Do not flatten a blue/lavender intro panel into a plain light-blue rectangle.
- If a gradient module has a decorative book/card/assistant icon, include a meaningful inline SVG or asset fallback in the same corner.
- Text inside gradient modules must stay vertically centered with enough line-height and padding; it cannot touch borders or overlap decorative icons.
- Fixed CTA pills must match the skill target color family. A blue-gradient `立即购买` should not become the generic black action button, and an arbitrary source orange CTA should not override the cyan/blue palette lock.

## Step Rail QA

- Timeline and level-progress rails use one explicit grid: left rail column, right card column.
- Active number node, locked node circles, and the vertical line must share the exact same x-axis.
- Nodes should align to the vertical center or header center of their corresponding card, not to arbitrary viewport coordinates.
- Locked nodes must contain visible lock SVGs centered within the circle.
- Cards should start at a consistent x position and keep a stable gap from the rail; the rail must not overlap card content.
- When scrolling content is cropped by a fixed CTA, reserve bottom padding so the last rail node/card remains visible above the CTA.

## Domain Fidelity QA

- Keep page semantics in the AI自主学习系统 domain: learning plans, subjects, courses, knowledge points, progress,作文批改, reports, and history.
- Do not replace education copy with CRM, sales, work status, customer communication, office schedule, or generic productivity wording.
- For `学习计划-未完成`, the page must show `学习计划` / `全部课程`, assistant study reminder, month plan calendar, subject legend, course task cards, and bottom tabs `首页`、`学习`、`我的`.
- When a Figma target is provided, preserve its visible data exactly: student name, month, dates, selected day, subject legend order, task count, task titles, and progress values.
- For the `APP-学习计划-未完成` reference, the collapsed calendar is part of the `#F7F8F9` sheet, not a separate white calendar card.
- For the `APP-学习计划-未完成` reference, task cards start immediately after the week strip; there is no `今日任务`, `今日安排`, or `已完成 1/4` section header.
- Unfinished course cards should use subject tag, knowledge point, course title, star/progress indicator, time progress, and play action.
- Reject implementations that show `Hi, Sorcerer`, `Sorcerer同学`, `今日任务`, `今日安排`, `已完成 1/4`, `预计学习`, `学习中`, `未开始`, `数据看板`, `代办事项`, `工作状态`, `CRM`, `办公`, `消息`, client报价沟通, or vertical schedule bars for this learning-plan page.

## Figma Data Lock QA

- Do not improve a Figma-based optimization by inventing new content. UI polish can change surface treatment, but the source's visible strings and layout hierarchy stay fixed.
- Compare generated output against the Figma node for:
  - same top tabs and no extra controls,
  - same assistant copy length and icon treatment,
  - same year/month, date range, weekday order, selected day, and calendar dots,
  - same subject legend items and order,
  - same number of visible cards,
  - same task titles, knowledge-point text, star/progress treatment, and play action.
- If any of those change without user instruction, the output fails even if it looks polished.

## APP Learning Plan Foundation QA

- Top tab selected state must use the product's gradient text plus thick cyan rounded underline. A plain text underline or pill tab fails this page.
- Assistant area must use the 40px brand assistant avatar and compact one-line speech bubble. A text `AI` square, oversized card bubble, or invented two-line summary fails.
- Collapsed calendar must keep 54px date cells, 8px radius, 6px gaps, and the selected black-gradient cell. A separate white calendar card or stretched date tiles fails.
- Course cards must remain about 362px by 124px with metadata row, title row, star/progress row, and 32px pale circular play button. Time-slot rows or status badges fail.
- Verify foundational tokens together: page margins, colors, corner radii, cell heights, card height, and icon size should match the Figma page before judging the UI polished.

## Home Foundation QA

- Home pages must keep the white background, brand header, grade selector, one primary state card, `热门推荐`, two-column course product grid, and bottom tabbar with `首页` active.
- Do not turn 首页 into a dashboard, learning-plan calendar page, CRM page, or generic course catalog.
- Home state card must match the state:
  - 未购课 uses `HomeWelcomeGuideCard` around 347px by 196px.
  - 已购课待制定/有更新 uses `HomePendingPlanCard` around 347px by 305px.
  - 完成全部计划 uses `HomeSuccessPlanCard` around 347px by 211px.
- Recommendation product covers must stay visual and subject-specific; blank pastel cards, gray placeholders, or missing teacher/course imagery fail.
- `热门推荐` vertical position should follow the state card height; it should not overlap the main card or disappear behind the tabbar.
- Product cards must keep cover, title, price, and `抢` badge aligned in the two-column grid.

## Touch And Interaction QA

- Tappable controls should have at least a 44px by 44px hit area, even when the visible icon is smaller.
- Keep at least 8px space between adjacent touch targets.
- Buttons and cards that trigger actions need visible press feedback within about 80ms to 150ms.
- Disabled controls must use real disabled semantics when possible and lower visual emphasis; they should not respond to taps.
- Loading buttons should prevent duplicate action and show progress, spinner, or changed copy.
- Gesture-heavy regions should have one primary gesture. Avoid nested drag/tap conflicts, especially in photo sorting and calendar areas.
- Icon-only controls need meaningful labels in code output, such as `aria-label` or platform accessibility labels.

## Contrast And Readability QA

- Primary text on light surfaces should be dark enough to read comfortably; avoid pale gray body text.
- Secondary text may be muted but must remain legible on white cards and pale blue backgrounds.
- Important status colors need supporting text or icons; do not communicate meaning by color alone.
- Dividers, borders, and selected states must be visible against their surface.
- Body copy should normally stay at 12px or above in dense mobile cards, and 14px to 16px for normal reading.
- Use stable line-height. Dense card text should still have enough line box to avoid clipping Chinese characters.
- If a special font is missing, use fallback fonts without collapsing layout or hiding text.

## Palette Lock QA

- Arbitrary source screenshots are not color references. Use their content, layout, and assets, then recolor UI surfaces to the AI自主学习系统 token palette.
- The default page mood is cool: pale cyan atmosphere, white cards, blue/cyan selected states, blue gradient CTAs, blue outlined secondary actions, and gray-blue muted text.
- Warm source colors fail unless explicitly required by the target page spec: orange score pills, peach card borders, beige category tags, brown labels, orange report buttons, and warm card glows should be remapped.
- Recommended remaps:
  - Primary warm action -> blue gradient `#00B3E8` to `#0288FF` or subject blue `#00639E`.
  - Warm score pill -> solid cyan/blue `#00A7D8` or pale blue `#CCE9FB` with blue text.
  - Peach detail border -> `rgba(0,167,216,0.18)` or `#CCE9FB`.
  - Beige category tag -> pale blue/gray fill with `#00639E` or `#071D39` text.
- Decorative warm icon/illustration fills -> cyan/blue tokens such as `#00639E`, `#00A7D8`, `#0EC5FF`, `#BFF9FF`, `#CCE9FB`, or gray-blue neutrals.
- Scan CSS/HTML for warm literals such as `#F97316`, `#FF8`, `#FF9`, `#F59`, `orange`, `amber`, `peach`, `brown`, `beige`, `tan`, and replace them unless they correspond to an explicit allowed token.

## Composition Batch Statistics QA

- Use this for `批改统计`, 作文批改历史, report-list, and batch-correction management pages.
- Each completed report card must include, when present in the source: avatar, user name, phone number, `查看报告`, `作文标题`, `提交时间`, score, and category/dang.
- Card hierarchy must be preserved:
  - First level: avatar, user information, and report action.
  - Second level: title/time detail panel plus score/category result row.
- Names should be list-card scale, usually 16px to 18px, and phone/detail text should be 13px to 15px. Oversized profile-card typography fails.
- The active tab should not be taller than needed; segmented controls should be compact and not consume excessive vertical space.
- Page background gradients should continue naturally to the page bottom or into the content sheet; they must not visibly stop at the tab bar boundary.
- Default avatars must come from provided/bundled assets when available; do not create decorative profile art that changes the product style.

## Composition Score Snapshot QA

- Use this for single作文数据展示页, score/rank summary pages, category result pages, no-value score states, and locked score/category states.
- The primary card must be immersive: left side title/data/copy, right side medal/rank asset.
- Use `assets/composition/badge-valued.svg` for valued medal states and `assets/composition/badge-empty.svg` for no-value medal states.
- Use `assets/composition/tag-rank-1.svg` through `tag-rank-5.svg` for `一类` through `五类`; use `assets/composition/tag-locked.svg` for `待解锁`.
- Use `assets/composition/empty-no-content.svg` for no-content fallbacks.
- Surrounding UI must remain cyan/blue; warm rank asset colors are allowed only inside the bundled SVG assets.
- Fail if the page replaces the medal/rank assets with emoji, generic trophies, CSS pills, or newly drawn badges.

## Composition Essay Record List QA

- Use this for作文列表, 作文批改列表, 历史作文记录, and repeated essay records where rows contain score/category plus title/time.
- Each list item must use the hierarchy: left score plus rank/locked asset, right title plus time.
- Score/rank must not move to the right side, and title/time must not move below avatar/name structures unless the source includes avatars.
- Use the rank SVG assets for `一类` to `五类` and `待解锁`; do not recreate them as text pills.
- Preserve every visible score, title, category, and time from the source.
- Empty list uses `empty-no-content.svg`.

## Composition Correction History Records QA

- Use this for `历史批改记录` and monthly correction history pages matching the exported target references.
- Header must be a full cyan/teal gradient with white status bar `assets/status-white.svg`, white back chevron, and centered `历史批改记录`.
- White sheet must start around y 212px with 20px top corner radius. It must not be a floating card.
- With-records state must show monthly copy, `badge-valued.svg`, `批改记录`, month filter, row dividers, score/rank left column, title/time right column, and chevrons.
- Empty state must keep the same header and sheet header/month filter, then show `empty-no-content.svg` and `暂无批改记录` centered in the sheet.
- Fail if avatars/phone/report buttons from other report-list patterns appear on this page.

## Responsive And Safe-Area QA

- Verify phone-width output at 375px and 390px. For HTML previews, no horizontal scroll should appear.
- Fixed headers, bottom tabbars, and sticky CTA bars must reserve content padding so scroll content is not hidden underneath.
- Respect the status bar, mini-program capsule area, and iPhone home indicator in visual mockups.
- Do not use viewport-height assumptions that break on mobile browser chrome; prefer content-driven height or `min-height`.
- Calendar grids, course lists, and photo panels should adapt with fixed internal proportions rather than squeezing text.
- Landscape or wider previews may add side gutters, but the core phone layout should remain centered and readable.

## Card QA

- Card children must stay inside the card padding box.
- Use `min-height` when a card has more than one content row, stats, tags, or a CTA.
- Use `display: flex` or `display: grid` for title/metric/action arrangements.
- Do not position `开始练习`, `去学习`, `查看详情`, or orange CTA pills outside normal card flow.
- Right-side actions need a reserved column width; left text should wrap before colliding with the action.
- Metric rows need at least 18px to 20px line box plus vertical breathing room.
- If text is two lines in the source or likely to wrap in Chinese, design for the wrapped state from the start.
- Use `overflow: hidden` only for images or decorative masks, not for text-heavy cards.

## Badge QA

- Stage tags such as `强化阶段` should use one border, one radius, and one fill strategy.
- Use `box-sizing: border-box` so the badge border does not enlarge the measured size.
- Keep at least 4px vertical padding and 8px horizontal padding inside small badges.
- Border radius must match the badge height; all corners should render evenly.
- Avoid pseudo-element borders unless they are required for a special effect and have been visually checked.
- If a badge sits in a row with text, align it to the text baseline or centerline; do not let it float upward/downward.

## Image And Manuscript QA

- Treat作文 photos, course covers, report previews, teacher/product images, source illustrations, tabbar icons, decorative module icons, and status/action icons as primary content assets.
- If a real image or source icon/illustration is available, preserve it; do not redraw it as a placeholder or a simplified substitute.
- Asset replacement priority is: source-cropped/extracted bitmap, existing bundled product asset, faithful traced SVG/vector, then neutral placeholder only when the source asset is absent or unusable.
- When extracting from a screenshot, preserve the asset's proportions, opacity, geometry, softness, and visual weight. Cropping and light cleanup are allowed; changing the icon or illustration style family is not.
- For decorative UI icons/illustrations, source geometry is locked but source warm palette is not. Recolor orange/peach/brown/beige fills and strokes into cyan/blue tokens unless the asset is real content media such as a course cover, photo, manuscript, or report preview.
- If no real作文 image is available, create a believable manuscript fallback: grid paper, varied handwritten Chinese strokes, red score marks, colored underlines, correction circles, and numbered annotation dots.
- A fallback essay manuscript must contain visual texture and sentence-like writing density. Repeated gray bars alone are a failed output.
- Keep annotated lines aligned to plausible manuscript rows; annotations should look attached to the essay, not floating over an empty skeleton.
- Do not blur, darken, or crop the作文 image so aggressively that handwriting and teacher marks are no longer inspectable.
- Promotional pages can simplify the manuscript, but they still need to communicate "this is a corrected handwritten essay photo" at first glance.

## HTML/CSS Guardrails

```css
*, *::before, *::after {
  box-sizing: border-box;
}

.card {
  display: flex;
  flex-direction: column;
  min-height: var(--card-min-height);
  overflow: visible;
}

.card-row {
  display: flex;
  align-items: center;
  gap: 8px;
  min-width: 0;
}

.card-title,
.card-meta {
  min-width: 0;
}

.card-action {
  flex: 0 0 auto;
}
```

Use this pattern as a starting point, then adapt dimensions to the exact component in `ui-style-guide.md`.

## Pre-Delivery Checklist

- [ ] The screen still uses the requested original copy and layout hierarchy unless the user asked to change them.
- [ ] The closest page pattern from `page-patterns.md` was selected.
- [ ] All repeated components were checked against `component-specs.md`.
- [ ] No card content escapes its parent boundary.
- [ ] No required text, metric, tag, button, icon, or calendar dot is clipped.
- [ ] `开始练习` and other CTAs sit inside their cards or fixed action areas.
- [ ] `强化阶段` and similar badges have clean, single-layer borders.
- [ ] 作文 image areas use a real photo or believable manuscript fallback, not repeated generic horizontal bars.
- [ ] Fixed tabbars and bottom actions do not cover scroll content.
- [ ] Touch targets are comfortable on mobile.
- [ ] Tappable elements have visible pressed/disabled/loading states without shifting layout.
- [ ] Structural icons use a consistent vector/icon style, not emoji.
- [ ] All source icons are represented by real SVG/icon/CSS fallbacks; none are silently missing.
- [ ] Browser/webview chrome is preserved when present, including domain pill and status controls.
- [ ] Normal light app pages use bundled `assets/status-light.svg` for the AI自主学习系统 status bar.
- [ ] Composition score/rank pages use bundled medal, rank, locked, and empty-state SVG assets from `assets/composition/`.
- [ ] Single作文数据展示页 uses left title/data and right medal/rank asset inside an immersive card.
- [ ] 作文列表 rows use left score plus rank/locked asset and right title plus time.
- [ ] Back chevron shape and container match the source; no invented boxed button.
- [ ] Font sizes are normalized to a 375px/390px CSS canvas and are not inflated from screenshot pixels.
- [ ] Repeated rows use stable alignment columns for left rail, content, tags, progress, and lock/play icons.
- [ ] Gradient modules preserve the target system gradient, border, shadow, and decorative icon without inheriting arbitrary source hues.
- [ ] Step/timeline rail nodes share one x-axis and align to their corresponding cards.
- [ ] Primary and secondary text remain readable against their card or page backgrounds.
- [ ] Color is not the only way important state or meaning is communicated.
- [ ] Arbitrary source screenshot colors were not inherited; all UI colors come from AI自主学习系统 tokens and the page remains cyan/blue dominant.
- [ ] No warm source-color leakage remains in score pills, category tags, card borders, report buttons, tabs, or primary CTAs.
- [ ] `批改统计` cards keep the required two-level hierarchy and include report action, title/time, score, and category when those fields exist.
- [ ] Management-list typography stays compact and does not turn names/phone numbers into oversized profile-card text.
- [ ] Page/background gradient continues naturally behind content and is not visibly cut off at the tabbar.
- [ ] Learning-plan screens do not drift into CRM/work schedule semantics or unrelated tab labels.
- [ ] Selected, disabled, loading, locked, completed, and error states are distinguishable.
- [ ] The page has been checked at 375px or 390px width.
- [ ] The result still matches the AI自主学习系统 visual language in `ui-style-guide.md`.
