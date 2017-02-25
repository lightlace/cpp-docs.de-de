---
title: "Typ f&#252;r Zeichenfolgenliterale | Microsoft Docs"
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
  - "Zeichenfolgenliterale, Typ"
  - "Typen [C], Zeichenfolgenliterale"
ms.assetid: f50a28af-20c1-4440-bdc6-564c86a309c8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Typ f&#252;r Zeichenfolgenliterale
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zeichenfolgenliterale haben ein Typarray von `char` \(d. h. **char\[ \]**\). \(Breitzeichen\-Zeichenfolgen haben ein Typarray von `wchar_t` \(d. h. **wchar\_t\[ \]**\).\) Dies bedeutet, dass eine Zeichenfolge ein Array mit Elementen vom Typ `char` ist.  Die Anzahl der Elemente im Array entspricht der Anzahl von Zeichen in der Zeichenfolge plus einem beendenden Null\-Zeichen.  
  
## Siehe auch  
 [C\-Zeichenfolgenliterale](../c-language/c-string-literals.md)