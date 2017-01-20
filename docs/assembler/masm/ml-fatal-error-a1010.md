---
title: "ML Fatal Error A1010"
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
  - "A1010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1010"
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# ML Fatal Error A1010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Blocks einem tiefer geschachtelten ohne Entsprechung:**  
  
 Ein Block beginnen, hatte kein entsprechendes Ende eines Blocks beendet oder hatte keinen übereinstimmenden Starten.  Eines der folgenden Elemente ist möglicherweise beteiligt:  
  
-   Direktiven auf hoher Ebene wie [.IF](../../assembler/masm/dot-if.md), [.REPEAT](../../assembler/masm/dot-repeat.md)oder [.WHILE](../../assembler/masm/dot-while.md).  
  
-   BedingtASSEMBLY\-Direktive wie [IF](../../assembler/masm/if-masm.md), [REPEAT](../../assembler/masm/repeat.md)oder **WHILE**.  
  
-   Eine Definition Struktur\- oder union.  
  
-   Eine Prozedurdefinition.  
  
-   Eine Definition des Segments.  
  
-   [POPCONTEXT](../../assembler/masm/popcontext.md)\-Direktive.  
  
-   Bedingt ASSEMBLY\-Direktive, wie [ELSE](../../assembler/masm/else-masm.md), [ELSEIF](../../assembler/masm/elseif-masm.md)oder **ENDIF** ohne passendes [IF](../../assembler/masm/if-masm.md).  
  
## Siehe auch  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)