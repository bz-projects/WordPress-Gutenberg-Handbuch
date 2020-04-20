---
description: Neue Block Preview Ansicht – Beispiel Inhalte generieren in der Vorschau
---

# Block Picker Preview

![](../.gitbook/assets/bildschirmfoto-2020-04-20-um-17.31.48.png)

Seit der neuen Version von Gutenberg wurde der Gutenberg Block Picker öfters überarbeitet. Diesmal gibt es eine Block Preview, die man als Entwickler zusätzlich noch anpassen kann. Diese Funktion ist optional, allerdings empfohlen! 

Denn durch die Vorschau weiß der Redakteur direkt bescheid, was für ein Block derzeit ausgewählt wurde. 

Diese Funktion ist abhängig von deinen Attributen. Diese musst du einfach erneut innerhalb dem **example** Befehl auflisten und einen Vorschau Inhalt eingeben. Hier ein Beispiel: 

```jsx
import './style.scss';

// Import Components 
import attributes from './globals/attributes';
import edit from './globals/edit';

// WP Packages 
import { __ } from '@wordpress/i18n'; 
import { registerBlockType } from '@wordpress/blocks';

// // Add Repeater Field 
registerBlockType( 'prwp-blocks/iconpicker', {
	title: __('Icon Picker'), 
	description: 'Dies ist ein Iconpicker.',
	category: 'prwpblocks',
	icon: {
		background: '#f0dd00',
		foreground: '#222832',
		src: 'star-half',
	},
	keywords: [
		__( 'iconpicker' ),
		__( 'icon' ), 
		__( 'dashicon' )
	],
	supports: {
		html: false
	},
	attributes,
	example: {
		attributes: {
			choosedIcon: 'fas fa-check',
			iconAlign: 'center',
			iconColorHex: '#f0dd00', 
			iconFontSize: 50, 
			iconContentsToggle: true,
			iconContentHeadline: 'Hallo Welt',
			iconContentDesc: 'Lorem Ipsum dolor sit amet'
		}
	},
	edit, 
	save: ( props ) => {
		return null
	}
});
```

#### Hier zur Verdeutlichung!

```jsx
	example: {
		attributes: {
			choosedIcon: 'fas fa-check',
			iconAlign: 'center',
			iconColorHex: '#f0dd00', 
			iconFontSize: 50, 
			iconContentsToggle: true,
			iconContentHeadline: 'Hallo Welt',
			iconContentDesc: 'Lorem Ipsum dolor sit amet'
		}
	}
```

That's it! Easy und vor allem schnell erledigt. Allerdings sobald Ihr den Block auswählt, werden die Inhalte dann im Bearbeitungseditor nicht angezeigt. **Diese Inhalte sind ausschließlich für die Vorschau gedacht.** 

