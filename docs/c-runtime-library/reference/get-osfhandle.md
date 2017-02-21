---
title: "_get_osfhandle | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_osfhandle"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_osfhandle"
  - "_get_osfhandle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Betriebssysteme, Abrufen von Dateihandles"
  - "get_osfhandle-Funktion"
  - "_get_osfhandle-Funktion"
  - "Dateihandles [C++], Betriebssystem"
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _get_osfhandle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft das Dateihandle des Betriebssystems, das dem angegebenen Dateideskriptor zugeordnet ist.  
  
## Syntax  
  
```  
intptr_t _get_osfhandle(   
   int fd   
);  
```  
  
#### Parameter  
 `fd`  
 Ein bereits Dateideskriptor.  
  
## Rückgabewert  
 Ein Dateihandle des Betriebssystems, wenn `fd` gültig ist.  Andernfalls wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, legt `INVALID_HANDLE_VALUE` gibt dieser Funktion \(\- 1\) und `errno` auf `EBADF` fest und gibt ein ungültiges Dateihandle an.  
  
## Hinweise  
 Um eine Datei zu schließen, die mit `_get_osfhandle` geöffnet ist, rufen Sie `_close` auf.  Das zugrunde liegende Handle wird auch durch den Aufruf `_close` geschlossen, ist daher nicht erforderlich, die Win32\-Funktion `CloseHandle` im anfänglichen Handle aufzurufen.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_get_osfhandle`|\<io.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_dup, \_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)