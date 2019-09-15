---
title: toupper, _toupper, towupper, _toupper_l, _towupper_l
ms.date: 11/04/2016
api_name:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
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
- towupper
- _toupper
- _totupper
- toupper
helpviewer_keywords:
- _toupper function
- towupper function
- uppercase, converting strings to
- totupper function
- string conversion, to different characters
- towupper_l function
- toupper_l function
- string conversion, case
- _toupper_l function
- _towupper_l function
- _totupper function
- case, converting
- characters, converting
- toupper function
ms.assetid: cdef1b0f-b19c-4d11-b7d2-cf6334c9b6cc
ms.openlocfilehash: e17f139789b2c37292764f2e4508b59cddd2c03e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957908"
---
# <a name="toupper-_toupper-towupper-_toupper_l-_towupper_l"></a>toupper, _toupper, towupper, _toupper_l, _towupper_l

Zeichen in Großbuchstaben konvertieren.

## <a name="syntax"></a>Syntax

```C
int toupper(
   int c
);
int _toupper(
   int c
);
int towupper(
   wint_t c
);
int _toupper_l(
   int c ,
   _locale_t locale
);
int _towupper_l(
   wint_t c ,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu konvertierendes Zeichen.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Jede dieser Routinen konvertiert nach Möglichkeit eine Kopie von *c*und gibt das Ergebnis zurück.

Wenn *c* ein breit Zeichen ist, für das **iswlower** ungleich 0 (null) ist und ein entsprechendes breit Zeichen vorhanden ist, für das [iswupper](isupper-isupper-l-iswupper-iswupper-l.md) ungleich NULL ist, gibt **towupper** das entsprechende breit Zeichen zurück. Andernfalls gibt **towupper** *c* unverändert zurück.

Es ist kein Rückgabewert zur Fehleranzeige reserviert.

Damit **toupperdie** erwarteten Ergebnisse liefert, müssen [__isascii](isascii-isascii-iswascii.md) und [IsLower](islower-iswlower-islower-l-iswlower-l.md) beide Werte ungleich 0 (null) zurückgeben.

## <a name="remarks"></a>Hinweise

Jede dieser Routinen konvertiert einen vorhandenen Kleinbuchstaben in einen Großbuchstaben, wenn dies möglich und relevant ist. Die case-Konvertierung von **towupper** ist Gebiets Schema spezifisch. Es werden nur die für das aktuelle Gebietsschema relevanten Zeichen geändert. Die Funktionen ohne das **_l** -Suffix verwenden das aktuell festgelegte Gebiets Schema. Die Versionen dieser Funktionen mit dem **_l** -Suffix übernehmen das Gebiets Schema als Parameter und verwenden dieses anstelle des aktuell festgelegten Gebiets Schemas. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Damit **toupperdie** erwarteten Ergebnisse liefert, müssen [__isascii](isascii-isascii-iswascii.md) und [IsUpper](isupper-isupper-l-iswupper-iswupper-l.md) beide Werte ungleich 0 (null) zurückgeben.

[Datenkonvertierungsroutinen](../../c-runtime-library/data-conversion.md)

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totupper**|**toupper**|**_mbctoupper**|**towupper**|
|**_totupper_l**|**_toupper_l**|**_mbctoupper_l**|**_towupper_l**|

> [!NOTE]
> **_toupper_l** und **_towupper_l** haben keine Gebiets Schema Abhängigkeit und sollen nicht direkt aufgerufen werden. Sie werden für die interne Verwendung durch **_totupper_l**bereitgestellt.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**toupper**|\<ctype.h>|
|**_toupper**|\<ctype.h>|
|**towupper**|\<ctype.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel in [to-Funktionen](../../c-runtime-library/to-functions.md).

## <a name="see-also"></a>Siehe auch

[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
[to-Funktionen](../../c-runtime-library/to-functions.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
