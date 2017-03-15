---
title: "INSTR | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "InStr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "INSTR directive"
ms.assetid: fc37f6a2-3c95-47b2-b6bb-1066edd25994
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# INSTR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sucht das erste Vorkommen der *textitem2* in *textitem1*.  
  
## Syntax  
  
```  
  
name  
 INSTR [[position,]] textitem1, textitem2  
```  
  
## Hinweise  
 Die Anfangsposition ist optional.  Jedes Textelement kann eine Literalzeichenfolge, eine Konstante, die von `%`vorangestellt werden, oder die Zeichenfolge sein, die durch eine Makrofunktion zurückgegeben wurde.  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)