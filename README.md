# aForum Category Badge Styles EVO v1.0.0

Fork based on the official [Discourse Category Badge Styles](https://github.com/discourse/discourse-category-badge-styles).

## Settings

- **main_category_badge_style** (default `box`): top-level badges in the category overview.
- **subcategory_badge_style** (default `none`): child-category badges in the category overview.
- **topic_list_badge_style** (default `bar`): badges in Latest, New, Top and the right-hand latest column, as well as other contexts outside the category overview.

Each setting supports `box`, `bar`, `none`. `none` retains the upstream meaning (no colored badge decoration; it does not remove the category name). Colors come from Discourse category colors and theme palette.

## Installation

Install the ZIP as a Discourse theme component, attach it to the active theme, and **disable the original Category Badge Styles component** to avoid conflicting CSS. Test both color schemes and mobile/desktop.

## Implementation notes

CSS-only, uses the modern `:has()` selector and Discourse's `--has-parent` badge class. It assumes main and child badges in the category overview appear inside `.category-list`. The topic-list setting acts as the fallback in other locations. No live Discourse browser test has been performed; check the actual DOM of your Discourse version if a category appears in an unexpected style.

## License

Original upstream copyright and Apache-2.0 license are preserved in `LICENSE`.


## v1.0.1
Fixed subcategory badge selection on category overview pages: Discourse renders these badges in `.subcategories` / `.subcategory` containers without reliably marking them `--has-parent`. The subcategory setting now applies to those containers directly.

### v1.0.2

Fix: Subcategory badge selectors no longer depend on a `.category-list` ancestor. Added explicit `none` reset for subcategory badge backgrounds.

### EVO v1.0.3

Fixes subcategory styling by targeting the actual `span.badge-category` element inside `.subcategories`, as confirmed using browser developer tools. For `None`, explicitly removes the colored background, padding and pseudo-element decorations. Also applies direct Box/Bar overrides. Main categories and topic-list settings remain independent.

## aForum EVO v1.0.4

Each of the three settings (`main_category_badge_style`,
`subcategory_badge_style`, `topic_list_badge_style`) now supports four options:

- `box`: colored badge background
- `bar`: slim category-color bar
- `none`: plain label without badge decoration
- `standard`: **native Discourse category badge**, including the colored
  square/marker before the label

`standard` is different from `none`: it leaves Discourse's built-in badge
styling in place. Category overview and subcategory selectors are isolated
from the topic-list style so a setting for one area does not override another.

Recommended aForum settings: main = `box`, subcategories = `standard`,
topic lists = `bar`.

Upgrade: replace the previous EVO component; keep the original upstream
Category Badge Styles component disabled to prevent CSS conflicts.

## aForum EVO v1.0.5

All three dropdowns now offer **five choices**:

- `box`: colored background
- `bar`: slim colored bar
- `none`: plain text in the normal interface color
- `standard`: native Discourse category badge, with the colored square in front
- `text`: **category-colored text**, without a colored box, bar or square

The `text` color is sourced from `--category-badge-color`, so it follows the
category's color as configured in Discourse. The existing defaults remain
main = box, subcategories = none, topic lists = bar.

After installing, refresh the browser (Ctrl+F5) and configure each dropdown.
Do not enable the original Category Badge Styles component at the same time.

## aForum EVO v1.0.6 — Text Auto

All three badge-style dropdowns now offer **Box**, **Bar**, **None**, **Standard**, **Text**, and **Text Auto** (`text-auto`).

**Text Auto** shows the category name without a box or bar, tinted toward its category color. To improve readability across light and dark Discourse palettes, the color is blended with the active palette's `--primary-high` foreground via CSS `color-mix()` (42% category color, 58% foreground). Older browsers fall back to `--primary-high`. This is a practical contrast-biased blend, **not a mathematical WCAG contrast guarantee** for every possible background. It does not change Discourse category colors or the other five modes.

Suggested settings: main categories **Box**, subcategories **Text Auto**, topic lists **Bar**. Test both light and dark themes after upgrading.


## aForum EVO v1.0.7 — Subcategory Standard fix

Fixes the `subcategory_badge_style: standard` option when the main category
style is `box`: subcategory chips in the category overview were inadvertently
matched by the main-category CSS selector because they don't reliably have the
`--has-parent` marker. The main selector now excludes `.subcategories`,
`.subcategory` and `.subcategories-list` descendants. `standard` leaves
Discourse's native colored-square badge intact. All other settings are kept.

Suggested verification: Main = Box, Subcategory = Standard, Topic List = Bar.
Reload the category overview, check a child category such as “Aprilia News”,
and verify that the native square marker appears rather than a filled box.
