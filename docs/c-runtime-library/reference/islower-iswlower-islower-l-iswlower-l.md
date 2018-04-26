---
title: islower, iswlower, _islower_l, _iswlower_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- iswlower
- _islower_l
- islower
- _iswlower_l
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
- _istlower
- islower
- _ismbclower_l
- _liswlower_l
- _istlower_l
- _iswlower_l
- _islower _l
- _islower_l
- iswlower
dev_langs:
- C++
helpviewer_keywords:
- _islower _l function
- _ismbclower_l function
- islower function
- _iswlower_l function
- _liswlower_l function
- _istlower_l function
- istlower function
- _istlower function
- iswlower function
- _islower_l function
ms.assetid: fcc3b70a-2b47-45fd-944d-e5c1942e6457
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 14cbb62fcdb23983b7c3167e400ddbe7e8b6f480
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="islower-iswlower-islowerl-iswlowerl"></a>islower, iswlower, _islower_l, _iswlower_l

Bestimmt, ob eine ganze Zahl einen Kleinbuchstaben darstellt.

## <a name="syntax"></a>Syntax

```C
int islower(
   int c
);
int iswlower(
   wint_t c
);
int islower_l(
   int c,
   _locale_t locale
);
int _iswlower_l(
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

Jede dieser Routinen gibt ungleich NULL, wenn *c* ist eine bestimmte Darstellung eines Zeichens in Kleinbuchstaben. **IsLower** gibt einen Wert ungleich NULL zurück, wenn *c* ein Kleinbuchstabe (a bis Z). **Iswlower** gibt einen Wert ungleich NULL zurück, wenn *c* ein Breitzeichen, das einem Kleinbuchstaben entspricht, oder wenn *c* ist ein von der Implementierung definierten breitzeichensatz für den **Iswcntrl**, **Iswdigit**, **Iswpunct**, oder **Iswspace** ungleich NULL ist. Jede dieser Routinen gibt 0 zurück, wenn *c* die testbedingung nicht erfüllt.

Die Versionen dieser Funktionen mit dem **_l** -Suffix verwenden das das übergebene Gebietsschema anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Das Verhalten des **Islower** und **_islower_l** ist undefiniert, wenn *c* nicht EOF ist oder im Bereich von 0 bis 0xFF liegt. Wenn eine CRT-Debugbibliothek verwendet wird und *c* ist keine dieser Werte, lösen die Funktionen eine Assertion.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istlower**|**islower**|[_ismbclower](ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|**iswlower**|
|**_istlower_l**|`_islower _l`|[_ismbclower_l](ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|**_liswlower_l**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**islower**|\<ctype.h>|
|**iswlower**|\<ctype.h> oder \<wchar.h>|
|**_islower_l**|\<ctype.h>|
|**_swlower_l**|\<ctype.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenklassifizierung](../../c-runtime-library/character-classification.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
