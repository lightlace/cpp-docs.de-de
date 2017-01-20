---
title: "„New“ kann nicht f&#252;r eine Schnittstelle verwendet werden."
ms.custom: na
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc30375"
  - "bc30375"
helpviewer_keywords: 
  - "BC30375"
ms.assetid: c1e06108-1b52-4cbe-8cae-e816a0dbac0b
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# „New“ kann nicht f&#252;r eine Schnittstelle verwendet werden.
Eine [Dim Statement](../Topic/Dim%20Statement%20\(Visual%20Basic\).md) verwendet eine [New Operator](../Topic/New%20Operator%20\(Visual%20Basic\).md)\-Klausel, wenn eine Variable als Schnittstellentyp deklariert wird.  
  
 Obwohl eine Schnittstelle ein Verweistyp ist, können Sie keine Instanz von ihr erstellen. Sie können `New` nur zum Erstellen einer Instanz einer Klasse oder einer Struktur verwenden.  
  
 **Fehler\-ID:** BC30375  
  
### So beheben Sie diesen Fehler  
  
1.  Wenn die Variable einen Schnittstellentyp aufweisen soll, entfernen Sie das `New`\-Schlüsselwort.  
  
2.  Wenn die Variable auf eine Instanz verweisen soll, deklarieren Sie sie als Klassen\- oder Strukturtyp. Behalten Sie das `New`\-Schlüsselwort bei, um eine Instanz zu erstellen.  
  
## Siehe auch  
 [Interface Statement](../Topic/Interface%20Statement%20\(Visual%20Basic\).md)   
 [Class Statement](../Topic/Class%20Statement%20\(Visual%20Basic\).md)   
 [Structure Statement](../Topic/Structure%20Statement.md)