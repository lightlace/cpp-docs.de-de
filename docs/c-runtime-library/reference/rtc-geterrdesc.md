---
title: _RTC_GetErrDesc
ms.date: 11/04/2016
apiname:
- _RTC_GetErrDesc
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
apitype: DLLExport
f1_keywords:
- RTC_GetErrDesc
- _RTC_GetErrDesc
helpviewer_keywords:
- run-time errors
- _RTC_GetErrDesc function
- RTC_GetErrDesc function
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
ms.openlocfilehash: d164626ea89bbe10f5b2ffe4224bf6381e40bab0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590306"
---
# <a name="rtcgeterrdesc"></a>_RTC_GetErrDesc

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

Eine Zeichenfolge, die eine kurze Beschreibung eines der vom Laufzeit-Fehlerprüfsystem zurückgegebenen Fehlertypen enthält. Wenn Fehler kleiner als 0 (null) oder größer als oder gleich dem Wert, der vom [_RTC_NumErrors](rtc-numerrors.md), **_RTC_GetErrDesc** gibt **NULL**.

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
