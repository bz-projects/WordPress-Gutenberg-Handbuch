---
description: >-
  POWER von Gutenberg. Standard Templates mit vordefinierten Blöcken beim
  Erstellen anzeigen
---

# Templates

Falls du pro Post Type deine eigenen vordefinierten Blöcke schon beim Erstellen einfügen möchtest, kannst du dies mit den Gutenberg Templates anpassen. **Hinweis: Diese Funktion ist noch experimentell!** 

Diese Funktion wird demnächst ziemlich erweitert werden, sodass man sogar ein Vorschaubild pro Template bekommen wird. Dazu aber bald mehr. 

```php
function prwp_gutenberg_portfolio_template() {
    $postTypeTemplate = get_post_type_object('page');
    $postTypeTemplate->template = array(
        array('core/heading', array(
            content => 'Ich bin eine dynamische Überschrift!'
        )),
        array('core/paragraph', array(
            content => 'Ich bin ein dynamischer Text.'
        )),
        array('core/freeform', array(
            content => 'Text im Classic Editor'
        )), 
        array('prwp-blocks/portfolio-listing', array(
            align => 'full'
        ))
    );
}

add_action('init', 'prwp_gutenberg_portfolio_template'); ); 
```

