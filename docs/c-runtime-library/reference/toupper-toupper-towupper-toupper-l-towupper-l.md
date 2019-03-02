---
title: toupper, _toupper, towupper, _toupper_l, _towupper_l
ms.date: 11/04/2016
apiname:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
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
ms.openlocfilehash: 6dd564a27ee7f3c2bb095564e5c9423249d6babc
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210613"
---
# <a name="toupper-toupper-towupper-toupperl-towupperl"></a>toupper, _toupper, towupper, _toupper_l, _towupper_l

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

Jede dieser Routinen konvertiert eine Kopie von *c*, sofern möglich, und gibt das Ergebnis zurück.

Wenn *c* ein Breitzeichen ist, für die **Iswlower** ungleich NULL ist, und es ist ein entsprechendes Breitzeichen für die [Iswupper](isupper-isupper-l-iswupper-iswupper-l.md) ungleich NULL ist, **Towupper** gibt das entsprechende Breitzeichen; andernfalls **Towupper** gibt *c* unverändert.

Es ist kein Rückgabewert zur Fehleranzeige reserviert.

In der Reihenfolge für **"ToUpper"** die erwarteten Ergebnisse, [__isascii](isascii-isascii-iswascii.md) und [Islower](islower-iswlower-islower-l-iswlower-l.md) müssen beide ungleich NULL zurückgeben.

## <a name="remarks"></a>Hinweise

Jede dieser Routinen konvertiert einen vorhandenen Kleinbuchstaben in einen Großbuchstaben, wenn dies möglich und relevant ist. Die Konvertierung von **Towupper** ist gebietsschemaspezifisch. Es werden nur die für das aktuelle Gebietsschema relevanten Zeichen geändert. Die Funktionen ohne das **_l** Suffix verwenden das aktuelle Gebietsschema. Die Versionen dieser Funktionen mit den **_l** Suffix übernehmen das Gebietsschema als Parameter und verwenden, anstatt des aktuellen Gebietsschemas. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

In der Reihenfolge für **"ToUpper"** die erwarteten Ergebnisse, [__isascii](isascii-isascii-iswascii.md) und [Isupper](isupper-isupper-l-iswupper-iswupper-l.md) müssen beide ungleich NULL zurückgeben.

[Datenkonvertierungsroutinen](../../c-runtime-library/data-conversion.md)

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totupper**|**toupper**|**_mbctoupper**|**towupper**|
|**_totupper_l**|**_toupper_l**|**_mbctoupper_l**|**_towupper_l**|

> [!NOTE]
> **_toupper_l** und **_towupper_l** haben keine gebietsschemaabhängigkeit und sind nicht dafür vorgesehen, direkt aufgerufen werden. Sie dienen zur internen Verwendung durch **_totupper_l**.

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
