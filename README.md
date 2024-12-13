# reveal.js-for-Contao5
reveal.js für Contao 5 mit einigen Plugins ergänzt. Verwendet wurde die Version 5.1.0.

Dabei wird mittels eigenem Seiten-Template, Artikel-Template und Textelement-Template gearbeitet. Das erleichert die Erstellung der Folien / Slides. (HTML Präsentation)

Für meine Webseite gebaut, kann aber für jede andere auch verwendet werden.<br>
Dazu können dann auch einige der Dateinamen anders genannt werden, die sind derzeit durch mehrere parallele Versuche so entstanden.

This is free software and can be used 'as is', for license of reveal.js please visit <a href="https://github.com/hakimel/reveal.js" target="_blank">reveal.js repository on GitHub</a> 

For questions concerning the license, installation or options of reveal.js please read <a href="https://github.com/hakimel/reveal.js" target="_blank">reveal.js repository on GitHub</a> 

## Anpassungen gegenüber Original - Theme / Font Lato

Das Theme "league", welches ich verwende, zieht einen Zeichensatz Lato von extern.

Das wurde angepasst. (wegen CSP und Datenschutz)

- geladen von https://gwfh.mranftl.com/fonts/lato?subsets=latin
- abgelegt in files/reveal/dist/theme/fonts/lato-v24-latin
- passende CSS Datei von Webseite kopiert und angelegt
- angepasst files/reveal/dist/theme/league.css 

## Plugins hinzugefügt
### Menu
- https://github.com/denehyg/reveal.js-menu
- abgelegt in files/reveal/plugin/menu

### Title-Footer, Fork mit Author und Datum
- https://github.com/skyface753/Reveal.js-Title-Footer
- abgelegt in files/reveal/plugin/title-footer

Leider nicht kompatibel mit neuerem reveal.js.<br>
Daher wurde die js Datei angepasst/umgeschrieben
- files/reveal/plugin/title-footer/title-footer.js

Ich bin kein JavaScript Programmierer, daher verzeiht mir die Code "Qualität" :-) 

## Nutzung - Theme Definitionen
- neues Theme anlegen
  - Ordner: files/reveal
  - Templates-Ordner: reveal1

- Seitenlayout darin anlegen
  - Zeilen nur Hauptzeile
  - Spalten nur Hauptspalte

  - Externe Stylesheets
    - files/reveal/dist/theme/league.css
    - files/reveal/plugin/highlight/monokai.css
    - files/css/league_ninja.css
    - jQuery laden aktiviert
    - j_reveal_1.js aktiviert
    - Seiten-Template: fe_page_reveal_1

CSS Datei league_ninja.css dient um einige CSS Definitionen zu überschreiben, der Name ist natürlich frei wählbar.<br>
Auch ein Logo wird hierüber definiert.

In der Datei j_reveal_1.js werden am Anfang die Plugins geladen.<br>
Die Initialisierung erfolgt am Ende der Datei.<br>
Dort sind auch die Definitionen für den Footer zu finden.


# Nutzung Seiten - Artikel - Text Elemente
- Seite anlegen mit angelegtem Seitenlayout
- Cache, beide auf "nicht cachen"

- Artikel anlegen mit Artikel-Template: mod_article_reveal_1 (article = slide)
- Text Element(e) anlegen mit Inhaltselement-Template: content_element/text/text_reveal_1 [Global] (text-element = subslide)

Das wird im Frontend dann automatisch durch das templates/reveal1/content_element/text/text_reveal_1.html.twig ersetzt.<br>
Das content_element/text/text_reveal_1 ist als Fallback nötig, das muss so sein.

Im TinyMCE nun normal den Inhalt eintragen. Überschrift kann genutzt werden, h2 bevorzugt. (dazu gibt es Definitionen in league_ninja.css)

Will man vertikale Folien haben (subslides), dann einfach ein zweites Text Element anlegen im Artikel. (bzw. mehrere, wieviel man halt will)
