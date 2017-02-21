---
title: "STACKSIZE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "STACKSIZE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STACKSIZE-Anweisung in .def-Dateien"
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# STACKSIZE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt die Stapelgröße in Bytes fest.  
  
```  
STACKSIZE reserve[,commit]  
```  
  
## Hinweise  
 Alternativ kann die Stapelgröße auch mit der Option [\/STACK \(Stapelreservierungen\)](../../build/reference/stack-stack-allocations.md) festgelegt werden.  Einzelheiten über die Argumente *reserve* und `commit` finden Sie in der Beschreibung der jeweiligen Option.  
  
 Diese Option hat keine Auswirkungen auf DLLs.  
  
## Siehe auch  
 [Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)