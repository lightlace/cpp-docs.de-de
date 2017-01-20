---
title: ".STACK"
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
  - ".STACK"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".STACK directive"
ms.assetid: 70019463-5d4f-41b6-8464-023a8ac2466f
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# .STACK
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn Sie mit [.MODEL](../../assembler/masm/dot-model.md)verwendet werden, definiert ein Segment \(mit segment Stapel Name des STAPEL\).  Optionale `size` gibt die Anzahl der Bytes für den Stapel an \(Standardwert 1,024\).  Die `.STACK`\-Direktive schließen automatisch die Stapel Statement.  
  
## Syntax  
  
```  
  
.STACK [[size]]  
```  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)