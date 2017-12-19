# KonG Code

KonG (混んG) Code is a simple mixed fontsets of [Source Han Code JP](https://github.com/adobe-fonts/source-han-code-jp) and [Source Han Serif](https://github.com/adobe-fonts/source-han-serif). 

## KonG Code Medium

KonG Code Medium consists of Source Han Code JP Medium and Source Han Serif **Bold** Kana.

![KonG Code Medium](https://raw.githubusercontent.com/jamcha-aa/KonG/master/images/medium.png)

## KonG Code Regular

KonG Code Regular consists of Source Han Code JP Regular and Source Han Serif **Medium** Kana.

![KonG Code Regular](https://raw.githubusercontent.com/jamcha-aa/KonG/master/images/regular.png)

## Download

-   [Latest release](https://github.com/jamcha-aa/KonG/tree/master/release)

## Procedure

-   HKana, Kana, and VKana of Source Han Code JP are replaced to those of Source Han Serif with using [Fontforge](https://fontforge.github.io). Processed results were recorded to texts as .sfb.
    + Fontforge can not read .sfb because its size is too large.
-   Output options of Fontforge is set to default.
-   Created OTFs have a corruption of CID-tables. Therefore following CID modifications are conducted with [AFDKO](http://www.adobe.com/devnet/opentype/afdko.html).

### CID Modification (Windows)
This is an example of KonGCode-Medium. Precise procedures are described at Okoneya (<https://okoneya.jp/font/knowhow.html>).

1.  Install AFDKO.
2.  Copy ttx.cmd to ttxs.cmd.
    - Edit ttxs.cmd "\%AFDKO\_Python\% \%AFDKO\_SCRIPTS\%\\ttx.py \%\*" to "\%AFDKO\_Python\% \%AFDKO\_SCRIPTS\%\\ttx.py -a -s \%\*"
3.  Drag and Drop KonGCode-Medium.otf into ttxs.cmd. Many .ttx are created.
4.  Open KonGCode-Medium.ttx
    - Edit "KonGCode-Medium.\_c\_m\_a\_p.ttx" to "SourceHanCodeJP-Medium.\_c\_m\_a\_p.ttx".
5.  Drag and Drop SourceHanCodeJP-Medium.otf into ttxs.cmd.
6.  Drag and Drop KonGCode-Medium.ttx. into ttxs.cmd. ttxs.cmd creates a CID-fixed font with the name of KonGCode-Medium\#1.otf.

## History

-   12-19-2017 First release.

## Copyright

(c) 2017 jamcha (jamcha.aa@gmail.com)

Source Han Code JP and Source Han Serif are products of Adobe systems incorporated.

## License

SIL Open Font License 1.1.
