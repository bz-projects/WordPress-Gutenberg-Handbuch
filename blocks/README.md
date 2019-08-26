---
description: Hier findest du alles rund um das Theme Blocks
---

# Blocks

### Blocks registrieren

Damit du eigene Blöcke erstellen kannst. Must du eine Entwicklungsumgebung haben. Ich emfehle direkt die Packages von WordPress Team selber. Über NPM sowie der WP CLI kannst du bequem dir alles einrichten.

Vergess nicht beim Enque deiner JavaScript Datei alle Abhängigkeiten zu aktivieren als Array in deiner PHP.

Über JavaScript JSX geht das so:

```jsx
// Importiere deine Variable / Komponenten
import { __ } from '@wordpress/i18n'; 
import { registerBlockType } from '@wordpress/blocks';

registerBlockType( 'blockarchive/blockname', {
    title: __('Blockname'), 
    description: 'Block Beschreibung.',
    category: 'category',
    icon: {
        background: '#deinefarbe',
        foreground: '#deinefarbe',
        src: 'Dashicon',
    },
    keywords: [
        __( 'Suchetag 1' ),
        __( 'Suchetag 2' ), 
        __( 'Suchetag 3' )
    ],
    supports: {
        html: false, 
        align: true
    },
    attributes: {
        deineAttr: {
            type: 'string' 
        }
    }
    edit: () => {
        return(
            <h2>Mein Backend<h2>
        )
    },
    save: ( props ) => {

        return(
            <h2>Mein Frontend<h2>
        )
    }
});
```

