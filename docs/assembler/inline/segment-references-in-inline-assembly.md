---
title: "Segmentverweise in der Inlineassembly"
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
  - "Inlineassembly, Register"
  - "Inlineassembly, Segmentverweise"
  - "Referenzen, Inlineassembly"
  - "Register"
  - "Register, Inlineassembly"
  - "Segmentverweise in der Inlineassembly"
ms.assetid: c63e6bb4-49d9-4fa1-bb22-eea21b5cbc0f
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Segmentverweise in der Inlineassembly
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Sie müssen über Kurvensegmente Register statt über den Namen verweisen \(der Name des Segments `_TEXT` ungültig ist, z\).  Segmentüberschreibungen müssen das Register, wie in ES explizit verwenden: \[BX\].  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Verwenden von Assemblysprache in \_\_asm\-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)