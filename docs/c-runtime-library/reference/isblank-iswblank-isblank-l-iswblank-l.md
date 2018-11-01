---
title: isblank, iswblank, _isblank_l, _iswblank_l
ms.date: 11/04/2016
apiname:
- isblank
- _isblank_l
- iswblank
- _iswblank_l
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
- _iswblank_l
- isblank
- _istblank_l
- _istblank
- _isblank_l
- iswblank
ms.assetid: 33ce96c0-f387-411a-8283-c3d2a69e56bd
ms.openlocfilehash: eb088c4056e2277e188d7f98a57dd36216d013ad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497317"
---
# <a name="isblank-iswblank-isblankl-iswblankl"></a>isblank, iswblank, _isblank_l, _iswblank_l

Bestimmt, ob eine ganze Zahl ein Leerzeichen darstellt.

## <a name="syntax"></a>Syntax

```C
int isblank(
   int c
);
int iswblank(
   wint_t c
);
int _isblank_l(
   int c,
   _locale_t locale
);
int _iswblank_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu testende ganze Zahl.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Jede dieser Routinen gibt ungleich NULL, wenn *c* eine bestimmte Darstellung eines Leerzeichens oder horizontales Tabstoppzeichen oder zu einem Gebietsschema-spezifische Satz von Zeichen, die zum Trennen von Wörtern in einer Textzeile verwendet werden. **Isblank** gibt einen Wert ungleich NULL zurück, wenn *c* ist ein Leerzeichen (0 x 20) oder horizontales Tabstoppzeichen (0 x 09). Das Ergebnis der testbedingung für die **Isblank** Funktionen hängt von der **LC_CTYPE** Kategorie des Gebietsschemas für Weitere Informationen finden Sie unter [Setlocale, _wsetlocale](setlocale-wsetlocale.md). Die Versionen dieser Funktionen, denen keine das **_l** -Suffix verwenden das aktuelle Gebietsschema für jedes vom Gebietsschema abhängige Verhalten; die Versionen, auf denen die **_l** -Suffix sind beinahe identisch, außer dass sie verwenden die Gebietsschema, das stattdessen den übergebenen. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

**Iswblank** gibt einen Wert ungleich NULL zurück, wenn *c* ist ein Breitzeichen ist, das einem standardleerzeichen entspricht, oder horizontales Tabstoppzeichen.

Das Verhalten der **Isblank** und **_isblank_l** ist undefiniert, wenn *c* nicht EOF-Markierung ist oder im Bereich von 0 bis 0xFF liegt. Wenn eine CRT-Debugbibliothek verwendet wird und *c* ist keine dieser Werte, lösen die Funktionen eine Assertion.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istblank**|**isblank**|[_ismbcblank](ismbcgraph-functions.md)|**iswblank**|
|**_istblank_l**|**_isblank_l**|[_ismbcblank_l](ismbcgraph-functions.md)|**_iswblank_l**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**isblank**|\<ctype.h>|
|**iswblank**|\<ctype.h> oder \<wchar.h>|
|**_isblank_l**|\<ctype.h>|
|**_iswblank_l**|\<ctype.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenklassifizierung](../../c-runtime-library/character-classification.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
