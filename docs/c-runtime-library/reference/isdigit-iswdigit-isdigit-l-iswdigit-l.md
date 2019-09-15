---
title: isdigit, iswdigit, _isdigit_l, _iswdigit_l
ms.date: 11/04/2016
api_name:
- _isdigit_l
- iswdigit
- _iswdigit_l
- isdigit
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _iswdigit_l
- _isdigit_l
- iswdigit
- isdigit
- _istdigit
- _istdigit_l
helpviewer_keywords:
- iswdigit function
- iswdigit_l function
- _iswdigit_l function
- _istdigit_l function
- _istdigit function
- istdigit function
- isdigit function
- isdigit_l function
- _ismbcdigit_l function
- _isdigit_l function
ms.assetid: 350b0093-843a-47b0-954e-c1776e8a3853
ms.openlocfilehash: 30944db0653e26b6130fb7a37ad87e8e81a343f5
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954389"
---
# <a name="isdigit-iswdigit-_isdigit_l-_iswdigit_l"></a>isdigit, iswdigit, _isdigit_l, _iswdigit_l

Bestimmt, ob eine ganze Zahl ein Dezimalstellenzeichen darstellt.

## <a name="syntax"></a>Syntax

```C
int isdigit(
   int c
);
int iswdigit(
   wint_t c
);
int _isdigit_l(
   int c,
   _locale_t locale
);
int _iswdigit_l(
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

Jede dieser Routinen gibt einen Wert ungleich 0 (null) zurück, wenn *c* eine bestimmte Darstellung eines Dezimalstellen Zeichens ist. **IsDigit** gibt einen Wert ungleich 0 (null) zurück, wenn *c* eine Dezimal Ziffer (0-9) ist. **iswdigit** gibt einen Wert ungleich 0 (null) zurück, wenn *c* ein breit Zeichen ist, das einem Dezimaltrennzeichen entspricht. Jede dieser Routinen gibt 0 zurück, wenn *c* die Test Bedingung nicht erfüllt.

Die Versionen dieser Funktionen mit dem **_l** -Suffix verwenden das übergebene Gebiets Schema anstelle des aktuellen Gebiets Schemas für Ihr vom Gebiets Schema abhängiges Verhalten. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Das Verhalten von **IsDigit** und **_isdigit_l** ist nicht definiert, wenn *c* nicht EOF ist oder im Bereich von 0 bis 0xFF (einschließlich) liegt. Wenn eine Debug-CRT-Bibliothek verwendet wird und *c* keiner dieser Werte ist, wird von den Funktionen eine-Assertion erhoben.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istdigit**|**isdigit**|[_ismbcdigit](ismbcalnum-functions.md)|**iswdigit**|
|**_istdigit_l**|**_isdigit_l**|[_ismbcdigit_l](ismbcalnum-functions.md)|**_iswdigit_l**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**isdigit**|\<ctype.h>|
|**iswdigit**|\<ctype.h> oder \<wchar.h>|
|**_isdigit_l**|\<ctype.h>|
|**_iswdigit_l**|\<ctype.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenklassifizierung](../../c-runtime-library/character-classification.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
