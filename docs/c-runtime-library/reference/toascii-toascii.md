---
title: toascii, __toascii | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- toascii function
- string conversion, to ASCII characters
- __toascii function
- ASCII characters, converting to
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cead516a7e298e56d13d8f1a09a054057796ca64
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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

**__toascii** konvertiert den Wert der *c* und 7-Bit-ASCII liegen, und gibt das Ergebnis zurück. Es ist kein Rückgabewert zur Fehleranzeige reserviert.

## <a name="remarks"></a>Hinweise

Die **__toascii** Routine konvertiert das angegebene Zeichen in eine ASCII-Zeichen an, auf das niederwertige 7 Bits abgeschnitten. Es wird keine andere Transformation angewendet.

Die **__toascii** Routine als Makro definiert werden, es sei denn, die _CTYPE_DISABLE_MACROS Präprozessormakro definiert ist. Gründen der Abwärtskompatibilität **Toascii** wird als Makro definiert nur, wenn [ &#95; &#95;STDC++&#95; &#95; ](../../preprocessor/predefined-macros.md) ist nicht definiert oder wird definiert als 0; andernfalls ist es nicht definiert.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**ToAscii**, **__toascii**|C: \<ctype.h><br /><br /> C++: \<cctype> oder \<ctype.h>|

Die **Toascii** -Makro ist eine Erweiterung für POSIX und **__toascii** ist eine Microsoft-spezifische Implementierung der POSIX-Erweiterung. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
[to-Funktionen](../../c-runtime-library/to-functions.md)<br/>
