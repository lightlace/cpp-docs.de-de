---
title: "Ziele in mehreren Beschreibungsbl&#246;cken"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Blöcke, Mehrere für Beschreibungen"
  - "Beschreibungsblöcke"
  - "Mehrere Beschreibungsblöcke"
ms.assetid: 8618dcd9-c11d-4562-91a7-0c904ed438a8
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Ziele in mehreren Beschreibungsbl&#246;cken
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um ein Ziel in mehreren Beschreibungsblöcken mit verschiedenen Befehlen zu aktualisieren, werden zwei aufeinander folgende Doppelpunkte \(`::`\) zwischen Zielen und abhängigen Dateien angegeben.  
  
```  
target.lib :: one.asm two.asm three.asm  
    ml one.asm two.asm three.asm  
    lib target one.obj two.obj three.obj  
target.lib :: four.c five.c  
    cl /c four.c five.c  
    lib target four.obj five.obj  
```  
  
## Siehe auch  
 [Ziele](../build/targets.md)