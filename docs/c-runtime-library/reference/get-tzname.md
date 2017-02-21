---
title: "_get_tzname | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_tzname"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_get_tzname"
  - "get_tzname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_tzname-Funktion"
  - "get_tzname-Funktion"
  - "Zeitzonen"
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _get_tzname
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die Zeichenfolgendarstellung des Zeitzonennamens oder des Tageslicht\-Normalzeit\-Zonennamens ab \(DST\).  
  
## Syntax  
  
```  
errno_t _get_tzname(  
    size_t* pReturnValue,  
    char* timeZoneName,  
    size_t sizeInBytes,  
    int index      
);  
```  
  
#### Parameter  
 \[out\] `pReturnValue`  
 Die Zeichenfolgenlänge von `timeZoneName` einschließlich einen Nullterminator.  
  
 \[out\] `timeZoneName`  
 Die Adresse einer Zeichenfolge für die Darstellung des Zeitzonennamens oder des Tageslicht\-Normalzeit\-Zonennamens \(DST\), je nach `index`.  
  
 \[in\] `sizeInBytes`  
 Die Größe der Zeichenfolge `timeZoneName` in Bytes.  
  
 \[in\] `index`  
 Der Index von einem der beiden Zeitzonennamen abzurufen.  
  
## Rückgabewert  
 Null wenn erfolgreich; andernfalls ein `errno`\-Typwert.  
  
 Wenn entweder `timeZoneName` ist `NULL` oder `sizeInBytes` einmal oder kleiner als null \(jedoch nicht beide\) ist, wird ein ungültiger Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `EINVAL` zurück.  
  
### Fehlerbedingungen  
  
|`pReturnValue`|`timeZoneName`|`sizeInBytes`|`index`|Rückgabewert|Inhalt von `timeZoneName`|  
|--------------------|--------------------|-------------------|-------------|------------------|-------------------------------|  
|Größe von TZ\-Namen|`NULL`|0|0 oder 1|0|nicht geändert|  
|Größe von TZ\-Namen|any|\> 0|0 oder 1|0|TZ\-Name|  
|nicht geändert|`NULL`|\> 0|any|`EINVAL`|nicht geändert|  
|nicht geändert|any|0 \(Null\)|any|`EINVAL`|nicht geändert|  
|nicht geändert|any|\> 0|\> 1|`EINVAL`|nicht geändert|  
  
## Hinweise  
 Die `_get_tzname`\-Funktion ruft die Zeichenfolgendarstellung des Zeitzonennamens oder des Tageslicht\-Normalzeit\-Zonennamens \(DST\) in die Adresse von `timeZoneName` abhängig von dem Indexwert, zusammen mit der Größe der Zeichenfolge in `pReturnValue` ab.  Wenn `timeZoneName``NULL` und `sizeInBytes` gleich ist, nur wird die Größe der Zeichenfolge der Zeitzone in Bytes in `pReturnValue` zurückgegeben.  Die Indexwerte müssen entweder 0 für Normalzeit\-Zone oder 1 für Tageslicht\-Normalzeit\-Zone sein; alle anderen Werte des Index verfügen unbestimmte Ergebnisse.  
  
### Indexwerte  
  
|`index`|Inhalt von `timeZoneName`|`timeZoneName` Standardwerte|  
|-------------|-------------------------------|----------------------------------|  
|0|Zeitzonenname|"PST"|  
|1|Tageslicht\-Normalzeit\-Zonenname|"PDT"|  
|\> 1 oder \< 0|`errno` auf `EINVAL` festgelegt|nicht geändert|  
  
 Es sei denn, die Werten explizit während der Laufzeit geändert werden, sind die Standardwerte PST "" und "PDT" bzw.  Die Größe dieser Zeichenarrays wird vom `TZNAME_MAX`\-Wert bestimmt.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_get_tzname`|\<time.h\>|  
  
 Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [\_get\_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [\_get\_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [\_get\_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [TZNAME\_MAX](../../c-runtime-library/tzname-max.md)