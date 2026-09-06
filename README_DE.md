# AnaglyphBatch 1.0

[English documentation](README.md)

AnaglyphBatch erzeugt Anaglyphen aus Side-by-Side-Stereobildern mit einer Auswahl verschiedener Verfahren zur direkten Vergleichbarkeit. Mehrfachauswahl und Batch-Verarbeitung von Dateien und Ordnern werden unterstützt.

## Voraussetzungen

- Windows

Das fertige Release-Paket enthält alle benötigten Drittprogramme im Ordner `tools` und benötigt keine zusätzliche Installation.

Das normale GitHub-Source-Repository enthält die Batch-Skripte, Dokumentation und Lizenzhinweise, aber nicht die großen Drittanbieter-Binärdateien. Die erwartete Tool-Struktur ist in [TOOLS.md](TOOLS.md) dokumentiert.

## Verwendung

1. Bilder oder Ordner auf `AnaglyphBatch_DE.bat` ziehen.
2. Ausgabegröße wählen.
3. Ein oder mehrere Verfahren auswählen.

Mehrfachauswahl ist möglich:

- Einzelwerte: `1,3,5`
- Bereiche: `1-5`
- Kombinationen: `1-5,8,10`

Für die englische Oberfläche `AnaglyphBatch_EN.bat` verwenden.

## Eingabe

- Side-by-Side Stereo, links/rechts
- Unterstützte Formate: JPG, JPEG, PNG, TIFF, BMP, WEBP

## Ausgabe

Die Ergebnisse werden im Ordner `output` gespeichert. Ordnerstrukturen werden beibehalten, und die Dateinamen enthalten das verwendete Verfahren.

Die Anaglyphen werden als finales Ausgabeformat betrachtet und deshalb effizient komprimiert in hoher Qualität gespeichert:

- JPEG Qualität 90
- ohne Chroma-Subsampling (4:4:4)

## Verfahren

1. Dubois LCD (Sanders/McAllister) + rot  
2. Dubois  
3. Optimized (Peter Wimmer)  
4. Cosima AnaglyphType=3 — Optimierter Farbraum ohne Kompromisse beim Ghosting (Gerhard P. Herbig)  
5. Cosima AnaglyphType=4 — Optimierter Farbraum mit etwas beigemischter Echtfarbe (Gerhard P. Herbig)  
6. Compromise (Jure Ahtik)  
7. iaian7 Anachrome (John Einselen)  
8. Rendepth (Andres Hernandez)  
9. Rendepth 2 (Andres Hernandez)  
10. Color  
11. Half-Color  
12. Grey  
13. Oldschool  
14. Frans van den Poel  
15. John Wattie  
16. CIELab Least Squares (David McAllister)  
17. Dubois grün/magenta (GM)  
18. Dubois amber/blau (YB)

## Hinweise

- Die Verfahren sind unterschiedlich aufgebaut und liefern je nach Bildinhalt und Betrachtungsbedingungen unterschiedliche Ergebnisse.
- CIELab unterscheidet sich algorithmisch von den anderen Verfahren und erfordert zusätzliche Berechnungsschritte, wodurch die Verarbeitung länger dauert.
- GM und YB sind für alternative Anaglyph-Brillen gedacht.

## Lizenz und Drittsoftware

Die AnaglyphBatch-Batch-Skripte und die eigene Dokumentation von Christoph Müller stehen unter der MIT-Lizenz.

Das Paket enthält außerdem unveränderte Drittsoftware:

- FFmpeg (GPL Build)
- libjpeg-turbo (`cjpeg`)
- ExifTool (Phil Harvey)
- CIELab Anaglyph Tool (mbrown1413)

Für diese Komponenten gelten weiterhin ausschließlich ihre jeweiligen eigenen Lizenzen. Die zugehörigen Lizenztexte und Hinweise befinden sich im Ordner `licenses`.

## Credits

- Andres Hernandez (Rendepth)  
  https://cybereality.com/rendepth-red-cyan-anaglyph-filter-optimized-for-stereoscopic-3d-on-lcd-monitors/
- David McAllister (Dubois LCD, CIELab Least Squares)  
  https://scispace.com/pdf/methods-for-computing-color-anaglyphs-20pz5s08er.pdf  
  https://www.david-romeuf.fr/3D/Anaglyphes/TCAnaglypheLSDubois/ei03.pdf
- Eric Dubois  
  https://www.site.uottawa.ca/~edubois/anaglyph/
- Frans van den Poel  
  https://web.archive.org/web/*/http://users.skynet.be/fa107055/AWS2/index.html
- Gerhard P. Herbig (Cosima)  
  http://www.cosima-3d.de/  
  http://www.herbig-3d.de/
- John Einselen (iaian7)  
  https://iaian7.com/photoshop/AnaglyphCompositinginPhotoshop
- John Wattie  
  https://web.archive.org/web/*/http://nzphoto.tripod.com/sterea/anaglyph_make.html  
  https://www.flickr.com/photos/kiwizone/
- Jure Ahtik (Compromise)  
  http://jpmtr.org/Advances-Vol-39(2012)_online.pdf
- Peter Wimmer (Optimized)  
  https://www.3dtv.at/Knowhow/AnaglyphComparison_en.aspx
- William Sanders (Dubois LCD)  
  https://www.david-romeuf.fr/3D/Anaglyphes/TCAnaglypheLSDubois/ei03.pdf

## Zusätzliche Software

- FFmpeg — https://ffmpeg.org/
- libjpeg-turbo — https://github.com/libjpeg-turbo/libjpeg-turbo
- ExifTool (Phil Harvey) — https://exiftool.org/
- CIELab Anaglyph Tool (mbrown1413) — https://github.com/mbrown1413/anaglyph

## Projekt und Batch-Skripte

Christoph Müller  
https://www.traumnarben.de/  
https://www.nachtexpeditionen.de/  
https://www.spiegelreich.de/
