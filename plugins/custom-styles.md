---
description: >-
  Falls du für deinen Block mit verschiedene Styles anbieten möchtest, kannst du
  folgendes tun.
---

# Custom Styles

### Methode als Funktion

Damit ich mich im Code nicht direkt wiederholen musst, schreibe ich lieber eine Funktion und gebe ihr Parameter mit. 

| Name & Hinweise | Type |
| :--- | :--- |
| $blockname \| Gebe den Namespace von deinem Block an | String |
| $classname  \| Gebe hier die CSS Klasse, die dann mit is-style concat. wird   | String |
| $label            \| Dieses Label wird im Backend angezeigt | String |

```jsx
// Globale Funktion wird geschrieben
function StyleGutenbergRegister( $blockname , $classname, $labelname) {
    wp.blocks.registerBlockStyle( $blockname, {
        name:  $classname,  
        label: $labelname
    });
}

// Funktion wird aufgerufen und Parameter werden mitgegeben
StyleGutenbergRegister( 'prwp-blocks/featureblock', 'dotted', 'Gepunktet'); 
```

### Methode direkt im RegisterBlockType 

Falls du dies nicht als Funktion extern haben möchtest, kannst du innerhalb vom der RegisterBlockType Funktion  zum Beispiel unter den Attributen diesen Code Block einfügen. 

```jsx
styles: [
	{
		name: "prwp__bg--default",
		label: __("Hintergrund Weiß"),
		isDefault: true
	},
	{
		name: "prwp__bg--grey",
		label: __("Hintergrund Grau")
	},
	{
		name: "prwp__bg--yellow",
		label: __("Hintergrund Gelb")
	}
],
```

#### Erläuterungen 

```jsx
isDefault: true
```

Mittels diesem Befehlen kannst du einen Standard definieren und dieser wird automatisch ausgewählt. Pro Objekt Branch kannst einen CSS/HTML Klasse definieren und einen Label angeben, welcher dann im Backend angezeigt wird. 

### Style deaktivieren

Falls du einen Style entfernen möchtest, kannst du dies so tun: 

```jsx
// Erster Parameter: Namespace des Blocks mit dem Style  
// Zweiter Parameter: Style Name 

wp.blocks.unregisterBlockStyle( 'core/quote', 'large' );

// Falls React dies nicht erkennt, verwende die DomReady Funktion
wp.domReady( function() {
    wp.blocks.unregisterBlockStyle( 'core/quote', 'large' );
} );
```

Weitere besonderen Filter Methoden findest du übrigens hier:   
[**Gutenberg Handbook**](https://developer.wordpress.org/block-editor/developers/filters/block-filters/) ****

