---
title: ".IF"
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
  - ".IF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".IF directive"
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# .IF
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Generiert Code, der `condition1` testet \(z. B. AX führt \> 7\) und die *Anweisungen,* wenn diese Bedingung true ist.  
  
## Syntax  
  
```  
  
   .IF condition1   
statements  
[[.ELSEIF condition2   
   statements]]  
[[.ELSE  
   statements]]  
.ENDIF  
```  
  
## Hinweise  
 Wenn [.ELSE](../../assembler/masm/dot-else.md) folgt, werden ihre Anweisungen ausgeführt, wenn die ursprüngliche Zustand fehlerhaft war.  Beachten Sie, dass die Bedingungen zur Laufzeit ausgewertet werden.  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)