---
title: _RTC_NumErrors
ms.date: 11/04/2016
api_name:
- _RTC_NumErrors
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _RTC_NumErrors
- RTC_NumErrors
helpviewer_keywords:
- run-time errors
- _RTC_NumErrors function
- RTC_NumErrors function
ms.assetid: 7e82adae-38e2-4f8b-bc0b-37bda8109fd1
ms.openlocfilehash: 72056208ca6d714f788ae325b90786f5be4ab443
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949030"
---
# <a name="_rtc_numerrors"></a>_RTC_NumErrors

Gibt die Gesamtzahl der Fehler zurück, die durch die Fehlerprüfung zur Laufzeit (RTC) erkannt werden können. Sie können diese Zahl als Steuerung in einer **for**-Schleife verwenden, wobei jeder Wert in der Schleife an [_RTC_GetErrDesc](rtc-geterrdesc.md) übergeben wird.

## <a name="syntax"></a>Syntax

```C

int _RTC_NumErrors( void );
```

## <a name="return-value"></a>Rückgabewert

Eine ganze Zahl, deren Wert die Gesamtzahl der Fehler darstellt, die von den Visual C++-Fehlerprüfungen zur Laufzeit erkannt werden können.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_RTC_NumErrors**|\<rtcapi.h>|

Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[_RTC_GetErrDesc](rtc-geterrdesc.md)<br/>
[Laufzeitfehlerüberprüfung](../../c-runtime-library/run-time-error-checking.md)<br/>
