# KonG Code

KonG (混んG) Code is a simple mixed fontsets of [Source Han Code JP](https://github.com/adobe-fonts/source-han-code-jp) and [Source Han Serif](https://github.com/adobe-fonts/source-han-serif). 

## KonG Code Medium

KonG Code Medium consists of Source Han Code JP Medium and Source Han Serif **Bold** Kana.

![KonG Code Medium](https://raw.githubusercontent.com/jamcha-aa/KonG/master/images/medium.png)

## KonG Code Regular

KonG Code Regular consists of Source Han Code JP Regular and Source Han Serif **Medium** Kana.

![KonG Code Regular](https://raw.githubusercontent.com/jamcha-aa/KonG/images/regular.png)

## Download

-   [Latest release](https://github.com/jamcha-aa/KonG/tree/master/release)

## Procedure

-   HKana, Kana, and VKana of Source Han Code JP are replaced to those of Source Han Serif with using [Fontforge](https://fontforge.github.io). Processed results were recorded to texts as .sfb.
-   Output options of Fontforge is set to default.
-   Created OTFs have a corruption of CID-tables. Therefore following CID modifications are conducted with using [AFDKO](http://www.adobe.com/devnet/opentype/afdko.html).

### Modification procedure (Windows)

1.  Install AFDKO.
2.  rename ttx.cmd to ttxs.cmd.
3.  Drag and Drop created font into ttxs.cmd. Many .ttx created.
4.  Open _fontname.ttx_
5.  Rename fontname.\_c\_m\_a\_p.ttx to its of Source Han Code JP.
    -   e.g.) KonG-Medium.\_c\_\_m\_a\_p.ttx to SourceHanCodeJP-Medium.\_c\_m\_a\_p.ttx
6.  Drag and Drop the correspond Source Han Code JP font ttxs.cmd. Many .ttx created.
7.  Drag and Drop fontname.ttx then it creates a CID-fixed font with \\#1.
8.  Precise procedures were described in Okoneya (<https://okoneya.jp/font/knowhow.html>).

## History

-   12-19-2017 First release.

## Copyright

(c) 2017 jamcha (jamcha.aa@gmail.com)

Source Han Code JP and Source Han Serif are products of Adobe systems incorporated.

## License

SIL Open Font License 1.1.

