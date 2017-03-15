---
title: "ML Fatal Error A1007 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A1007"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1007"
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Fatal Error A1007
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Schachtelungsebene zu tief**  
  
 Der Assembler hat seine Schachtelungs beschränkt.  Die Grenze beträgt 20 Ebenen, wenn bekannt. Andernfalls  
  
 Eines der folgenden Elemente zu tief geschachtelt wurde:  
  
-   Direktiven auf hoher Ebene wie [.IF](../../assembler/masm/dot-if.md), [.REPEAT](../../assembler/masm/dot-repeat.md)oder [.WHILE](../../assembler/masm/dot-while.md).  
  
-   Eine Strukturdefinition.  
  
-   BedingtASSEMBLY\-Direktive.  
  
-   Eine Prozedurdefinition.  
  
-   [PUSHCONTEXT](../../assembler/masm/pushcontext.md)\-Direktive \(die Kapazität ist 10\).  
  
-   Eine Definition des Segments.  
  
-   Eine Includedatei.  
  
-   Ein Makro.  
  
## Siehe auch  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)