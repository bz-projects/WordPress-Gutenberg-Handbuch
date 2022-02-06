---
description: Hier eine kurze Anleitung bezüglich SVG Files in Gutenberg.
---

# Eigene SVG Icons

### Eigenes SVG

Falls du ein Icon in Gutenberg einbauen möchtest, ist es empfohlen dies als Funktion  abzuspeichern, um sie dann in anderen Dateien zu importieren zu können.&#x20;

Wichtig ist, dass das SVG JSV konform ist. Dafür gibt es einen tollen Generator, der wirklich das abdeckt und dir ein sauberes kompatibles SVG liefert. \
[**Hier geht es zum Generator.**](https://www.smooth-code.com/open-source/svgr/playground/)****

#### Hier ein Beispiel:&#x20;

```jsx
export function icon() {

    /* 
     *  Define inline CSS to the Icon 
     */ 
     let styles = {
         margin : '0 10px', 
         width  : '20px', 
         height : '20px'
     };
 
    /* 
     *  Return SVG Image with inline CSS
     *  SVG to JSX Compiler: https://svg2jsx.herokuapp.com
     *  Use the attribute style={styles} to return all css defin.
     */
     return (
         <svg style={styles} viewBox="0 0 24 24">
    		<Path fill="none" d="M0 0h24v24H0V0z" />
    		<G>
    			<Path d="M20 4v12H8V4h12m0-2H8L6 4v12l2 2h12l2-2V4l-2-2z" />
    			<Path d="M12 12l1 2 3-3 3 4H9z" />
    			<Path d="M2 6v14l2 2h14v-2H4V6H2z" />
    		</G>
    	</svg>
     );
 }
```

### WordPress SVG Component

Gutenberg hat schon eine interne SVG Function, die du verwenden kannst: \
Weitere Informationen findest du in der offiziellen Doku. \
\
[Hier geht es zur Doku!](https://github.com/WordPress/gutenberg/tree/master/packages/components/src/primitives/svg)

```jsx
import { G, Path, SVG } from '@wordpress/components';

const MyIcon = () => (
	<SVG
		viewBox="0 0 24 24"
		xmlns="http://www.w3.org/2000/svg"
	>
		<Path fill="none" d="M0 0h24v24H0V0z" />
		<G>
			<Path d="M20 4v12H8V4h12m0-2H8L6 4v12l2 2h12l2-2V4l-2-2z" />
			<Path d="M12 12l1 2 3-3 3 4H9z" />
			<Path d="M2 6v14l2 2h14v-2H4V6H2z" />
		</G>
	</SVG>
);
```
