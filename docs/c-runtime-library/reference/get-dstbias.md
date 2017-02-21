---
title: "_get_dstbias | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_dstbias"
  - "__dstbias"
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
  - "__dstbias"
  - "_get_dstbias"
  - "get_dstbias"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__dstbias"
  - "_get_dstbias-Funktion"
  - "Sommerzeit-Offset"
  - "get_dstbias-Funktion"
ms.assetid: e751358c-1ecc-411b-ae2c-81b2ec54ea45
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _get_dstbias
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die Sommerzeitverschiebung in Sekunden ab.  
  
## Syntax  
  
```  
  
error_t _get_dstbias(      int* seconds );  
```  
  
#### Parameter  
 `seconds`  
 Die Verschiebung der Sommerzeit in Sekunden.  
  
## Rückgabewert  
 Bei Erfolg Null oder ein `errno`\-.Wert, falls ein Fehler auftritt.  
  
## Hinweise  
 Die Funktion `_get_dstbias` ruft die Anzahl der Sekunden in der Sommerzeit als Ganzzahl ab.  Wenn die Sommerzeit gültig ist, beträgt die Standardzeitverschiebung 3600 Sekunden. Dies ist die Anzahl der Sekunden in einer Stunde \(obwohl in ein paar Regionen eine Zeitverschiebung von zwei Stunden gilt\).  
  
 Wenn `seconds` den Wert `NULL` annimmt, wird wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben der Handler für ungültige Parameter aufgerufen.  Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `EINVAL` zurück.  
  
 Es wird empfohlen, diese Funktion statt des Makros `_dstbias` oder der veralteten Funktion`__dstbias` zu verwenden.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_get_dstbias`|\<time.h\>|  
  
 Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [\_get\_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [\_get\_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [\_get\_tzname](../../c-runtime-library/reference/get-tzname.md)