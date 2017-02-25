---
title: "Ziele in mehreren Beschreibungsbl&#246;cken | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Blöcke, Mehrere für Beschreibungen"
  - "Beschreibungsblöcke"
  - "Mehrere Beschreibungsblöcke"
ms.assetid: 8618dcd9-c11d-4562-91a7-0c904ed438a8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
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