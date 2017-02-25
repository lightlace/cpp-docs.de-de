---
title: "EXTERNDEF | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EXTERNDEF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EXTERNDEF directive"
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# EXTERNDEF
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Definiert eine oder mehrere Variablen mit externen Bezeichnungen oder Symbole, die *Namen* aufgerufen werden, dessen Typ `type`ist.  
  
## Syntax  
  
```  
  
EXTERNDEF [[langtype]] name:type [[, [[langtype]] name:type]]...  
```  
  
## Hinweise  
 Wenn der *Name* im Modul definiert ist, wird er als [Token](../../assembler/masm/public-masm.md)behandelt.  Wenn Namen im Modul verwiesen wird, wird er als [EXTERN](../../assembler/masm/extern-masm.md)behandelt.  Wenn der *Name* nicht verwiesen wird, wird er ignoriert.  `type` kann [ABS](../../assembler/masm/operator-abs.md)sein, das *Namen* als Konstante importiert.  Normalerweise wird in den Dateien enthalten.  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)