---
title: _RTC_SetErrorType
ms.date: 11/04/2016
api_name:
- _RTC_SetErrorType
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
- RTC_SetErrorType
- _RTC_SetErrorType
helpviewer_keywords:
- run-time errors
- RTC_SetErrorType function
- _RTC_SetErrorType function
ms.assetid: f5f99be7-d357-4b11-b8f5-ddd3428f2b06
ms.openlocfilehash: 6c1eff5920931aa3b72bf3dbc6232c371828b16a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948925"
---
# <a name="_rtc_seterrortype"></a>_RTC_SetErrorType

Ordnet einen Fehler, der von den Fehlerprüfungen zur Laufzeit (RTCs) erkannt wurde, einem Typ zu. Wie die Fehler des angegebenen Typs verarbeitet werden, hängt von Ihrem Fehlerhandler ab.

## <a name="syntax"></a>Syntax

```C
int _RTC_SetErrorType(
   _RTC_ErrorNumber errnum,
   int ErrType
);
```

### <a name="parameters"></a>Parameter

*errnum*<br/>
Eine Zahl zwischen null und eins und kleiner als der von [_RTC_NumErrors](rtc-numerrors.md) zurückgegebene Wert.

*ErrType*<br/>
Ein Wert, der dieser *errnum*zugewiesen werden soll. Sie können beispielsweise **_CRT_ERROR**verwenden. Wenn Sie **_CrtDbgReport** als Fehlerhandler verwenden, kann *errtype* nur eines der in [_CrtSetReportMode](crtsetreportmode.md)definierten Symbole sein. Wenn Sie einen eigenen Fehlerhandler ([_RTC_SetErrorFunc](rtc-seterrorfunc.md)) verwenden, können Sie so viele *ErrType*s definieren, wie es *errnum*s gibt.

Ein *errtype* von _RTC_ERRTYPE_IGNORE hat eine besondere Bedeutung für **_CrtSetReportMode**; der Fehler wird ignoriert.

## <a name="return-value"></a>Rückgabewert

Der vorherige Wert für *den Fehlertyp.*

## <a name="remarks"></a>Hinweise

Standardmäßig werden alle Fehler auf *ErrType* = 1 festgelegt, was **_CRT_ERROR**entspricht. Weitere Informationen zu den Standardfehlertypen, wie etwa **_CRT_ERROR**, finden Sie unter [_CrtDbgReport](crtdbgreport-crtdbgreportw.md).

Bevor Sie diese Funktion aufrufen können, müssen Sie zuerst eine der Initialisierungsfunktionen der Laufzeitfehlerüberprüfung aufrufen; siehe dazu [Verwenden von Laufzeitüberprüfungen ohne die C-Laufzeitbibliothek](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_RTC_SetErrorType**|\<rtcapi.h>|

Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[_RTC_GetErrDesc](rtc-geterrdesc.md)<br/>
[Laufzeitfehlerüberprüfung](../../c-runtime-library/run-time-error-checking.md)<br/>
