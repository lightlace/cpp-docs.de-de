---
title: _RTC_GetErrDesc
ms.date: 11/04/2016
api_name:
- _RTC_GetErrDesc
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
- RTC_GetErrDesc
- _RTC_GetErrDesc
helpviewer_keywords:
- run-time errors
- _RTC_GetErrDesc function
- RTC_GetErrDesc function
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
ms.openlocfilehash: 7174e9242b77a904df817886df4f8c763e3e0b2c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949056"
---
# <a name="_rtc_geterrdesc"></a>_RTC_GetErrDesc

Gibt eine kurze Beschreibung eines Fehlertyps der Fehlerprüfung zur Laufzeit (RTC) zurück.

## <a name="syntax"></a>Syntax

```C
const char * _RTC_GetErrDesc(
   _RTC_ErrorNumber errnum
);
```

### <a name="parameters"></a>Parameter

*errnum*<br/>
Eine Zahl zwischen null und einem um eins kleineren als dem von **_RTC_NumErrors**zurückgegebenen Wert.

## <a name="return-value"></a>Rückgabewert

Eine Zeichenfolge, die eine kurze Beschreibung eines der vom Laufzeit-Fehlerprüfsystem zurückgegebenen Fehlertypen enthält. Wenn der Fehler kleiner als 0 (null) oder größer als der oder gleich dem von [_RTC_NumErrors](rtc-numerrors.md)zurückgegebenen Wert ist, gibt **_RTC_GetErrDesc** den Wert **null**zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_RTC_GetErrDesc**|\<rtcapi.h>|

Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[_RTC_NumErrors](rtc-numerrors.md)<br/>
[Laufzeitfehlerüberprüfung](../../c-runtime-library/run-time-error-checking.md)<br/>
