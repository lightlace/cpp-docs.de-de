---
title: "_setjmp3 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_setjmp3"
apilocation: 
  - "msvcrt.dll"
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "setjmp3"
  - "_setjmp3"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_setjmp3-Funktion"
  - "setjmp3-Funktion"
ms.assetid: 6129c2f3-8bac-4fdb-a827-44e1eebba500
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# _setjmp3
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Interne CRT\-Funktion.  Eine neue Implementierung der Funktion `setjmp`.  
  
## Syntax  
  
```  
int _setjmp3(    OUT jmp_buf env,    int count,    (optional parameters) );  
```  
  
#### Parameter  
 \[out\] `env`  
 Adresse des Puffers zur Speicherung von Statusinformationen.  
  
 \[in\] `count`  
 Die Anzahl zusätzlicher `DWORD`s von Informationen, die in der `optional parameters` gespeichert werden.  
  
 \[in\] `optional parameters`  
 Zusätzliche vom systeminternen Objekt `setjmp` nach unten geschobene Daten.  Das erste `DWORD` ist ein Funktionszeiger, der verwendet wird, um zusätzliche Daten aufzurufen und zu einem nichtflüchtigen Speicherstatus zurückzukehren.  Das zweite `DWORD` ist die wiederherzustellende Versuchsebene.  Alle weiteren Daten werden im generischen Datenarray im `jmp_buf` gespeichert.  
  
## Rückgabewert  
 Gibt immer 0 zurück.  
  
## Hinweise  
 Verwenden Sie diese Funktion nicht in einem C\+\+\-Programm.  Es handelt sich um eine systeminterne Funktion, die C\+\+ nicht unterstützt.  Weitere Informationen zum Verwenden von `setjmp` finden Sie unter [Verwenden von "setjmp\/longjmp"](../cpp/using-setjmp-longjmp.md).  
  
## Anforderungen  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [setjmp](../c-runtime-library/reference/setjmp.md)