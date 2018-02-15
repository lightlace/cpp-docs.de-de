---
title: _RTC_SetErrorType | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _RTC_SetErrorType
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
- RTC_SetErrorType
- _RTC_SetErrorType
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- RTC_SetErrorType function
- _RTC_SetErrorType function
ms.assetid: f5f99be7-d357-4b11-b8f5-ddd3428f2b06
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f6aaeaabe07f84a10167057ff94b45f91af0c93
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="rtcseterrortype"></a>_RTC_SetErrorType
Ordnet einen Fehler, der von den Fehlerprüfungen zur Laufzeit (RTCs) erkannt wurde, einem Typ zu. Wie die Fehler des angegebenen Typs verarbeitet werden, hängt von Ihrem Fehlerhandler ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int _RTC_SetErrorType(  
   _RTC_ErrorNumber errnum,  
   int ErrType   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *errnum*  
 Eine Zahl zwischen null und einem um eins kleineren als dem von [_RTC_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md)zurückgegebenen Wert.  
  
 *ErrType*  
 Ein Wert, der dieser *errnum*zugewiesen werden soll. Sie können beispielsweise **_CRT_ERROR**verwenden. Wenn Sie `_CrtDbgReport` als Fehlerhandler verwenden, kann *ErrType* nur eins der in [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)definierten Symbole sein. Wenn Sie einen eigenen Fehlerhandler ([_RTC_SetErrorFunc](../../c-runtime-library/reference/rtc-seterrorfunc.md)) verwenden, können Sie so viele *ErrType*s definieren, wie es *errnum*s gibt.  
  
 Ein *ErrType* von _RTC_ERRTYPE_IGNORE hat für `_CrtSetReportMode`eine besondere Bedeutung; der Fehler wird ignoriert.  
  
## <a name="return-value"></a>Rückgabewert  
 Der vorherige Wert für den Fehlertyp `type`.  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig werden alle Fehler auf *ErrType* = 1 festgelegt, was **_CRT_ERROR**entspricht. Weitere Informationen zu den Standardfehlertypen, wie etwa **_CRT_ERROR**, finden Sie unter [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md).  
  
 Bevor Sie diese Funktion aufrufen können, müssen Sie zuerst eine der Initialisierungsfunktionen der Laufzeitfehlerüberprüfung aufrufen; siehe dazu [Verwenden von Laufzeitüberprüfungen ohne die C-Laufzeitbibliothek](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_RTC_SetErrorType`|\<rtcapi.h>|  
  
 Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [_RTC_GetErrDesc](../../c-runtime-library/reference/rtc-geterrdesc.md)   
 [Laufzeitfehlerüberprüfung](../../c-runtime-library/run-time-error-checking.md)