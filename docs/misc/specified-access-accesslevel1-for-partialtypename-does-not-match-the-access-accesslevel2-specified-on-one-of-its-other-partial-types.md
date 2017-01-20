---
title: "Der angegebene Zugriff &#39;&lt;Zugriffsebene1&gt;&#39; f&#252;r &#39;&lt;PartiellerTypname&gt;&#39; stimmt nicht mit dem Zugriff &#39;&lt;Zugriffsebene2&gt;&#39; &#252;berein, der f&#252;r einen der anderen partiellen Typen angegeben wurde."
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc30925"
  - "BC30925"
helpviewer_keywords: 
  - "BC30925"
ms.assetid: aabe0f4a-dc02-4828-a837-20cd47a7bd43
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Der angegebene Zugriff &#39;&lt;Zugriffsebene1&gt;&#39; f&#252;r &#39;&lt;PartiellerTypname&gt;&#39; stimmt nicht mit dem Zugriff &#39;&lt;Zugriffsebene2&gt;&#39; &#252;berein, der f&#252;r einen der anderen partiellen Typen angegeben wurde.
Eine Klasse oder Struktur ist in mehreren partiellen Deklarationen mit Zugriffsebenenspezifikationen definiert, die miteinander in Konflikt stehen.  
  
 Wenn Sie die Definition einer Klasse oder Struktur zwischen mehreren partiellen Deklarationen aufteilen, behandelt der Compiler den Typ als die Union all seiner partiellen Deklarationen. Dies gilt nicht nur für die Member, sondern auch für die Implementierung, Vererbung und Zugriffsebene.  
  
 Sie können Zugriffsebenen in der Definition einer Klasse oder Struktur nicht mischen. Selbst die Kombination `Protected Friend` ist nur zulässig, wenn die Schlüsselwörter in der gleichen Deklarationsanweisung zusammenhängen.  
  
 **Fehler\-ID:** BC30925  
  
### So beheben Sie diesen Fehler  
  
-   Entscheiden Sie, welche Zugriffsebene die Klasse aufweisen soll, und entfernen Sie dann alle miteinander in Konflikt stehenden Zugriffsebenenspezifikationen.  
  
## Siehe auch  
 [Partial](../Topic/Partial%20\(Visual%20Basic\).md)   
 [Access Levels in Visual Basic](../Topic/Access%20Levels%20in%20Visual%20Basic.md)   
 [Class Statement](../Topic/Class%20Statement%20\(Visual%20Basic\).md)   
 [Structure Statement](../Topic/Structure%20Statement.md)   
 [NICHT IM BUILD: Klassen: Blaupausen für Objekte](assetId:///2c86373d-0333-4616-a7d8-4790c4e89f7b)   
 [Structures](../Topic/Structures%20\(Visual%20Basic\).md)