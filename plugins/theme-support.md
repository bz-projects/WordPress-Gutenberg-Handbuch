---
description: 'Standard Dinge, die dein Theme erfüllen sollte ...'
---

# Theme Support

Damit dein Gutenberg Theme das volle Potenzial unterstützen kann, kannst du zu deinem Theme Support folgende Einstellungen mittels PHP aktivieren. 

```php
// Delete Custom Font Sizes
add_theme_support('disable-custom-font-sizes');

// Delete Custom Colors
add_theme_support( 'disable-custom-colors' );

// Add Editor Style
add_theme_support('editor-styles');

// Add Block Style Support
add_theme_support( 'wp-block-styles' );

// Responsive Embeds (Youtube etc.)
add_theme_support( 'responsive-embeds' );

// Add Theme Support for Content Sizes -> Full etc. 
add_theme_support( 'align-wide' );

// Content Width Define
if ( ! isset( $content_width ) ) {
	$content_width = 1024;
}
```

