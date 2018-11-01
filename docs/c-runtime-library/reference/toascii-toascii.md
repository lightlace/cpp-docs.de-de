---
title: toascii, __toascii
ms.date: 11/04/2016
apiname:
- __toascii
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __toascii
- toascii
- ctype/toascii
- ctype/__toascii
helpviewer_keywords:
- toascii function
- string conversion, to ASCII characters
- __toascii function
- ASCII characters, converting to
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
ms.openlocfilehash: 22f76bdbdb21eb5b3cc9a226c111e321ee2fd0ce
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578970"
---
# <a name="toascii-toascii"></a>toascii, __toascii

Konvertiert Zeichen durch Abschneiden in 7-Bit-ASCII.

## <a name="syntax"></a>Syntax

```C
int __toascii(
   int c
);
#define toascii __toascii
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu konvertierendes Zeichen.

## <a name="return-value"></a>Rückgabewert

**__toascii** konvertiert den Wert der *c* und das 7-Bit-ASCII liegen, und gibt das Ergebnis zurück. Es ist kein Rückgabewert zur Fehleranzeige reserviert.

## <a name="remarks"></a>Hinweise

Die **__toascii** Routine konvertiert das angegebene Zeichen in eine ASCII-Zeichen an, um die niederwertigen 7 Bits abgeschnitten. Es wird keine andere Transformation angewendet.

Die **__toascii** Routine ist als Makro definiert, es sei denn, das Präprozessormakro _CTYPE_DISABLE_MACROS ist definiert. Für die Abwärtskompatibilität **Toascii** ist als Makro definiert nur, wenn [ &#95; &#95;STDC&#95; &#95; ](../../preprocessor/predefined-macros.md) ist nicht definiert oder wird als 0 definiert; andernfalls ist es nicht definiert.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**ToAscii**, **__toascii**|C: \<ctype.h><br /><br /> C++: \<cctype> oder \<ctype.h>|

Die **Toascii** Makro ist eine POSIX-Erweiterung und **__toascii** ist eine Microsoft-spezifische Implementierung der POSIX-Erweiterung. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
[to-Funktionen](../../c-runtime-library/to-functions.md)<br/>
