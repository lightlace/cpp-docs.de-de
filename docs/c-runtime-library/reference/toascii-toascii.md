---
title: toascii, __toascii | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf4c29934d22d3f20d79650faa406f217ffdd4c6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
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

*c*  
Zu konvertierendes Zeichen.

## <a name="return-value"></a>Rückgabewert

`__toascii` Konvertiert den Wert der *c* und 7-Bit-ASCII liegen, und gibt das Ergebnis zurück. Es ist kein Rückgabewert zur Fehleranzeige reserviert.

## <a name="remarks"></a>Hinweise

Die Routine `__toascii` konvertiert das angegebene Zeichen in ein ASCII-Zeichen, indem es beim Abschneiden die unteren 7 Bits übrig lässt. Es wird keine andere Transformation angewendet.

Die Routine `__toascii` ist als Makro definiert, es sei denn, das Präprozessormakro _CTYPE_DISABLE_MACROS ist definiert. Für die Abwärtskompatibilität `toascii` wird als Makro definiert nur, wenn [&#95; &#95; STDC++ &#95; &#95; ](../../preprocessor/predefined-macros.md) ist nicht definiert oder wird definiert als 0 ist; andernfalls ist es nicht definiert.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`toascii`, `__toascii`|C: \<ctype.h><br /><br /> C++: \<cctype> oder \<ctype.h>|

Das `toascii`-Makro ist eine POSIX-Erweiterung und `__toascii` ist eine Microsoft-spezifische Implementierung der POSIX-Erweiterung. Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
[is- und isw-Routinen](../../c-runtime-library/is-isw-routines.md)   
[to-Funktionen](../../c-runtime-library/to-functions.md)