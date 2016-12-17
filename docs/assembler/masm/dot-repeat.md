---
title: ".REPEAT"
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
  - ".REPEAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".REPEAT directive"
ms.assetid: cb8ad8c6-587b-42f9-a0ad-b5316a24918c
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# .REPEAT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Generiert Code, der die Ausführung des Blocks *der Anweisungen* wiederholt, bis `condition` auf true festgelegt ist.  [.UNTILCXZ](../../assembler/masm/dot-untilcxz.md), der true ist, wenn CX null ist, wird für [.UNTIL](../../assembler/masm/dot-until.md)ersetzt werden.  `condition` ist mit **.UNTILCXZ**optional.  
  
## Syntax  
  
```  
  
   .REPEAT  
statements  
.UNTIL condition  
```  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)