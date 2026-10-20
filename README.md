# Category Badge Styles EVO

**Flexible category badge styling for Discourse.**

Category Badge Styles EVO is a Discourse theme component that gives administrators more control over how category badges appear throughout their community.

Choose different badge styles for main categories, subcategories, and topic lists — independently, without writing custom CSS.

Based on the original [Discourse Category Badge Styles](https://github.com/discourse/discourse-category-badge-styles) theme component.

## Features

- **Independent styling** for main categories, subcategories, and topic lists
- **Six badge styles** available for each area
- **Category-aware colors** using existing Discourse category settings
- **Light and dark theme support**
- **No custom CSS required** for configuration
- **Easy setup** through Discourse theme component settings

## Available Badge Styles

| Style | Description |
|---|---|
| **Box** | Displays the category name inside a colored badge |
| **Bar** | Displays a slim category-colored marker next to the name |
| **None** | Displays the category name without a colored marker or background |
| **Standard** | Uses the native Discourse category badge appearance |
| **Text** | Displays the category name in its assigned category color |
| **Text Auto** | Blends the category color with the active theme's text color to improve readability |

All styles use the colors configured in your Discourse category settings.

**Note:** Text Auto is designed to improve readability across light and dark themes but does not guarantee a specific accessibility contrast ratio.

## Independent Styling

Configure category badges separately in three areas.

### Main Category Badge Style

Controls the appearance of main categories in the category overview.

### Subcategory Badge Style

Controls the appearance of subcategories displayed beneath their parent categories.

### Topic List Badge Style

Controls category badges in topic lists, including Latest, New, Top, and topic lists displayed alongside categories on the homepage.

Each setting supports all six badge styles.

## Installation

1. Open your Discourse administration panel.
2. Navigate to **Appearance → Themes & Components**.
3. Select **Install**.
4. Choose **From a Git repository**.
5. Enter your Category Badge Styles EVO repository URL.
6. Install the component and add it to your active theme.

If you previously installed the original Category Badge Styles component, disable it to avoid conflicting styles.

## Configuration

After installation, open the component settings and configure the three dropdowns.

### Example Configuration

| Setting | Style |
|---|---|
| Main Category Badge Style | Box |
| Subcategory Badge Style | Standard |
| Topic List Badge Style | Bar |

This combination provides prominent main categories, familiar Discourse subcategory markers, and subtle category indicators in topic lists.

All three settings can be changed independently at any time.

## Compatibility

Category Badge Styles EVO is designed for Discourse communities using the standard category badge system.

It uses existing Discourse category colors and supports light and dark color schemes.

Compatibility may vary with custom themes or other components that modify category badges. Test the component with your community's theme before deploying it widely.

## Credits

Category Badge Styles EVO is based on the original [Category Badge Styles](https://github.com/discourse/discourse-category-badge-styles) theme component by the Discourse project.

The EVO edition was developed for [aForum – Aprilia Community](https://aforum.net), with a focus on flexible configuration and a consistent browsing experience.

Concept, configuration, and real-world testing by the aForum community administrator, with AI-assisted implementation.

Thanks to the original contributors for creating the foundation on which this component is built.

## License

This project is derived from Discourse Category Badge Styles and retains the applicable original open-source license. See the repository's `LICENSE` file for details.
