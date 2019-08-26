---
description: >-
  Der neue WordPress Editor basiert auf React von Facebook. Damit dir die
  Entwicklung in Gutenberg leichter fällt, solltest du diese Hinweise mal
  durchlesen.
---

# React Hinweise

### Fragment

Das Fragment ist in teilen von WordPress teilweise nicht nötig. Allerdings sobald du mehrere DIV Container sowie Elemente und Komponenten verwenden möchtest, wird man ohne das Fragment nicht herumkommen. 

Eine Methode ist nach einem TAG immer ein **`,`**  Komma zu setzten, dann klappt es hervorragend. 

#### Gutenber**g**

In Gutenberg gibt es dafür extra ein Komponent. 

`import { Fragment } from '@wordpress/element';`  

Du musst ganz einfach den Tag `<Fragment>`  öffnen und deinen Inhalt bzw. Komponenten schreiben und dann wie in HTML wieder schließen. 

```text
<Fragment>
    <h2>Dein Inhalt</h2>
</Fragment>
```

#### React 

Seitens React gibt es auch eine noch einfachere Lösung. Es basiert auf der Ebene, wie bei Gutenberg allerdings ohne einen richtigen TAG Name. Hier ein Beispiel: 

**Normale Fragment Variante:** 

```text
   <React.Fragment>
         <h2>TestInhalt</h2>
    </React.Fragment>
```

#### Einfache Fragment Variante

```text
  <> //Das ist dein Fragment! 
    <h2>TestInhalt</h2>
  </>  //Fragment Ende  
```

{% hint style="info" %}
Schau dir dafür die offizielle Dokumentation von React an.   
Dort gibt es zahlreiche Anwendungsbeispiele.  
  
[Hier geht es zur Seite.](https://reactjs.org/docs/fragments.html)
{% endhint %}

