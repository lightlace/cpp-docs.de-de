---
title: _get_dstbias | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_dstbias
- __dstbias
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
- __dstbias
- _get_dstbias
- get_dstbias
dev_langs:
- C++
helpviewer_keywords:
- __dstbias
- daylight saving time offset
- get_dstbias function
- _get_dstbias function
ms.assetid: e751358c-1ecc-411b-ae2c-81b2ec54ea45
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.openlocfilehash: 51facd97e9e1b7478893c23693d67cd022b5bed7
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="getdstbias"></a>_get_dstbias
Ruft die Sommerzeitverschiebung in Sekunden ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      error_t _get_dstbias(   
    int* seconds  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `seconds`  
 Die Verschiebung der Sommerzeit in Sekunden.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg Null oder ein `errno`-.Wert, falls ein Fehler auftritt.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `_get_dstbias` ruft die Anzahl der Sekunden in der Sommerzeit als Ganzzahl ab. Wenn die Sommerzeit gültig ist, beträgt die Standardzeitverschiebung 3600 Sekunden. Dies ist die Anzahl der Sekunden in einer Stunde (obwohl in ein paar Regionen eine Zeitverschiebung von zwei Stunden gilt).  
  
 Wenn `seconds` `NULL` ist, wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen. Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `EINVAL` zurück.  
  
 Es wird empfohlen, diese Funktion statt des Makros `_dstbias` oder der veralteten Funktion`__dstbias` zu verwenden.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_get_dstbias`|\<time.h>|  
  
 Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [_get_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [_get_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [_get_tzname](../../c-runtime-library/reference/get-tzname.md)
