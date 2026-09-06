# Third-party tools

The ready-to-use AnaglyphBatch release contains the third-party tools required by the batch scripts. They are not stored in the normal GitHub source repository because some binaries are too large for a regular repository.

Expected layout:

```text
tools/
  ffmpeg.exe
  cjpeg.exe
  libjpeg-62.dll
  exiftool.exe
  exiftool_files/
  cielab/
    cielab.exe
    opencv_core2413.dll
    opencv_highgui2413.dll
    opencv_imgproc2413.dll
```

Sources:

- FFmpeg: https://ffmpeg.org/
- libjpeg-turbo: https://github.com/libjpeg-turbo/libjpeg-turbo
- ExifTool: https://exiftool.org/
- CIELab Anaglyph Tool: https://github.com/mbrown1413/anaglyph

The binaries bundled with the release are unmodified third-party components and remain subject to their respective licenses. The corresponding license texts and notices are included in the `licenses` folder.

---

## Deutsch

Das fertige AnaglyphBatch-Release enthält die von den Batch-Skripten benötigten Drittprogramme. Sie werden nicht im normalen GitHub-Source-Repository gespeichert, weil einzelne Binärdateien für ein reguläres Repository zu groß sind.

Die erwartete Ordnerstruktur ist oben dargestellt. Quellen und Lizenzhinweise befinden sich ebenfalls oben bzw. im Ordner `licenses`.

Die mit dem Release gebündelten Binärdateien wurden von AnaglyphBatch nicht verändert und unterliegen weiterhin ausschließlich ihren jeweiligen eigenen Lizenzen.
