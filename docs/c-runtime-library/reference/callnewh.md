---
title: "_callnewh | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_callnewh"
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
  - "_callnewh"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_callnewh"
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# _callnewh
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den aktuell installierten *neuen Handler* auf.  
  
## Syntax  
  
```cpp  
int _callnewh(  
   size_t size  
   )  
  
```  
  
#### Parameter  
 `size`  
 Der Speicherplatz, den der [neuer Operator](../../cpp/new-operator-cpp.md) versucht hat zu belegen.  
  
## Rückgabewert  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|0|Fehler: Entweder wurde kein neuer Handler installiert oder der neue Handler ist nicht aktiv.|  
|1|Erfolg: Der neue Handler wurde installiert und ist aktiv.  Die Speicherbelegung kann wiederholt werden.|  
  
## Ausnahmen  
 Diese Funktion löst [bad\_alloc](../../standard-library/bad-alloc-class.md) aus, wenn der *neue Handler* nicht gefunden werden kann.  
  
## Hinweise  
 Der *neue Handler* wird aufgerufen, wenn der [neue Operator](../../cpp/new-operator-cpp.md) die Speicherbelegung nicht erfolgreich durchführen kann.  Der neue Handler initialisiert dann möglicherweise einige entsprechende Aktionen, z. B. die Freigabe des Speichers, sodass nachfolgende Belegungen erfolgreich sind.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|\_callnewh|internal.h|  
  
## Siehe auch  
 [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md)   
 [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md)