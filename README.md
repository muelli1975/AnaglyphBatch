# AnaglyphBatch 1.0

[Deutsch](README_DE.md)

AnaglyphBatch creates anaglyph images from side-by-side stereo images using a selection of different methods for direct comparison. Multiple methods can be selected at once, and batch processing of files and folders is supported.

## Download

For normal use, download the ready-to-use Windows package from [GitHub Releases](https://github.com/muelli1975/AnaglyphBatch/releases).

The release ZIP is fully portable and contains both language versions plus all required runtime tools, including the precompiled CIELab Anaglyph Tool with its OpenCV DLLs, FFmpeg, libjpeg-turbo (`cjpeg`) and ExifTool. No compilation or additional installation is required.

## Requirements

- Windows

The normal GitHub source repository contains the batch scripts, documentation and license notices, but not the large third-party binaries. See [TOOLS.md](TOOLS.md) for the expected tool layout.

## Usage

1. Drag images or folders onto `AnaglyphBatch_EN.bat`.
2. Select the output size.
3. Select one or more anaglyph methods.

Multiple selection is possible:

- individual values: `1,3,5`
- ranges: `1-5`
- combinations: `1-5,8,10`

Use `AnaglyphBatch_DE.bat` for the German interface.

## Input

- Side-by-side stereo, left/right
- Supported formats: JPG, JPEG, PNG, TIFF, BMP, WEBP

## Output

Results are written to the `output` folder. Folder structures are preserved, and filenames include the selected method.

The anaglyphs are treated as final output and are therefore stored as efficiently compressed high-quality JPEG files:

- JPEG quality 90
- no chroma subsampling (4:4:4)

## Methods

1. Dubois LCD (Sanders/McAllister) + red  
2. Dubois  
3. Optimized (Peter Wimmer)  
4. Cosima AnaglyphType=3 — optimized color space without compromising ghosting (Gerhard P. Herbig)  
5. Cosima AnaglyphType=4 — optimized color space with some true color mixed in (Gerhard P. Herbig)  
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
17. Dubois green/magenta (GM)  
18. Dubois amber/blue (YB)

## Notes

- The methods use different approaches and can produce different results depending on image content and viewing conditions.
- CIELab differs algorithmically from the other methods and requires additional processing steps, so it takes longer.
- GM and YB are intended for alternative anaglyph glasses.

## License and third-party software

The AnaglyphBatch batch scripts and original documentation by Christoph Müller are licensed under the MIT License.

The release package also contains third-party software:

- FFmpeg (GPL build)
- libjpeg-turbo (`cjpeg`)
- ExifTool (Phil Harvey)
- CIELab Anaglyph Tool (mbrown1413)

These components remain subject to their own licenses. The corresponding license texts and notices are included in the `licenses` folder.

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

## Additional software

- FFmpeg — https://ffmpeg.org/
- libjpeg-turbo — https://github.com/libjpeg-turbo/libjpeg-turbo
- ExifTool (Phil Harvey) — https://exiftool.org/
- CIELab Anaglyph Tool (mbrown1413) — https://github.com/mbrown1413/anaglyph

## Project and batch scripts

Christoph Müller  
https://www.traumnarben.de/  
https://www.nachtexpeditionen.de/  
https://www.spiegelreich.de/
