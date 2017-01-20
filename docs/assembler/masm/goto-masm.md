---
title: "GOTO (MASM)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "goto"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GOTO directive"
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
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