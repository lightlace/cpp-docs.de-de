---
title: "_get_daylight | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__daylight"
  - "_get_daylight"
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
  - "get_daylight"
  - "_get_daylight"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_daylight-Funktion"
  - "Sommerzeit-Offset"
  - "get_daylight-Funktion"
ms.assetid: f85a6ba3-e187-4ca7-aed7-ffc694c8ac4c
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _get_daylight
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die Sommerzeitverschiebung in Stunden ab.  
  
## Syntax  
  
```  
  
error_t _get_daylight(      int* hours );  
```  
  
#### Parameter  
 `hours`  
 Die Verschiebung der Sommerzeit in Stunden.  
  
## Rückgabewert  
 Bei Erfolg Null oder ein `errno`\-.Wert, falls ein Fehler auftritt.  
  
## Hinweise  
 Die Funktion `_get_daylight` ruft die Anzahl der Stunden in der Sommerzeit als Ganzzahl ab.  Wenn die Sommerzeit gültig ist, beträgt die Standardzeitverschiebung eine Stunde \(obwohl in ein paar Regionen eine Zeitverschiebung von zwei Stunden gilt\).  
  
 Wenn `hours` den Wert `NULL` annimmt, wird wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben der Handler für ungültige Parameter aufgerufen.  Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `EINVAL` zurück.  
  
 Es wird empfohlen, diese Funktion statt des Makros `_daylight` oder der veralteten Funktion`__daylight` zu verwenden.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_get_daylight`|\<time.h\>|  
  
 Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [\_get\_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [\_get\_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [\_get\_tzname](../../c-runtime-library/reference/get-tzname.md)