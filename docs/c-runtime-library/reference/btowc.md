---
title: btowc
ms.date: 11/04/2016
api_name:
- btowc
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
- api-ms-win-crt-convert-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- btowc
helpviewer_keywords:
- btowc function
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
ms.openlocfilehash: 1f03fce8686f919af85ee3751cb9a0a3fca1ede7
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943471"
---
# <a name="btowc"></a>btowc

Bestimmt, ob eine ganze Zahl ein gültiges Einzelbytezeichen im ersten Umschaltzustand darstellt.

## <a name="syntax"></a>Syntax

```C
wint_t btowc(
   int character
);
```

### <a name="parameters"></a>Parameter

*character*<br/>
Zu testende ganze Zahl.

## <a name="return-value"></a>Rückgabewert

Gibt die Breitzeichendarstellung des Zeichens zurück, wenn die ganze Zahl ein gültiges Einzelbytezeichen im ersten Umschaltzustand darstellt. Gibt WEOF zurück, wenn die ganze Zahl ein EOF oder kein gültiges Einzelbytezeichen im ersten Umschaltzustand ist. Das aktuelle **LC_TYPE** -Gebiets Schema wirkt sich auf die Ausgabe dieser Funktion aus.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**btowc**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
