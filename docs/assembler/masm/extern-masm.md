---
title: "EXTERN (MASM)"
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
  - "extern"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EXTERN directive"
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
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