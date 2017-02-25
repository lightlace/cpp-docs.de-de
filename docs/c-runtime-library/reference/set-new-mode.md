---
title: "_set_new_mode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_new_mode"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "set_new_mode"
  - "_set_new_mode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_new_mode-Funktion"
  - "Handlermodi"
  - "set_new_mode-Funktion"
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _set_new_mode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt einen neuen Handlermodus für `malloc` fest.  
  
## Syntax  
  
```  
int _set_new_mode(  
   int newhandlermode   
);  
```  
  
#### Parameter  
 `newhandlermode`  
 Neuer Handlermodus für `malloc`; gültiger Wert ist 0 oder 1.  
  
## Rückgabewert  
 Gibt dem vorherigen Handlermodus zurück, der für `malloc` festgelegt wird.  Ein Rückgabewert 1 gibt an, dass, auf Speicher zu belegen, dass `malloc` zuvor die neue Handlerroutine aufgerufen hat; ein Rückgabewert 0 gibt an, dass sie nicht geladen.  Wenn das Argument `newhandlermode` nicht 0 oder 1 entspricht, gibt \- 1 zurück.  
  
## Hinweise  
 Die Funktion C\+\+ `_set_new_mode` Legt den neuen Handlermodus für [malloc](../../c-runtime-library/reference/malloc.md) fest.  Der neue Handlermodus gibt an, ob bei einem Fehler `malloc` die neue Handlerroutine aufgerufen werden soll, wie dies von [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md) festgelegt ist.  Standardmäßig ruft `malloc` bei einem Speicherbelegungsfehler nicht die neue Handlerroutine auf.  Sie können dieses Standardverhalten überschreiben, sodass, wenn `malloc` Speicher nicht belegen kann,`malloc` die neue Handlerroutine genauso aufruft wie der `new`\-Operator, wenn dieser aus demselben Grund fehlschlägt.  Weitere Informationen finden Sie in [neu](../../cpp/new-operator-cpp.md) und [löschen](../../cpp/delete-operator-cpp.md) in Operatoren der *C\+\+\-Sprachreferenz*.  Um den Standardwert überschreibt, rufen Sie auf:  
  
```  
_set_new_mode(1)  
```  
  
 frühzeitig im Programm oder in Link mit Newmode.obj \(siehe [Linkoptionen](../../c-runtime-library/link-options.md)\).  
  
 Diese Funktion überprüft seine Parameter.  Wenn `newhandlermode` einen anderen Wert als 0 oder 1 ist, ruft die Funktion den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren,`set_new_mode` gibt **\_**\-1 zurück und legt `errno` auf `EINVAL` fest.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_set_new_mode`|\<new.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_query\_new\_handler](../../c-runtime-library/reference/query-new-handler.md)   
 [\_query\_new\_mode](../../c-runtime-library/reference/query-new-mode.md)