# Gutenberg Block Kategorie

Falls du deine eigene Block Kategorie haben möchtest, kannst du dies mit dieser PHP Funktion tun. 

### Standard Funktion

```php
function gutenberg_modul_category( $categories, $post ) {
    
    // Add Category 
    return array_merge(
		array(
            array(
                'slug'  => 'meineblocks',
				'title' => 'POWER + RADACH Blocks'
				'icon'  => 'wordpress'
            ),
        ),
        $categories
    );
}
add_filter( 'block_categories', 'gutenberg_modul_category', 10, 2 );
```

### Mittels JavaScript Block Kategorie aktualisieren

```jsx
import { prwp_icon } from './icon';

// Set Icon to Block Category PR Module 
wp.blocks.updateCategory('prwpblocks', { 
    icon: prwp_icon
});
```

### 

