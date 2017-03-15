---
title: "ML Fatal Error A1011 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A1011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1011"
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Fatal Error A1011
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Direktiven müssen im Kontrollblock sein**  
  
 Der Assembler gefundene Direktive auf hoher Ebene, bei denen nicht erwartet wurde.  Eine der folgende Direktive wurde nicht gefunden:  
  
-   [.ELSE](../../assembler/masm/dot-else.md) ohne [.IF](../../assembler/masm/dot-if.md)  
  
-   [.ENDIF](../../assembler/masm/dot-endif.md) ohne [.IF](../../assembler/masm/dot-if.md)  
  
-   [.ENDW](../../assembler/masm/dot-endw.md) ohne [.WHILE](../../assembler/masm/dot-while.md)  
  
-   [.UNTILCXZ](../../assembler/masm/dot-untilcxz.md) ohne [.REPEAT](../../assembler/masm/dot-repeat.md)  
  
-   [.CONTINUE](../../assembler/masm/dot-continue.md) ohne [.WHILE](../../assembler/masm/dot-while.md) oder [.REPEAT](../../assembler/masm/dot-repeat.md)  
  
-   [.BREAK](../../assembler/masm/dot-break.md) ohne [.WHILE](../../assembler/masm/dot-while.md) oder [.REPEAT](../../assembler/masm/dot-repeat.md)  
  
-   [.ELSE](../../assembler/masm/dot-else.md) nach `.ELSE`  
  
## Siehe auch  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)