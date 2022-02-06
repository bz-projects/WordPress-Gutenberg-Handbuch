---
description: >-
  Um die Daten vom Editor zu speichern, verwendet WordPress nun Redux, ein
  Framework für React. Dort sind die sogenannten "States" alles abgespeichert.
---

# Redux | React

### Browser Entwickler Tool

Falls du Gutenberg Entwickler bist, dann kann ich dir wärmstens das Chrome bzw. Firefox Plugin weiterempfehlen. Dort kannst du zugleich alle States herauslesen und manipulieren.&#x20;

![](<../.gitbook/assets/Bildschirmfoto 2019-08-26 um 13.58.11.png>)

**Hier sind die Links:** \
[Google Chrome Plugin](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en)\
[Firefox Plugin](https://addons.mozilla.org/en-US/firefox/addon/react-devtools/)

### Dispatch | Einfaches Beispiel mit wp.data

![](<../.gitbook/assets/Bildschirmfoto 2019-08-26 um 14.22.39.png>)

Das Package "**wp.data**" wird standardmäßig von Gutenberg mitgeliefert. Dort findest du viele weitere Funktionen, um die Aktionen von Gutenberg zu managen. &#x20;

#### Gutenberg Sidebar zuklappen mittels React &#x20;

Als erstes importieren wir uns die Funktion **dispatch** von dem Package "**wp.data**".

```javascript
import { dispatch } from '@wordpress/data';
```

Mit dieser Funktion können wir die **States** verändern bzw. manipulieren. &#x20;

```jsx
<Button onClick={ ( event ) => {  dispatch('core/edit-post').closeGeneralSidebar()  }   }>
    Sidebar schließen
</Button>
```

Von der Konsole aus kann man dieses Script verwenden:\
`wp.data.dispatch('core/edit-post').openGeneralSidebar();`

#### Gutenberg Sidebar aufklappen mittels React &#x20;

```jsx
<Button onClick={ ( event ) => {  dispatch('core/edit-post').openGeneralSidebar('edit-post/document')  }   }>
    Sidebar öffnen
</Button>
```

Von der Konsole aus kann man dieses Script verwenden:

`wp.data.dispatch('core/edit-post').openGeneralSidebar('edit-post/document')`

![](<../.gitbook/assets/Bildschirmfoto 2019-08-26 um 14.23.32.png>)

{% hint style="info" %}
Weitere tolle Hooks findest du hier: [https://github.com/WordPress/gutenberg/tree/master/packages/edit-post](https://github.com/WordPress/gutenberg/tree/master/packages/edit-post)
{% endhint %}

### Withstate | React State Funktion

In React wird in einem Class Component ein State Objekt geschrieben mit Zuweisungen.\
Diese dienen als Default zum Arbeiten. Beispiel: **HeadlineActive: false**&#x20;

WordPress bietet diese Funktion auch direkt im Core an und diese heißt WithState. Die Schreibweise ist etwas seltsam, aber zum effektiven Arbeiten lohnt sich dies. Ich persönlich arbeite direkt mit den internen WordPress Attributen. \
\
Diese sind in meiner Meinung nach effektiver, weil WordPress ständig Revisionen machen und alle Eingaben direkt speichert. Dies kann natürlich auf Zeit so einigen Datenmüll erzeugen. Aber dafür gibt es gute WordPress Cleaning Tools. Aber dafür freuen sich die User, falls der PC ausging oder der Browser abstürzt die geschriebenen Inhalte immer noch da sind. \
\
**Hier ein Beispiel mit WithSate:**&#x20;

```jsx
import { CheckboxControl } from '@wordpress/components';
import { withState } from '@wordpress/compose';
 
const MyCheckboxControl = withState( {
    isChecked: true,
} )( ( { isChecked, setState } ) => (
    <CheckboxControl
        heading="User"
        label="Is author"
        help="Is the user a author or not?"
        checked={ isChecked }
        onChange={ ( isChecked ) => { setState( { isChecked } ) } }
    />
) );
```
