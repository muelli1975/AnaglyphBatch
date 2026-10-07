# Third-party tools

The ready-to-use AnaglyphBatch release contains the third-party tools required by the batch scripts. They are not stored in the normal GitHub source repository because some binaries are too large for a regular repository.

The existing **1.0 release ZIP** uses this layout:

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

## Updated CIELab PNG build

AnaChroma maintains a shared native PNG port of the original CIELab tool. The
CIELab math and levmar solver sources remain unchanged; the obsolete OpenCV
image front end is replaced by libpng/zlib. Precise compiler options preserve
the iterative solver’s arithmetic. The interface remains:

```sh
cielab.exe left.png right.png -o output.png
```

The Batch already supplies separate, resized RGB8 PNG halves, so neither
script requires modification. The executable itself does not resize images.

[Build updated CIELab tool](https://github.com/muelli1975/AnaglyphBatch/actions/workflows/cielab.yml) compiles the
shared source at the pinned AnaChroma commit `f809526`, compares its lossless
output with the actual executable from Batch 1.0, and tests Unicode paths and
recorded reference samples. A failed comparison stops distribution. Successful
runs provide a development `CIELab-windows-2022` artifact, retained for 14 days.
This is a separate updated tool package; the published Batch 1.0 ZIP is unchanged.

To use a successfully validated updated tool, close running Batch jobs, keep a
backup of the old `tools/cielab` directory, and extract the new `cielab` folder
into `tools`. Preserve its license files, `BUILD_INFO.json`, README and
`cielab-source.tar.gz`. The new executable does not require OpenCV DLLs.
FFmpeg, cjpeg and ExifTool remain as supplied in the Batch release.

The PNG port and corresponding sources are distributed under GPL-3.0, with
levmar (GPL-2.0-or-later), libpng and zlib retaining their license notices.
The Batch scripts remain MIT licensed. Source/build details:
https://github.com/muelli1975/AnaChroma/tree/f8095260736eee56159d66728e95c8f31c447c32/native/cielab

### Aktualisierte CIELab-Version

Der gemeinsame native PNG-Port wird im oben verlinkten Workflow aus einem
festgehaltenen AnaChroma-Quellstand gebaut. CIELab-Rechnung und levmar-Solver
bleiben unverändert; präzise Compileroptionen verhindern Abweichungen durch
Fast-Math. Der Vergleich mit der tatsächlichen CIELab-Datei aus Batch 1.0 und
weitere native Tests müssen bestehen, bevor ein Entwicklungspaket bereitsteht.

Die Batch übergibt bereits getrennte, auf Ausgabegröße skalierte RGB8-PNGs.
An den Batch-Skripten muss deshalb nichts geändert werden. Das neue Programm
skaliert selbst nicht und benötigt keine OpenCV-DLLs. Das bestehende
Release-ZIP von Batch 1.0 bleibt unverändert.

Zum Einsetzen der erfolgreich geprüften neuen Version alle Batch-Aufträge
beenden, den bisherigen Ordner `tools/cielab` sichern und den neuen Ordner
`cielab` nach `tools` entpacken. Quellenarchiv, Lizenzen, README und Build-
Informationen gehören mit dazu. FFmpeg, cjpeg und ExifTool bleiben unverändert.
