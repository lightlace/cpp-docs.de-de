---
title: "Zeichenfolgenliterale in prim&#228;ren Ausdr&#252;cken | Microsoft Docs"
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
  - "Zeichenfolgenliterale, In primären Ausdrücken"
ms.assetid: 3ec31278-527b-40d2-8c83-6b09e2d81ca6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Zeichenfolgenliterale in prim&#228;ren Ausdr&#252;cken
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein "Zeichenfolgenliteral" ist ein Zeichen, ein Breitzeichen oder eine Sequenz von angrenzenden Zeichen, die in Anführungszeichen gesetzt werden.  Da es keine Variablen sind, können weder Zeichenfolgenliterale noch deren Elemente als linksseitige Operanden in einer Zuweisungsoperation verwendet werden.  Der Typ eines Zeichenfolgenliterals ist ein Array von `char` \(oder ein Array von `wchar_t` für Breitzeichenliterale\).  Arrays in Ausdrücken werden in Zeiger konvertiert.  Weitere Informationen zu Zeichenfolgen finden Sie unter [Zeichenfolgenliterale](../c-language/c-string-literals.md).  
  
## Siehe auch  
 [C\-Ausdrücke \(primär\)](../c-language/c-primary-expressions.md)