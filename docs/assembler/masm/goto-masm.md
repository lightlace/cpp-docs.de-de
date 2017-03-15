---
title: "GOTO (MASM) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "goto"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GOTO directive"
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# GOTO (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Überträgt Assembly in den:\-markierten Zeile*macrolabel*.  
  
## Syntax  
  
```  
  
GOTO   
macrolabel  
  
```  
  
## Hinweise  
 **GEHE ZU** ist nur innerhalb [MAKRO](../../assembler/masm/macro.md), [FÜR](../../assembler/masm/for-masm.md), [FORC](../../assembler/masm/forc.md), [REPEAT](../../assembler/masm/repeat.md)und **WHILE** Blöcke nicht zulässig.  Die Bezeichnung muss die einzelnen Direktiven in der Zeile sein und muss von einem führenden Doppelpunkt vorangestellt werden.  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)