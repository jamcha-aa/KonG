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

-   **HKana**, **Kana**, and **VKana** of Source Han Code JP are replaced to those of Source Han Serif with using [Fontforge](https://fontforge.github.io). Processed results were recorded as .sfb.
    + Fontforge can not read .sfb because its size is too large.
-   Export OTFs with Fontforge (default option).
-   Generated otfs have a corruption of CID-tables. Therefore following CID modifications are conducted with [AFDKO](http://www.adobe.com/devnet/opentype/afdko.html).
-   Furthermore, balances of glyphs were modified for vertical presentation.

### CID modifications (Windows)
This is an example of KonGCode-Medium. Precise procedures are described at Okoneya (<https://okoneya.jp/font/knowhow.html>). Specific ttx files are included to KonG/Source/CIDFix.

1.  Install AFDKO.
2.  Rename ttx.cmd as ```ttxs.cmd```.
    - Edit ```ttxs.cmd```

    ```
    --- %AFDKO_Python% %AFDKO_SCRIPTS%\ttx.py %*
    +++ %AFDKO_Python% %AFDKO_SCRIPTS%\ttx.py -a -s %*
    ```

3.  Drag and Drop KonGCode-Medium.otf and SourceHanCodeJP-Medium.otf to ```ttxs.cmd```. Wait until process finished. Many .ttx are generated.
4.  Edit ```KonGCode-Medium.ttx```

    ```
    --- KonGCode-Medium._c_m_a_p.ttx
    +++ SourceHanCodeJP-Medium._c_m_a_p.ttx
    ```

5.  Drag and Drop ```KonGCode-Medium.ttx```. to ```ttxs.cmd```. Generated KonGCode-Medium\#1.otf is a CID-fixed font.

### Vertical balance modifications (Windows)
This is an example of KonGCode-Medium. Precise procedures are described at Okoneya (<https://okoneya.jp/font/knowhow.html>). Specific ttx files are included to KonG/Source/VFix.

6. Remove .ttx files, what are generated in **3**.
7. Rename KonGCode-Medium\#1.otf to KonGCode-Medium.otf.
8. Drag and Drop KonGCode-Medium.otf (former KonGCode-Medium\#1.otf) to ```ttxs.cmd```. Wait until process finished.
9. Download [o_vmtx-fix](https://okoneya.jp/font/knowhow.html) and extract.
10. Launch vmtx-fix.exe. Drag and Drop ```KonGCode-Medium._v_m_t_x.ttx``` to it. Then ```_KonGCode-Medium._v_m_t_x.ttx``` is generated.
11. Edit ```KonGCode-Medium.ttx``` (not \_KonGCode-Medium._v_m_t_x.ttx)

    ```
    --- KonGCode-Medium._v_m_t_x.ttx
    +++ _KonGCode-Medium._v_m_t_x.ttx
    ```

12. Drag and Drop ```KonGCode-Medium.ttx``` to ```ttxs.cmd```. Generated KonGCode-Medium\#1.otf is a vertically-fixed font.

## History
-   08-09-2018 v1.01. Fix glyphs for newest Source Han Code JP (v2.0.11R).
-   12-20-2017 Fix glyphs for vertical presentation.
-   12-19-2017 Initial release.

## Copyright

(c) 2017-2018 jamcha (jamcha.aa@gmail.com)

Source Han Code JP and Source Han Serif are products of Adobe systems incorporated.

o_vmtx-fix is a product of o_tamon (https://okoneya.jp/).
## License

SIL Open Font License 1.1.
