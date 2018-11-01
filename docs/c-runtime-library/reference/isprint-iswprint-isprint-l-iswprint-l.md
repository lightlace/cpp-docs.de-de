---
title: isprint, iswprint, _isprint_l, _iswprint_l
ms.date: 11/04/2016
apiname:
- iswprint
- isprint
- _isprint_l
- _iswprint_l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- iswprint
- _istprint
- isprint
helpviewer_keywords:
- _istprint function
- iswprint function
- _iswprint_l function
- isprint_l function
- istprint function
- isprint function
- iswprint_l function
- _isprint_l function
ms.assetid: a8bbcdb0-e8d0-4d8c-ae4e-56d3bdee6ca3
ms.openlocfilehash: 826bc825824054a5a6716f8074690f18a2c3f016
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556402"
---
# <a name="isprint-iswprint-isprintl-iswprintl"></a>isprint, iswprint, _isprint_l, _iswprint_l

Bestimmt, ob eine ganze Zahl ein druckbares Zeichen darstellt.

## <a name="syntax"></a>Syntax

```C
int isprint(
   int c
);
int iswprint(
   wint_t c
);
int _isprint_l(
   int c,
   _locale_t locale
);
int _iswprint_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu testende ganze Zahl.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Jede dieser Routinen gibt ungleich NULL, wenn *c* eine bestimmte Darstellung eines druckbaren Zeichens ist. **Isprint** gibt einen Wert ungleich NULL zurück, wenn *c* ein druckbares Zeichen ist — dies schließt das Leerzeichen (0 x 20 - 0x7E). **Iswprint** gibt einen Wert ungleich NULL zurück, wenn *c* ein druckbares Breitzeichen ist – dies schließt das Leerzeichen-Breitzeichen. Jede dieser Routinen gibt 0 zurück, wenn *c* die testbedingung nicht erfüllt.

Das Ergebnis der testbedingung für diese Funktionen hängt die **LC_CTYPE** -kategorieeinstellung des Gebietsschemas, siehe [Setlocale, _wsetlocale](setlocale-wsetlocale.md) für Weitere Informationen. Die Versionen dieser Funktionen, denen keine das **_l** -Suffix verwenden das aktuelle Gebietsschema für jedes vom Gebietsschema abhängige Verhalten; die Versionen, auf denen die **_l** -Suffix sind beinahe identisch, außer dass sie verwenden die Gebietsschema, das stattdessen den übergebenen. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Das Verhalten der **Isprint** und **_isprint_l** ist undefiniert, wenn *c* nicht EOF-Markierung ist oder im Bereich von 0 bis 0xFF liegt. Wenn eine CRT-Debugbibliothek verwendet wird und *c* ist keine dieser Werte, lösen die Funktionen eine Assertion.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_unicode definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_** **Istprint**|**isprint**|[_ismbcprint](ismbcgraph-functions.md)|**iswprint**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**isprint**|\<ctype.h>|
|**iswprint**|\<ctype.h> oder \<wchar.h>|
|**_isprint_l**|\<ctype.h>|
|**_iswprint_l**|\<ctype.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenklassifizierung](../../c-runtime-library/character-classification.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
