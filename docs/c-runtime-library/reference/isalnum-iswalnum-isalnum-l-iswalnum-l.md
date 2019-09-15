---
title: isalnum, iswalnum, _isalnum_l, _iswalnum_l
ms.date: 11/04/2016
api_name:
- _iswalnum_l
- _isalnum_l
- iswalnum
- isalnum
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
- _istalnum_l
- _iswalnum_l
- iswalnum
- _isalnum_l
- isalnum
- _istalnum
helpviewer_keywords:
- _istalnum function
- _ismbcalnum_l function
- iswalnum function
- isalnum function
- istalnum function
- _isalnum_l function
- _istalnum_l function
- _iswalnum_l function
ms.assetid: 0dc51306-ade8-4944-af27-e4176fc89093
ms.openlocfilehash: 636e43a921c2b859db3a31b3dd658112f4e8e9f4
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954591"
---
# <a name="isalnum-iswalnum-_isalnum_l-_iswalnum_l"></a>isalnum, iswalnum, _isalnum_l, _iswalnum_l

Bestimmt, ob eine ganze Zahl ein alphanumerisches Zeichen darstellt.

## <a name="syntax"></a>Syntax

```C
int isalnum( int c );
int iswalnum( wint_t c );
int _isalnum_l( int c,  _locale_t locale );
int _iswalnum_l( wint_t c, _locale_t locale );
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu testende ganze Zahl.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Jede dieser Routinen gibt einen Wert ungleich 0 (null) zurück, wenn *c* eine bestimmte Darstellung eines alphanumerischen Zeichens ist. **isalnum** gibt einen Wert ungleich 0 (null) zurück, wenn für *c*entweder **isalpha** oder **IsDigit** ungleich 0 (null) ist, d. h., wenn *c* innerhalb der Bereiche a-z, a-z oder 0-9 liegt. **iswalnum** gibt einen Wert ungleich 0 (null) zurück, wenn **iswalpha** oder **iswdigit** für *c*ungleich 0 (null) ist. Jede dieser Routinen gibt 0 zurück, wenn *c* die Test Bedingung nicht erfüllt.

Die Versionen dieser Funktionen mit dem **_l** -Suffix verwenden den Gebiets Schema Parameter, der anstelle des aktuellen Gebiets Schemas übergeben wurde. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Das Verhalten von **isalnum** und **_isalnum_l** ist nicht definiert, wenn *c* nicht EOF ist oder im Bereich von 0 bis 0xFF (einschließlich) liegt. Wenn eine Debug-CRT-Bibliothek verwendet wird und *c* keiner dieser Werte ist, wird von den Funktionen eine-Assertion erhoben.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istalnum**|**isalnum**|[_ismbcalnum](ismbcalnum-functions.md)|**iswalnum**|
|**_istalnum_l**|**_isalnum_l**|**_ismbcalnum_l**|**_iswalnum_l**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**isalnum**|\<ctype.h>|
|**iswalnum**|\<ctype.h> oder \<wchar.h>|
|**_isalnum_l**|\<ctype.h>|
|**_iswalnum_l**|\<ctype.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenklassifizierung](../../c-runtime-library/character-classification.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
