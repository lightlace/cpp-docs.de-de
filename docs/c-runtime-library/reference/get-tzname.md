---
title: _get_tzname | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_tzname
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
- _get_tzname
- get_tzname
dev_langs: C++
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3f70e928c3877bf5d660231cbe2646f6cf72575e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="gettzname"></a>_get_tzname
Ruft die Darstellung der Zeichenfolge vom Namen der Zeitzone oder den Name der Standard-Sommerzeitzone (DST) ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t _get_tzname(  
    size_t* pReturnValue,  
    char* timeZoneName,  
    size_t sizeInBytes,  
    int index      
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `pReturnValue`  
 Die Länge der Zeichenfolge von `timeZoneName` einschließlich eines NULL-Terminators.  
  
 [out] `timeZoneName`  
 Die Adresse einer Zeichenfolge für die Darstellung des Namens der Zeitzone oder des Namens der Standard-Sommerzeitzone (DST), abhängig von `index`.  
  
 [in] `sizeInBytes`  
 Die Größe der `timeZoneName`-Zeichenfolge in Bytes.  
  
 [in] `index`  
 Der Index eines der zwei abzurufenden Zeitzonen.  
  
## <a name="return-value"></a>Rückgabewert  
 Null (0), wenn erfolgreich; andernfalls ein `errno`-Zeichenwert.  
  
 Wenn `timeZoneName`, `NULL` oder `sizeInBytes` null oder kleiner als null ist (aber nicht beides), wird ein Handler für ungültige Parameter abgerufen, siehe Beschreibung unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `EINVAL` zurück.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`pReturnValue`|`timeZoneName`|`sizeInBytes`|`index`|Rückgabewert|Inhalt von `timeZoneName`|  
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|  
|Größe des ZZ-Namens|`NULL`|0|0 oder 1|0|nicht geändert|  
|Größe des ZZ-Namens|any|> 0|0 oder 1|0|ZZ-Name|  
|nicht geändert|`NULL`|> 0|any|`EINVAL`|nicht geändert|  
|nicht geändert|any|Null|any|`EINVAL`|nicht geändert|  
|nicht geändert|any|> 0|> 1|`EINVAL`|nicht geändert|  
  
## <a name="remarks"></a>Hinweise  
 Die `_get_tzname`-Funktion ruft die Darstellung der Zeichenfolge des Namens der Zeitzone oder des Namens der Standard-Sommerzeit (DST) in die Adresse von `timeZoneName` ab, je nach Indexwert sowie der Größe der Zeichenfolge in `pReturnValue`. Wenn `timeZoneName` `NULL` ist und `sizeInBytes` gleich null, wird nur die Größe der Zeichenfolge der beiden Zeitzonen in Bytes in `pReturnValue` zurückgegeben. Die Indexwerte müssen entweder für Standard-Zeitzonen 0 oder 1 für Standard-Sommerzeitzonen betragen. Alle anderen Indexwerte haben unbestimmte Ergebnisse.  
  
### <a name="index-values"></a>Indexwerte  
  
|`index`|Inhalt von `timeZoneName`|`timeZoneName` Standardwert|  
|-------------|--------------------------------|----------------------------------|  
|0|Name der Zeitzone|„PST“|  
|1|Name der Standard-Sommerzeitzone|„PDT“|  
|> 1 oder < 0|`errno` auf `EINVAL` festgelegt.|nicht geändert|  
  
 Werden die Werte nicht ausdrücklich während der Laufzeit geändert, sind die Standardwerte „PST“ und „PDT“.  Die Größen dieser Zeichenarrays unterliegen dem `TZNAME_MAX`-Wert.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_get_tzname`|\<time.h>|  
  
 Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Time Management (Uhrzeitverwaltung)](../../c-runtime-library/time-management.md)   
 [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [_get_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [_get_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [_get_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [TZNAME_MAX](../../c-runtime-library/tzname-max.md)