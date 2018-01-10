---
title: _get_daylight | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __daylight
- _get_daylight
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_daylight
- _get_daylight
dev_langs: C++
helpviewer_keywords:
- get_daylight function
- daylight saving time offset
- _get_daylight function
ms.assetid: f85a6ba3-e187-4ca7-aed7-ffc694c8ac4c
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0407b18bed459aefaa904e32c39f491af73cba6e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="getdaylight"></a>_get_daylight
Ruft die Sommerzeitverschiebung in Stunden ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      error_t _get_daylight(   
    int* hours  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `hours`  
 Die Verschiebung der Sommerzeit in Stunden.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg Null oder ein `errno`-.Wert, falls ein Fehler auftritt.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `_get_daylight` ruft die Anzahl der Stunden in der Sommerzeit als Ganzzahl ab. Wenn die Sommerzeit gültig ist, beträgt die Standardzeitverschiebung eine Stunde (obwohl in ein paar Regionen eine Zeitverschiebung von zwei Stunden gilt).  
  
 Wenn `hours` `NULL` ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `EINVAL` zurück.  
  
 Es wird empfohlen, diese Funktion statt des Makros `_daylight` oder der veralteten Funktion`__daylight` zu verwenden.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_get_daylight`|\<time.h>|  
  
 Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Time Management (Uhrzeitverwaltung)](../../c-runtime-library/time-management.md)   
 [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [_get_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [_get_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [_get_tzname](../../c-runtime-library/reference/get-tzname.md)