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
