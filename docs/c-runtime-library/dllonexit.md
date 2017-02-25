---
title: "__dllonexit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__dllonexit"
apilocation: 
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr120_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__dllonexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__dllonexit"
ms.assetid: 708f2ceb-f95c-46b0-a58d-d68b3fa36f12
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# __dllonexit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Registriert eine an der Beendigungszeit aufgerufen werden Routine.  
  
## Syntax  
  
```  
_onexit_t __dllonexit(  
   _onexit_t func,  
   _PVFV **  pbegin,   
   _PVFV **  pend   
   )  
```  
  
#### Parameter  
 `func`  
 Zeiger auf eine nach Beendigung Funktion, die ausgeführt wird.  
  
 `pbegin`  
 Zeiger auf eine Variable, die auf den Anfang einer Liste von Funktionen verweist, um an erneut, Trennen.  
  
 `pend`  
 Zeiger die Variable, die auf das Ende einer Liste von Funktionen verweist, um an erneut, Trennen.  
  
## Rückgabewert  
 Wenn erfolgreich, ein Zeiger zur Funktion des Benutzers.  Andernfalls ein NULL\-Zeiger.  
  
## Hinweise  
 Die Funktion `__dllonexit` ist der [\_onexit](../c-runtime-library/reference/onexit-onexit-m.md)\-Funktion analog, sofern die globalen Variablen, die durch diese Funktion verwendet werden, sind keine zu dieser Routine sichtbar.  Anstelle der globalen Variablen verwendet diese Funktion die Parameter `pbegin` und `pend`.  
  
 Die Funktionen `_onexit` und `atexit` in einer DLL, die mit MSVCRT.LIB verknüpft ist, müssen eigene atexit\-\/\_onexitliste übergeben.  Diese Routine ist der Mitarbeiter, der durch diese DLLs aufgerufen wird.  
  
 Der Typ `_PVFV` wird als `typedef void (__cdecl *_PVFV)(void)` definiert.  
  
## Anforderungen  
  
|Routine|Erforderliche Datei|  
|-------------|-------------------------|  
|\_\_dllonexit|onexit.c|  
  
## Siehe auch  
 [\_onexit, \_onexit\_m](../c-runtime-library/reference/onexit-onexit-m.md)