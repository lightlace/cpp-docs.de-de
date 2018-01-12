---
title: _RTC_NumErrors | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _RTC_NumErrors
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
- _RTC_NumErrors
- RTC_NumErrors
dev_langs: C++
helpviewer_keywords:
- run-time errors
- _RTC_NumErrors function
- RTC_NumErrors function
ms.assetid: 7e82adae-38e2-4f8b-bc0b-37bda8109fd1
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b0d305575a2dca1df3084ab413b82d445260a6e1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="rtcnumerrors"></a>_RTC_NumErrors
Gibt die Gesamtzahl der Fehler zurück, die durch die Fehlerprüfung zur Laufzeit (RTC) erkannt werden können. Sie können diese Zahl als Steuerung in einer **for**-Schleife verwenden, wobei jeder Wert in der Schleife an [_RTC_GetErrDesc](../../c-runtime-library/reference/rtc-geterrdesc.md) übergeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
int _RTC_NumErrors( void );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, deren Wert die Gesamtzahl der Fehler darstellt, die von den Visual C++-Fehlerprüfungen zur Laufzeit erkannt werden können.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_RTC_NumErrors`|\<rtcapi.h>|  
  
 Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [_RTC_GetErrDesc](../../c-runtime-library/reference/rtc-geterrdesc.md)   
 [Laufzeitfehlerüberprüfung](../../c-runtime-library/run-time-error-checking.md)