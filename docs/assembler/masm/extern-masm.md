---
title: "EXTERN (MASM) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "extern"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EXTERN directive"
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# EXTERN (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Definiert eine oder mehrere Variablen mit externen Bezeichnungen oder Symbole, die *Namen* aufgerufen werden, dessen Typ `type`ist.  
  
## Syntax  
  
```  
  
   EXTERN [[langtype]] name [[(altid)]] :  
type [[, [[langtype]] name [[(altid)]] :type]]...  
```  
  
## Hinweise  
 `type` kann [ABS](../../assembler/masm/operator-abs.md)sein, das *Namen* als Konstante importiert.  Identisch mit [EXTRN](../../assembler/masm/extrn.md).  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)