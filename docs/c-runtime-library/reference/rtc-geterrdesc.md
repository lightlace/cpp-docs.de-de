---
title: _RTC_GetErrDesc | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _RTC_GetErrDesc
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
dev_langs: C++
helpviewer_keywords:
- run-time errors
- _RTC_GetErrDesc function
- RTC_GetErrDesc function
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3149c1be671566785f67963368a50cdf2eee3809
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="rtcgeterrdesc"></a>_RTC_GetErrDesc
Gibt eine kurze Beschreibung eines Fehlertyps der Fehlerprüfung zur Laufzeit (RTC) zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      const char * _RTC_GetErrDesc(  
   _RTC_ErrorNumber errnum   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *errnum*  
 Eine Zahl zwischen null und einem um eins kleineren als dem von `_RTC_NumErrors`zurückgegebenen Wert.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die eine kurze Beschreibung eines der vom Laufzeit-Fehlerprüfsystem zurückgegebenen Fehlertypen enthält. Wenn der Fehler kleiner als null oder größer als der oder gleich dem von [_RTC_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md) zurückgegebenen Wert ist, gibt `_RTC_GetErrDesc` NULL zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_RTC_GetErrDesc`|\<rtcapi.h>|  
  
 Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [_RTC_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md)   
 [Laufzeitfehlerüberprüfung](../../c-runtime-library/run-time-error-checking.md)