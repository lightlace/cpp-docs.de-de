---
title: "Der Typparametername &quot;&lt;Typparametername1&gt;&quot; stimmt nicht mit dem Namen &quot;&lt;Typparametername2&gt;&quot; des entsprechenden Typparameters &#252;berein, der f&#252;r einen der anderen partiellen Typen von &quot;&lt;Name des partiellen Typs&gt;&quot; definiert wurde."
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
  - "vbc30931"
  - "bc30931"
helpviewer_keywords: 
  - "BC30931"
ms.assetid: 01b053c3-d1b5-4e69-b908-3d5cfc73913b
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Der Typparametername &quot;&lt;Typparametername1&gt;&quot; stimmt nicht mit dem Namen &quot;&lt;Typparametername2&gt;&quot; des entsprechenden Typparameters &#252;berein, der f&#252;r einen der anderen partiellen Typen von &quot;&lt;Name des partiellen Typs&gt;&quot; definiert wurde.
Eine generische Klasse oder Struktur ist in mehreren partiellen Deklarationen mit Typparameterspezifikationen definiert, die miteinander in Konflikt stehen.  
  
 Wenn Sie die Definition einer Klasse oder Struktur zwischen mehreren partiellen Deklarationen aufteilen, behandelt der Compiler den Typ als die Union all seiner partiellen Deklarationen. Dies gilt nicht nur für die Member, sondern auch für die Implementierung, Vererbung und Zugriffsebene.  
  
 Sie können für einen Typparameter in der Definition einer generischen Klasse oder Struktur nicht mehrere Namen angeben.  
  
 **Fehler\-ID:** BC30931  
  
### So beheben Sie diesen Fehler  
  
-   Entscheiden Sie, welchen Namen der Typparameter aufweisen soll, und verwenden Sie in jeder partiellen Deklaration denselben Namen.  
  
## Siehe auch  
 [Partial](../Topic/Partial%20\(Visual%20Basic\).md)   
 [Class Statement](../Topic/Class%20Statement%20\(Visual%20Basic\).md)   
 [Structure Statement](../Topic/Structure%20Statement.md)   
 [NICHT IM BUILD: Klassen: Blaupausen für Objekte](assetId:///2c86373d-0333-4616-a7d8-4790c4e89f7b)   
 [Structures](../Topic/Structures%20\(Visual%20Basic\).md)   
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)