---
title: "_except_handler3 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_except_handler3"
apilocation: 
  - "msvcrt.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_except_handler3"
  - "except_handler3"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_except_handler3-Funktion"
  - "except_handler3-Funktion"
ms.assetid: b0c64898-0ae5-48b7-9724-80135a0813e2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# _except_handler3
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Interne CRT\-Funktion.  Wird von einem Framework verwendet, um den passenden Ausnahmehandler zur Verarbeitung der aktuellen Ausnahme zu suchen.  
  
## Syntax  
  
```  
int _except_handler3(    PEXCEPTION_RECORD exception_record,    PEXCEPTION_REGISTRATION registration,    PCONTEXT context,    PEXCEPTION_REGISTRATION dispatcher );  
```  
  
#### Parameter  
 \[in\] `exception_record`  
 Informationen über die spezifische Ausnahme.  
  
 \[in\] `registration`  
 Die Aufzeichnung, die anzeigt, welche Bereichstabelle für die Suche nach dem Ausnahmehandler verwendet werden soll.  
  
 \[in\] `context`  
 Reserviert.  
  
 \[in\] `dispatcher`  
 Reserviert.  
  
## Rückgabewert  
 Gibt `DISPOSITION_DISMISS` zurück, wenn eine Ausnahme verworfen wird.  Gibt `DISPOSITION_CONTINUE_SEARCH` zurück, wenn die Ausnahme eine Ebene höher an die kapselnden Ausnahmehandler übergeben wird.  
  
## Hinweise  
 Wenn diese Methode einen passenden Ausnahmehandler findet, übergibt sie die Ausnahme an diesen Handler.  In dieser Situation wird diese Methode nicht an den Code zurückgegeben, der sie aufgerufen hat, und der Rückgabewert ist irrelevant.  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)