---
title: "Segmentverweise in der Inlineassembly | Microsoft Docs"
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
  - "Inlineassembly, Register"
  - "Inlineassembly, Segmentverweise"
  - "Referenzen, Inlineassembly"
  - "Register"
  - "Register, Inlineassembly"
  - "Segmentverweise in der Inlineassembly"
ms.assetid: c63e6bb4-49d9-4fa1-bb22-eea21b5cbc0f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Segmentverweise in der Inlineassembly
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Sie müssen über Kurvensegmente Register statt über den Namen verweisen \(der Name des Segments `_TEXT` ungültig ist, z\).  Segmentüberschreibungen müssen das Register, wie in ES explizit verwenden: \[BX\].  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Verwenden von Assemblysprache in \_\_asm\-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)