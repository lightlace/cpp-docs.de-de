---
title: btowc | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- btowc
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
- btowc
dev_langs:
- C++
helpviewer_keywords:
- btowc function
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d0e56649218e6249550638af4e198cbd1284bc2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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

Gibt die Breitzeichendarstellung des Zeichens zurück, wenn die ganze Zahl ein gültiges Einzelbytezeichen im ersten Umschaltzustand darstellt. Gibt WEOF zurück, wenn die ganze Zahl ein EOF oder kein gültiges Einzelbytezeichen im ersten Umschaltzustand ist. Die Ausgabe dieser Funktion wird von der aktuellen beeinflusst **LC_TYPE** Gebietsschema.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**btowc**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
