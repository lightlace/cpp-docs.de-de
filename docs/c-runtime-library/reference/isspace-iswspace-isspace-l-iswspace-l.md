---
title: isspace, iswspace, _isspace_l, _iswspace_l
ms.date: 11/04/2016
apiname:
- iswspace
- _isspace_l
- _iswspace_l
- isspace
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- iswspace
- _istspace
- isspace
helpviewer_keywords:
- iswspace function
- isspace function
- _iswspace_l function
- _isspace_l function
- iswspace_l function
- isspace_l function
- _istspace function
- istspace function
ms.assetid: b851e0c0-36bb-4dac-a1a3-533540939035
ms.openlocfilehash: bb3d18e5034be50d69531d2686b6c270ba55a1cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157382"
---
# <a name="isspace-iswspace-isspacel-iswspacel"></a>isspace, iswspace, _isspace_l, _iswspace_l

Bestimmt, ob eine ganze Zahl ein Leerzeichen darstellt.

## <a name="syntax"></a>Syntax

```C
int isspace(
   int c
);
int iswspace(
   wint_t c
);
int _isspace_l(
   int c,
   _locale_t locale
);
int _iswspace_l(
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

Jede dieser Routinen gibt ungleich NULL, wenn *c* eine bestimmte Darstellung eines Leerzeichens ist. **Isspace** gibt einen Wert ungleich NULL zurück, wenn *c* ist ein Zeichen, Leerzeichen (0 x 09-0x0D oder 0 x 20). Das Ergebnis der testbedingung für die **Isspace** Funktion hängt von der **LC_CTYPE** -kategorieeinstellung des Gebietsschemas, siehe [Setlocale, _wsetlocale](setlocale-wsetlocale.md) für Weitere Informationen. Die Versionen dieser Funktionen, denen keine das **_l** -Suffix verwenden das aktuelle Gebietsschema für jedes vom Gebietsschema abhängige Verhalten; die Versionen, auf denen die **_l** -Suffix sind beinahe identisch, außer dass sie verwenden die Gebietsschema, das stattdessen den übergebenen. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

**Iswspace** gibt einen Wert ungleich NULL zurück, wenn *c* ein Breitzeichen ist, die eine standardmäßige Leerzeichen entspricht.

Das Verhalten der **Isspace** und **_isspace_l** ist undefiniert, wenn *c* nicht EOF-Markierung ist oder im Bereich von 0 bis 0xFF liegt. Wenn eine CRT-Debugbibliothek verwendet wird und *c* ist keine dieser Werte, lösen die Funktionen eine Assertion.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_** **istspace**|**isspace**|[_ismbcspace](ismbcgraph-functions.md)|**iswspace**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**isspace**|\<ctype.h>|
|**iswspace**|\<ctype.h> oder \<wchar.h>|
|**_isspace_l**|\<ctype.h>|
|**_iswspace_l**|\<ctype.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenklassifizierung](../../c-runtime-library/character-classification.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
