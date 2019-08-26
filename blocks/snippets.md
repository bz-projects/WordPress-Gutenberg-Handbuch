---
description: Hier eine Snippet Sammlung für den Gutenberg Editor
---

# Snippets

### **Alle Blöcke aus dem System**

![](https://i.ibb.co/rc21kb6/getallblocks.png)

Hier werden alle Blöcke angezeigt, welche du bisher registriert hast sowie die Standardblöcke. Dies kannst du bequem über eine Zeile Code rauslesen.

```javascript
wp.data.select( 'core/blocks' ).getBlockTypes();
```

### Alle Blöcke auf der jetzigen Seite

Falls du auf der jetzigen Seite/Beitrag bist und nur von dieser Seite die verwendeten Blöcke benötigst, führe ganz einfach diese Zeile Code aus in der Console natürlich.

```javascript
wp.data.select('core/block-editor').getBlocks();
```

### Zeigt die aktuell Post Type an

Falls du im Backend auf der jetzigen Seite oder Beitrag die PostType herausfinden möchtest im Code und damit später Conditionals zu erstellen also IF\(\) ... und soweiter, kannst du dieses Snippet verwenden:

```javascript
wp.data.select('core/editor').getCurrentPostType();
```

