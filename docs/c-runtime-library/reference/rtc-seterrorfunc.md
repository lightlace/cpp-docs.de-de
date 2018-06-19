---
title: _RTC_SetErrorFunc | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _RTC_SetErrorFunc
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
- RTC_SetErrorFunc
- _RTC_SetErrorFunc
dev_langs:
- C++
helpviewer_keywords:
- RTC_SetErrorFunc function
- _RTC_SetErrorFunc function
ms.assetid: b2292722-0d83-4092-83df-3d5b19880666
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e146f699f9026260470b1c540c7567f074896a38
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451614"
---
# <a name="rtcseterrorfunc"></a>_RTC_SetErrorFunc

Legt eine Funktion als den Handler für das Melden von Fehlern der Fehlerprüfung zur Laufzeit (RTCs) fest. Diese Funktion ist veraltet. Verwenden Sie **_RTC_SetErrorFuncW** stattdessen.

## <a name="syntax"></a>Syntax

```C
_RTC_error_fn _RTC_SetErrorFunc(
   _RTC_error_fn function
);
```

### <a name="parameters"></a>Parameter

*Funktion*<br/>
Die Adresse der Funktion, die Fehlerprüfungen zur Laufzeit verarbeitet.

## <a name="return-value"></a>Rückgabewert

Die zuvor definierte Fehlerfunktion. Wenn keine zuvor definierte Funktion vorhanden ist, gibt **NULL**.

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion nicht. Verwenden Sie stattdessen **_RTC_SetErrorFuncW**. Sie wird nur aus Gründen der Abwärtskompatibilität beibehalten.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_RTC_SetErrorFunc**|\<rtcapi.h>|

Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[Laufzeitfehlerüberprüfung](../../c-runtime-library/run-time-error-checking.md)<br/>
