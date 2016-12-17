---
title: "UNION"
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
  - "union"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UNION directive"
ms.assetid: 52504abf-7dc1-47c5-944c-b886803a0c6a
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# UNION
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Deklariert eine Union von einem oder mehreren Datentypen.  Die *fielddeclarations* müssen gültige Datendefinitionen sein.  Lassen Sie die [ENDEN](../../assembler/masm/ends-masm.md) *Name* Bezeichnung auf geschachtelte **UNION** Definitionen weg.  
  
## Syntax  
  
```  
  
      name   
      UNION [[alignment]] [[, NONUNIQUE]]  
   fielddeclarations  
[[name]] ENDS  
```  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)