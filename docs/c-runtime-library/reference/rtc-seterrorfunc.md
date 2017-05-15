---
title: _RTC_SetErrorFunc | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: f5846074abafcbbb3cfe55cca00b9912dd0a994e
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="rtcseterrorfunc"></a>_RTC_SetErrorFunc
Legt eine Funktion als den Handler für das Melden von Fehlern der Fehlerprüfung zur Laufzeit (RTCs) fest. Diese Funktion ist veraltet. Verwenden Sie stattdessen `_RTC_SetErrorFuncW` .  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      _RTC_error_fn _RTC_SetErrorFunc(  
   _RTC_error_fn function   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *Funktion*  
 Die Adresse der Funktion, die Fehlerprüfungen zur Laufzeit verarbeitet.  
  
## <a name="return-value"></a>Rückgabewert  
 Die zuvor definierte Fehlerfunktion. Wenn es keine zuvor definierte Funktion gibt, wird NULL zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion nicht. Verwenden Sie stattdessen `_RTC_SetErrorFuncW`. Sie wird nur aus Gründen der Abwärtskompatibilität beibehalten.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_RTC_SetErrorFunc`|\<rtcapi.h>|  
  
 Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [Laufzeitfehlerüberprüfung](../../c-runtime-library/run-time-error-checking.md)
