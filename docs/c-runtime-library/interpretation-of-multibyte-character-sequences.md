---
title: Interpretation von Multibytezeichensequenzen
ms.date: 10/22/2019
f1_keywords:
- c.character.multibyte
helpviewer_keywords:
- MBCS [C++], locale code page
ms.assetid: da9150de-70ea-4d2f-90e6-ddb9202dd80b
ms.openlocfilehash: 7431f0c63df60414af192ea38103318c775c430d
ms.sourcegitcommit: 0a5518fdb9d87fcc326a8507ac755936285fcb94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2019
ms.locfileid: "72811076"
---
# <a name="interpretation-of-multibyte-character-sequences"></a>Interpretation von Multibytezeichensequenzen

Die meisten Multibytezeichen-Routinen in der Microsoft-Laufzeitbibliothek erkennen Multibytezeichen-Sequenzen, die mit einer Multibytecodepage in Zusammenhang stehen. Der Ausgabewert ist von der Einstellung der **LC_CTYPE** -Kategorieeinstellung des Gebiets Schemas betroffen. Weitere Informationen finden Sie unter [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md). Die Versionen dieser Funktionen ohne das **_l** -Suffix verwenden das aktuelle Gebiets Schema für dieses vom Gebiets Schema abhängige Verhalten. Die Versionen mit dem **_l** -Suffix sind identisch, außer Sie verwenden den locale-Parameter anstelle des aktuellen Gebiets Schemas.

## <a name="locale-dependent-multibyte-routines"></a>Gebiets Schema abhängige Multibytezeichen-Routinen

|-Routine zurückgegebener Wert|Mit|
|-------------|---------|
|[_mbclen, mblen, _mblen_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|Überprüfen und Zurückgeben einer Anzahl von Bytes in Multibytezeichen|
|[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|Bei Multibyte-Zeichenfolgen: Überprüfen jedes Zeichens in der Zeichenfolge; Zurückgeben der Zeichenfolgenlänge. Für die Breitzeichen-Zeichenfolgen: Zurückgeben der Zeichenfolgenlänge.|
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Konvertieren von Multibytezeichensequenz in entsprechende Breitzeichensequenz|
|[mbtowc, _mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Konvertieren von Multibytezeichen in entsprechendes Breitzeichen|
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md), [wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Konvertieren von Breitzeichensequenz in entsprechende Multibytezeichensequenz|
|[wctomb, _wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb_s, _wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Konvertieren von Breitzeichen in entsprechendes Multibytezeichen|

## <a name="locale-independent-multibyte-routines"></a>Gebiets Schema unabhängige Multibytezeichen-Routinen

|-Routine zurückgegebener Wert|Mit|
|-------------|---------|
|[mbrtoc16, mbrtoc32](../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)|Konvertieren von Multibytezeichen-UTF-8-Zeichen in entsprechendes UTF-16-oder UTF-32-Zeichen|
|[c16rtomb, c32rtomb](../c-runtime-library/reference/c16rtomb-c32rtomb1.md)|Konvertieren von UTF-16-oder UTF-32-Zeichen in entsprechendes UTF-8-Multibytezeichen|

## <a name="see-also"></a>Siehe auch

[Internationalisierung](../c-runtime-library/internationalization.md)\
[Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)
