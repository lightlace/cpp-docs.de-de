---
title: "_get_wpgmptr"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_get_wpgmptr"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_wpgmptr"
  - "_get_wpgmptr"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_get_wpgmptr-Funktion"
  - "_wpgmptr (globale Variable)"
  - "get_wpgmptr-Funktion"
  - "wpgmptr (globale Variable)"
ms.assetid: a77cdd13-2303-4b7c-9a60-8debdbef2011
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# _get_wpgmptr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den aktuellen Wert der globalen `_wpgmptr`\-Variable ab.  
  
## Syntax  
  
```  
errno_t _get_wpgmptr(     wchar_t **pValue  );  
```  
  
#### Parameter  
 \[out\] `pValue`  
 Ein Zeiger für eine Zeichenfolge, die mit dem aktuellen Wert der `_wpgmptr`\-Variable ausgefüllt wird.  
  
## Rückgabewert  
 Gibt 0 \(null\) zurück, wenn der Vorgang erfolgreich war. Wenn ein Fehler auftritt, erscheint ein Fehlercode.  Wenn `pValue` den Wert `NULL` annimmt, wird wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben der Handler für ungültige Parameter aufgerufen.  Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `EINVAL` zurück.  
  
## Hinweise  
 Die globale `_wpgmptr`\-Variable enthält den vollständigen Pfad für die ausführbare Datei, die dem Prozess als Breitzeichen\-Zeichenfolge zugeordnet ist.  Weitere Informationen finden Sie unter [\_pgmptr, \_wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_get_wpgmptr`|\<stdlib.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [\_get\_pgmptr](../../c-runtime-library/reference/get-pgmptr.md)