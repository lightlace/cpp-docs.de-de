---
title: Interpretation von Mehrbytezeichensequenzen
ms.date: 04/11/2018
f1_keywords:
- c.character.multibyte
helpviewer_keywords:
- MBCS [C++], locale code page
ms.assetid: da9150de-70ea-4d2f-90e6-ddb9202dd80b
ms.openlocfilehash: 79d053029edcb357f791dade1ec20f562dce3c16
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614990"
---
# <a name="interpretation-of-multibyte-character-sequences"></a>Interpretation von Mehrbytezeichensequenzen

Die meisten Multibytezeichen-Routinen in der Microsoft-Laufzeitbibliothek erkennen Multibytezeichen-Sequenzen, die mit einer Multibytecodepage in Zusammenhang stehen. Der Ausgabewert ist von der Kategorieeinstellung **LC_CTYPE** des Gebietsschemas betroffen. Weitere Informationen finden Sie unter [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md). Die Versionen dieser Funktionen ohne das **_l**-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem **_l**-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter.

## <a name="locale-dependent-multibyte-routines"></a>Vom Gebietsschema abhängige Multibyteroutinen

|-Routine zurückgegebener Wert|Mit|
|-------------|---------|
|[_mbclen, mblen, _mblen_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|Überprüfen und Zurückgeben einer Anzahl von Bytes in Multibytezeichen|
|[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|Bei Multibyte-Zeichenfolgen: Überprüfen jedes Zeichens in der Zeichenfolge; Zurückgeben der Zeichenfolgenlänge. Für die Breitzeichen-Zeichenfolgen: Zurückgeben der Zeichenfolgenlänge.|
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Konvertieren von Multibytezeichensequenz in entsprechende Breitzeichensequenz|
|[mbtowc, _mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Konvertieren von Multibytezeichen in entsprechendes Breitzeichen|
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md), [wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Konvertieren von Breitzeichensequenz in entsprechende Multibytezeichensequenz|
|[wctomb, _wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb_s, _wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Konvertieren von Breitzeichen in entsprechendes Multibytezeichen|
|[mbrtoc16, mbrtoc32](../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)|Konvertieren von Multibytezeichen in entsprechende UTF-16- oder UTF-32-Zeichen|
|[c16rtomb, c32rtomb](../c-runtime-library/reference/c16rtomb-c32rtomb1.md)|Konvertieren von UTF-16- oder UTF-32-Zeichen in entsprechende Multibytezeichen|

## <a name="see-also"></a>Siehe auch

[Internationalisierung](../c-runtime-library/internationalization.md)<br/>
[Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)<br/>
