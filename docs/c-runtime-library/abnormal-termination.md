---
title: "_abnormal_termination | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_abnormal_termination"
apilocation: 
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_abnormal_termination"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_abnormal_termination"
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# _abnormal_termination
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob der `__finally`\-Block einer [TRY\-\-abschließendanweisung](../cpp/try-finally-statement.md) eingeführt wird, während das System einer internen Liste von Beendigungshandlern ausführt.  
  
## Syntax  
  
```cpp  
int   _abnormal_termination(  
   );  
```  
  
## Rückgabewert  
 `true`, wenn das System den Stapel *entlädt* ; andernfalls `false`.  
  
## Hinweise  
 Dies ist eine interne Funktion, die verwendet wird, um Entladungsausnahmen verwalten und nicht, im Benutzercode aufgerufen werden soll.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|\_abnormal\_termination|excpt.h|  
  
## Siehe auch  
 [try\-finally\-Anweisung](../cpp/try-finally-statement.md)