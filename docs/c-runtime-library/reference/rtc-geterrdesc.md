---
title: _RTC_GetErrDesc | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- _RTC_GetErrDesc function
- RTC_GetErrDesc function
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8e3b0c7b0de8d8162c5d1ec08e3a7a072ce8c125
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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
Eine Zahl zwischen null und eins und kleiner als der von **_RTC_NumErrors** zurückgegebene Wert.

## <a name="return-value"></a>Rückgabewert

Eine Zeichenfolge, die eine kurze Beschreibung eines der vom Laufzeit-Fehlerprüfsystem zurückgegebenen Fehlertypen enthält. Wenn Fehler kleiner als 0 (null) oder größer als oder gleich dem Wert ist von zurückgegebenen [_RTC_NumErrors](rtc-numerrors.md), **_RTC_GetErrDesc** gibt NULL zurück.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_RTC_GetErrDesc**|\<rtcapi.h>|

Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[_RTC_NumErrors](rtc-numerrors.md)<br/>
[Laufzeitfehlerüberprüfung](../../c-runtime-library/run-time-error-checking.md)<br/>
