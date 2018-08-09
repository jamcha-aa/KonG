# KonG Code

KonG (混んG) Code is a simply mixed opentype fontsets of [Source Han Code JP](https://github.com/adobe-fonts/source-han-code-jp) and [Source Han Serif](https://github.com/adobe-fonts/source-han-serif). 

## KonG Code Medium

KonG Code Medium consists of Source Han Code JP Medium and Source Han Serif **Bold** Kana.

![KonG Code Medium](https://raw.githubusercontent.com/jamcha-aa/KonG/master/images/medium.png)

## KonG Code Regular

KonG Code Regular consists of Source Han Code JP Regular and Source Han Serif **Medium** Kana.

![KonG Code Regular](https://raw.githubusercontent.com/jamcha-aa/KonG/master/images/regular.png)

## Download

-   [Latest release](https://github.com/jamcha-aa/KonG/raw/master/release/KonGCode.zip)

## Procedure
Following sections describe making of KonG.

-   HKana, Kana, and VKana of Source Han Code JP are replaced to those of Source Han Serif with using [Fontforge](https://fontforge.github.io). Processed results were recorded to texts as .sfb.
    + Fontforge can not read .sfb because its size is too large.
-   Output options of Fontforge is set to default.
-   Generated otfs have a corruption of CID-tables. Therefore following CID modifications are conducted with [AFDKO](http://www.adobe.com/devnet/opentype/afdko.html).
-   Furthermore, balances of glyphs were modified for vertical presentation.

### CID modifications (Windows)
This is an example of KonGCode-Medium. Precise procedures are described at Okoneya (<https://okoneya.jp/font/knowhow.html>). Specific ttx files are included to KonG/Source/CIDFix.

1.  Install AFDKO.
2.  Copy ttx.cmd to ttxs.cmd.
    - Edit ttxs.cmd "\%AFDKO\_Python\% \%AFDKO\_SCRIPTS\%\\ttx.py \%\*" to "\%AFDKO\_Python\% \%AFDKO\_SCRIPTS\%\\ttx.py -a -s \%\*"
3.  Drag and Drop KonGCode-Medium.otf into ttxs.cmd. Many .ttx are generated.
4.  Open KonGCode-Medium.ttx
    - Edit "KonGCode-Medium.\_c\_m\_a\_p.ttx" to "SourceHanCodeJP-Medium.\_c\_m\_a\_p.ttx".
5.  Drag and Drop SourceHanCodeJP-Medium.otf into ttxs.cmd.
6.  Drag and Drop KonGCode-Medium.ttx. into ttxs.cmd. ttxs.cmd creates a CID-fixed font with the name of KonGCode-Medium\#1.otf.

### Vertical balance modifications (Windows)
This is an example of KonGCode-Medium. Precise procedures are described at Okoneya (<https://okoneya.jp/font/knowhow.html>). Specific ttx files are included to KonG/Source/VFix.

7. Remove ttx files. Rename KonGCode-Medium\#1.otf to KonGCode-Medium.otf.
8. Drag and Drop KonGCode-Medium.otf, which was generated previous section, into ttxs.cmd.
9. Download [o_vmtx-fix](https://okoneya.jp/font/knowhow.html) and extract.
10. Launch vmtx-fix.exe. Drag and Drop "KonGCode-Medium.\_v\_m\_t\_x.ttx" to it. "\_KonGCode-Medium.\_v\_m\_t\_x.ttx" is generated. Put it back to the original location.
11. Open KonGCode-Medium.ttx
    - Edit "KonGCode-Medium.\_v\_m\_t\_x.ttx" to "\_KonGCode-Medium.\_v\_m\_t\_x.ttx".
12. Drag and Drop KonGCode-Medium.ttx into ttxs.cmd.
    - ttxs.cmd generates a vertically-fixed font with the name of KonGCode-Medium\#1.otf.

## History
-   12-20-2017 Fix glyphs for vertical presentation.
-   12-19-2017 First release.

## Copyright

(c) 2017 jamcha (jamcha.aa@gmail.com)

Source Han Code JP and Source Han Serif are products of Adobe systems incorporated.

o_vmtx-fix is a product of o_tamon (https://okoneya.jp/).
## License

SIL Open Font License 1.1.
