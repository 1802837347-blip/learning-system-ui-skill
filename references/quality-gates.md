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
| 8 | Content asset fidelity | Core images such as作文 photos remain visually meaningful and inspectable | Replacing content images with abstract placeholders or repeated gray bars |
| 9 | Interaction polish | Tappable elements have feedback, disabled semantics, and stable layout bounds | No tap feedback, layout-shifting press states, or fake disabled controls |
| 10 | Accessibility basics | Meaningful controls have labels; contrast is readable; touch targets are not tiny | Icon-only controls without labels or low-contrast gray-on-gray text |

## Output Workflow

1. Build or revise the UI with normal flow layout first: flex/grid, clear gaps, `box-sizing: border-box`, and semantic sections.
2. Reserve space for fixed headers, bottom tabbars, sticky CTA bars, and the iPhone home indicator before placing scroll content.
3. Review each card from outside to inside: parent size, padding, row gaps, text wrapping, metrics, badges, action buttons.
4. Test the narrow target width first: 375px for compact pages, 390px for newer APP learning-plan pages.
5. If any required text or control is clipped, increase container space or adjust layout. Do not hide the issue with `overflow: hidden`.
6. Check interaction states: pressed, selected, disabled, loading, locked, expanded, and empty.
7. For HTML output, visually inspect the rendered page before final delivery whenever a browser is available.

## Professional UI Baseline

- Use one visual language per screen. Do not mix unrelated icon styles, shadows, gradients, or border treatments.
- Use semantic tokens from `ui-style-guide.md` before inventing new colors.
- Keep elevation consistent: cards, sheets, modals, sticky bars, and floating controls should not each use unrelated shadow styles.
- Use vector icons or existing product icons for structural controls. Do not use emoji as navigation, tabbar, toolbar, or action icons.
- Keep icon stroke width consistent within the same hierarchy, usually 1.5px to 2px.
- Use color, opacity, or shadow for press feedback; do not animate size or position in a way that shifts surrounding layout.
- Each screen should have one clear primary action. Secondary actions must be visually quieter.
- Use functional decoration only: atmosphere, gradients, and illustrations should support hierarchy or state, not compete with content.

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

- Treat作文 photos, course covers, report previews, and teacher/product images as primary content assets.
- If a real image is available, preserve it; do not redraw it as a placeholder.
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
- [ ] No card content escapes its parent boundary.
- [ ] No required text, metric, tag, button, icon, or calendar dot is clipped.
- [ ] `开始练习` and other CTAs sit inside their cards or fixed action areas.
- [ ] `强化阶段` and similar badges have clean, single-layer borders.
- [ ] 作文 image areas use a real photo or believable manuscript fallback, not repeated generic horizontal bars.
- [ ] Fixed tabbars and bottom actions do not cover scroll content.
- [ ] Touch targets are comfortable on mobile.
- [ ] Tappable elements have visible pressed/disabled/loading states without shifting layout.
- [ ] Structural icons use a consistent vector/icon style, not emoji.
- [ ] Primary and secondary text remain readable against their card or page backgrounds.
- [ ] Color is not the only way important state or meaning is communicated.
- [ ] Selected, disabled, loading, locked, completed, and error states are distinguishable.
- [ ] The page has been checked at 375px or 390px width.
- [ ] The result still matches the AI自主学习系统 visual language in `ui-style-guide.md`.
