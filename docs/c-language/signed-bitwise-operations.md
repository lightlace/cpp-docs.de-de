---
title: "Signierte bitweise Operationen | Microsoft Docs"
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
  - "Bitweise Operationen"
  - "Signierte bitweise Operationen"
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Signierte bitweise Operationen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.3** Die Ergebnisse der bitweisen Vorgänge an Ganzzahlen mit Vorzeichen  
  
 Bitweise Vorgänge auf Ganzzahlen mit Vorzeichen arbeiten genauso wie bitweise Vorgänge auf Ganzzahlen ohne Vorzeichen.  So kann beispielsweise `–16 & 99` binär ausgedrückt werden als  
  
```  
  11111111 11110000  
& 00000000 01100011  
  _________________  
  00000000 01100000  
```  
  
 Das Ergebnis des bitweisen AND\-Vorgangs ist 96.  
  
## Siehe auch  
 [Ganze Zahlen](../c-language/integers.md)