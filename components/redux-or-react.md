---
description: >-
  Um die Daten vom Editor zu speichern, verwendet WordPress nun Redux, ein
  Framework für React. Dort sind die sogenannten "States" alles abgespeichert.
---

# Redux \| React

### Browser Entwickler Tool

Falls du Gutenberg Entwickler bist, dann kann ich dir wärmstens das Chrome bzw. Firefox Plugin weiterempfehlen. Dort kannst du zugleich alle States herauslesen und manipulieren. 

![](../.gitbook/assets/bildschirmfoto-2019-08-26-um-13.58.11.png)

**Hier sind die Links:**   
[Google Chrome Plugin](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en)  
[Firefox Plugin](https://addons.mozilla.org/en-US/firefox/addon/react-devtools/)

### Dispatch \| Einfaches Beispiel mit wp.data

![](../.gitbook/assets/bildschirmfoto-2019-08-26-um-14.22.39.png)

Das Package "**wp.data**" wird standardmäßig von Gutenberg mitgeliefert. Dort findest du viele weitere Funktionen, um die Aktionen von Gutenberg zu managen.  

#### Gutenberg Sidebar zuklappen mittels React  

Als erstes importieren wir uns die Funktion **dispatch** von dem Package "**wp.data**".

```text
import { dispatch } from '@wordpress/data';
```

Mit dieser Funktion können wir die **States** verändern bzw. manipulieren.  

```text
<Button onClick={ ( event ) => {  dispatch('core/edit-post').closeGeneralSidebar()  }   }>
    Sidebar schließen
</Button>
```

Von der Konsole aus kann man dieses Script verwenden:  
`wp.data.dispatch('core/edit-post').openGeneralSidebar();`

#### Gutenberg Sidebar aufklappen mittels React  

```text
<Button onClick={ ( event ) => {  dispatch('core/edit-post').openGeneralSidebar('edit-post/document')  }   }>
    Sidebar öffnen
</Button>
```

Von der Konsole aus kann man dieses Script verwenden:

`wp.data.dispatch('core/edit-post').openGeneralSidebar('edit-post/document')`

![](../.gitbook/assets/bildschirmfoto-2019-08-26-um-14.23.32.png)

{% hint style="info" %}
Weitere tolle Hooks findest du hier: [https://github.com/WordPress/gutenberg/tree/master/packages/edit-post](https://github.com/WordPress/gutenberg/tree/master/packages/edit-post)
{% endhint %}

