---
title: tolower, _tolower, towlower, _tolower_l, _towlower_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _tolower_l
- towlower
- tolower
- _tolower
- _towlower_l
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _totlower
- tolower
- _tolower
- towlower
dev_langs:
- C++
helpviewer_keywords:
- tolower_l function
- _tolower_l function
- totlower function
- string conversion, to different characters
- lowercase, converting to
- tolower function
- string conversion, case
- towlower function
- _tolower function
- _totlower function
- towlower_l function
- case, converting
- characters, converting
- _towlower_l function
ms.assetid: 86e0fc02-94ae-4472-9631-bf8e96f67b92
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 23d03190ae47857a7b49f687d1f03e78c0dbc9e0
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="tolower-tolower-towlower-tolowerl-towlowerl"></a>tolower, _tolower, towlower, _tolower_l, _towlower_l
Konvertiert ein Zeichen in Kleinbuchstaben.

## <a name="syntax"></a>Syntax

```C
int tolower(
   int c
);
int _tolower(
   int c
);
int towlower(
   wint_t c
);
int _tolower_l(
   int c,
   _locale_t locale
);
int _towlower_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu konvertierendes Zeichen.

*locale*<br/>
Für die gebietsschemaspezifische Übersetzung zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Jede dieser Routinen konvertiert eine Kopie des *c* in Kleinbuchstaben umgewandelt, wenn die Konvertierung möglich ist, und gibt das Ergebnis zurück. Es ist kein Rückgabewert zur Fehleranzeige reserviert.

## <a name="remarks"></a>Hinweise

Jede dieser Routinen konvertiert einen vorhandenen Großbuchstaben in einen Kleinbuchstaben, wenn dies möglich und relevant ist. Die Groß-/Kleinschreibung Konvertierung von **Towlower** ist gebietsschemaspezifisch. Es werden nur die für das aktuelle Gebietsschema relevanten Zeichen geändert. Die Funktionen ohne das **_l** -Suffix verwenden das aktuell festgelegte Gebietsschema. Die Versionen dieser Funktionen mit dem **_l** Suffix das Gebietsschema als Parameter übernehmen und verwenden, anstatt die aktuell festgelegten Gebietsschema. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

In der Reihenfolge für **_tolower** zu den erwarteten Ergebnissen [__isascii](isascii-isascii-iswascii.md) und [Isupper](isupper-isupper-l-iswupper-iswupper-l.md) müssen beide ungleich NULL zurückgeben.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totlower**|**tolower**|**_mbctolower**|**towlower**|
|**_totlower_l**|**_tolower_l**|**_mbctolower_l**|**_towlower_l**|

> [!NOTE]
> **_tolower_l** und **_towlower_l** haben keine gebietsschemaabhängigkeit und sollen nicht direkt aufgerufen werden. Sie dienen zur internen Verwendung durch **_totlower_l**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**tolower**|\<ctype.h>|
|**_tolower**|\<ctype.h>|
|**towlower**|\<ctype.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel in [to-Funktionen](../../c-runtime-library/to-functions.md).

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
[to-Funktionen](../../c-runtime-library/to-functions.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
