---
description: Hier findest du alles rund um das Theme Blocks
---

# Blocks

### Standard Blocks \| Namespaces

#### WordPress Standard Blöcke

Dieses Blocks sind standardmäßig immer dabei, sobald du WordPress installierst.

**Standard**

| Block | Name Space |
| :--- | :--- |
| Paragraph | core/paragraph |
| Bild | core/image |
| Überschrift | core/heading |
| Bilder Galerie | core/gallery |
| Auflistung | core/list |
| Zitat | core/quote |
| Shortcode | core/shortcode |
| Archive | core/archives |
| Audio | core/audio |
| Button | core/button |
| Kalendar | core/calendar |
| Kategorien | core/categories |
| Code | core/code |
| Spalten/Grids | core/columns |
| Spalte/Column | core/column |
| Cover | core/cover |

**Einbettungen**

| Einbettung | Name Space |
| :--- | :--- |
| Einbettung | core/embed |
| Einbettung Twitter | core-embed/twitter |
| Einbettung Youtube | core-embed/youtube |
| Einbettung Facebook | core-embed/facebook |
| Einbettung Instagram | core-embed/instagram |
| Einbettung WordPress | core-embed/wordpress |
| Einbettung Soundcloud | core-embed/soundcloud |
| Einbettung Spotify | core-embed/spotify |
| Einbettung Flickr | core-embed/flickr |
| Einbettung Vimeo | core-embed/vimeo |
| Einbettung Animoto | core-embed/animoto |
| Einbettung Cloudup | core-embed/cloudup |
| Einbettung Collegehumor | core-embed/collegehumor |
| Einbettung Crowdsignal | core-embed/crowdsignal |
| Einbettung Dailymotion | core-embed/dailymotion |
| Einbettung Hulu | core-embed/hulu |
| Einbettung Imgur | core-embed/imgur |
| Einbettung Issuu | core-embed/issuu |
| Einbettung Kickstarter | core-embed/kickstarter |
| Einbettung Meetup-com | core-embed/meetup-com |
| Einbettung Mixcloud | core-embed/mixcloud |
| Einbettung Polldaddy | core-embed/polldaddy |
| Einbettung Reddit | core-embed/reddit |
| Einbettung Reverbnation | core-embed/reverbnation |
| Einbettung Screencast | core-embed/screencast |
| Einbettung Scribd | core-embed/scribd |
| Einbettung Slideshare | core-embed/slideshare |
| Einbettung Smugmug | core-embed/smugmug |
| Einbettung Speaker | core-embed/speaker |
| Einbettung Speaker Deck | core-embed/speaker-deck |
| Einbettung Ted | core-embed/ted |
| Einbettung Tumblr | core-embed/tumblr |
| Einbettung Videopress | core-embed/videopress |
| Einbettung Wordpress TV | core-embed/wordpress-tv |
| Einbettung Amazon Kindle | core-embed/amazon-kindle |

**Weitere Core Blocks**

| Block | Name Space |
| :--- | :--- |
| Datei | core/file |
| Gruppe | core/group |
| Klassik Editor \(ehm. Editor\) | core/freeform |
| HTML | core/html |
| Media Text | core/media-text |
| Kommentare aus dem System | core/latest-comments |
| Artikel aus dem System | core/latest-posts |
| Fehlende | core/missing |
| Weitere | core/more |
| Nächste Seite | core/nextpage |
| Vorformatiert | core/preformatted |
| Zitat | core/pullquote |
| Rss | core/rss |
| Suche | core/search |
| Trenner | core/separator |
| Block | core/block |
| Trenner | core/spacer |
| Unterüberschrift | core/subhead |
| Tabelle | core/table |
| Tag Cloud | core/tag-cloud |
| Vorlagen | core/template |
| Text Spalten | core/text-columns |
| Verse | core/verse |
| Video | core/video |

#### Alle Blöcke aus dem System

![](https://i.ibb.co/rc21kb6/getallblocks.png)

Hier werden alle Blöcke angezeigt, welche du bisher registriert hast sowie die Standardblöcke. Dies kannst du bequem über eine Zeile Code rauslesen.

```text
wp.data.select( 'core/blocks' ).getBlockTypes();
```

#### Alle Blöcke auf der jetzigen Seite

Falls du auf der jetzigen Seite/Beitrag bist und nur von dieser Seite die verwendeten Blöcke benötigst, führe ganz einfach diese Zeile Code aus in der Console natürlich.

```text
wp.data.select('core/block-editor').getBlocks();
```

#### Zeigt die aktuell Post Type an

Falls du im Backend auf der jetzigen Seite oder Beitrag die PostType herausfinden möchtest im Code und damit später Conditionals zu erstellen also IF\(\) ... und soweiter, kannst du dieses Snippet verwenden:

```text
wp.data.select('core/editor').getCurrentPostType();
```

### Blocks registrieren

Damit du eigene Blöcke erstellen kannst. Must du eine Entwicklungsumgebung haben. Ich emfehle direkt die Packages von WordPress Team selber. Über NPM sowie der WP CLI kannst du bequem dir alles einrichten.

Vergess nicht beim Enque deiner JavaScript Datei alle Abhängigkeiten zu aktivieren als Array in deiner PHP.

Über JavaScript JSX geht das so:

```text
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

