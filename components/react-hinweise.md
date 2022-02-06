---
description: >-
  Der neue WordPress Editor basiert auf React von Facebook. Damit dir die
  Entwicklung in Gutenberg leichter fällt, solltest du diese Hinweise mal
  durchlesen.
---

# React Hinweise

### Fragment

Das Fragment ist in teilen von WordPress teilweise nicht nötig. Allerdings sobald du mehrere DIV Container sowie Elemente und Komponenten verwenden möchtest, wird man ohne das Fragment nicht herumkommen.&#x20;

Eine Methode ist nach einem TAG immer ein **`,`  ** Komma zu setzten, dann klappt es hervorragend.&#x20;

#### Gutenber**g**

In Gutenberg gibt es dafür extra ein Komponent.&#x20;

`import { Fragment } from '@wordpress/element';` &#x20;

Du musst ganz einfach den Tag `<Fragment>`  öffnen und deinen Inhalt bzw. Komponenten schreiben und dann wie in HTML wieder schließen.&#x20;

```jsx
<Fragment>
    <h2>Dein Inhalt</h2>
</Fragment>
```

#### React&#x20;

Seitens React gibt es auch eine noch einfachere Lösung. Es basiert auf der Ebene, wie bei Gutenberg allerdings ohne einen richtigen TAG Name. Hier ein Beispiel:&#x20;

**Normale Fragment Variante:**&#x20;

```jsx
   <React.Fragment>
         <h2>TestInhalt</h2>
    </React.Fragment>
```

#### Einfache Fragment Variante

```jsx
  <> //Das ist dein Fragment! 
    <h2>TestInhalt</h2>
  </>  //Fragment Ende  
```

{% hint style="info" %}
Schau dir dafür die offizielle Dokumentation von React an. \
Dort gibt es zahlreiche Anwendungsbeispiele.\
\
[Hier geht es zur Seite.](https://reactjs.org/docs/fragments.html)
{% endhint %}

### Component

Wenn du die Standard Variante von WordPress verwenden möchtest und nicht direkt das React Component, dann solltest du diese Möglichkeit verwenden.&#x20;

`import { Component } from '@wordpress/element';`
