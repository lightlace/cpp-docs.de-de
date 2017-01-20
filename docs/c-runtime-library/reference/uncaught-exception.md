---
title: "__uncaught_exception"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "__uncaught_exception"
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
apitype: "DLLExport"
f1_keywords: 
  - "__uncaught_exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__uncaught_exception"
ms.assetid: 4d9b75c6-c9c7-4876-b761-ea9ab1925e96
caps.latest.revision: 2
caps.handback.revision: "2"
ms.author: "corob"
manager: "ghogen"
---
# __uncaught_exception
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob eine oder mehrere Ausnahmen ausgelöst wurden an, jedoch noch nicht durch den entsprechenden `catch`\-Block einer [try\-catch\-](../../cpp/try-throw-and-catch-statements-cpp.md)\-Anweisung behandelt werden.  
  
## Syntax  
  
```cpp  
bool __uncaught_exception(  
   );  
```  
  
## Rückgabewert  
 `true` der Zeit, die eine Ausnahme in einem Block `try` ausgelöst wird, bis der entsprechende `catch`\-Block initialisiert ist; andernfalls `false`.  
  
## Hinweise  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|\_\_uncaught\_exception|eh.h|  
  
## Siehe auch  
 [try\-, throw\- und catch\-Anweisungen \(C\+\+\)](../../cpp/try-throw-and-catch-statements-cpp.md)