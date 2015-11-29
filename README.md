# PDF/A Core Fonts
*Type1 core fonts for PDF/A*

* **category**    Fonts
* **author**      Nicola Asuni <info@tecnick.com>
* **license**     https://www.gnu.org/licenses/gpl-3.0.en.html GNU-GPL v3 (see LICENSE)
* **link**        https://github.com/tecnickcom/tc-font-pdfa

## Description

This project contains 14 Type 1 PDF core fonts derived from the GNU FreeFont fonts (http://www.gnu.org/software/freefont/).

The purpose of these fonts is to be able to embedd PDF Core fonts when using the PDF/A mode.

The original Unicode fonts can be downloaded from: https://ftp.gnu.org/gnu/freefont/freefont-ttf-20120503.zip

For additional information, please check the GNU FreeFont website: http://www.gnu.org/software/freefont/

## Changes

The font files were generated using the following procedure:

* Open the font using FontForge (http://fontforge.sourceforge.net/);
* From the menu select: Encoding > Reencode > Windows Latin ("ANSI") (or "Symbol" for the Symbol font, or load custom ZapfDingbats.enc);
* Select first 255 characters;
* Invert selection with: Edit > Select > Invert selection [CTRL+ESC];
* Remove glyps with: Encoding > Detach & Remove Glyphs...;
* Remove unused slots with: Encoding > Remove Unused Slots;
* Change font name with: Element > Font Info...;
* Export the file with: File > Generate fonts ... > PS Type 1 (Binary).

### Processed files
```
* FreeMono.ttf             => PDFACourier.pfb
* FreeMonoBold.ttf         => PDFACourierBold.pfb
* FreeMonoBoldOblique.ttf  => PDFACourierBoldOblique.pfb
* FreeMonoOblique.ttf      => PDFACourierOblique.pfb
* FreeSans.ttf             => PDFAHelvetica.pfb
* FreeSansBold.ttf         => PDFAHelveticaBold.pfb
* FreeSansBoldOblique.ttf  => PDFAHelveticaBoldOblique.pfb
* FreeSansOblique.ttf      => PDFAHelveticaOblique.pfb
* FreeSerif.ttf            => PDFATimes.pfb
* FreeSerifBold.ttf        => PDFATimesBold.pfb
* FreeSerifBoldItalic.ttf  => PDFATimesBoldItalic.pfb
* FreeSerifItalic.ttf      => PDFATimesItalic.pfb
* FreeSerif.ttf            => PDFASymbol.pfb
* FreeSerif.ttf            => PDFAZapfdingbats.pfb
```
