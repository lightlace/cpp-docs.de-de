---
title: "Ein Using-Operand vom Typ &#39;&lt;typname&gt;&#39; muss &#39;System.IDisposable&#39; implementieren"
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
  - "vbc36010"
  - "bc36010"
helpviewer_keywords: 
  - "BC36010"
ms.assetid: ae9ed5d5-68ba-4950-bb7a-61327fa0e7d5
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Ein Using-Operand vom Typ &#39;&lt;typname&gt;&#39; muss &#39;System.IDisposable&#39; implementieren
Eine `Using`\-Anweisung gibt eine Ressource eines Typs an, der nicht die Schnittstelle <xref:System.IDisposable> implementiert.  
  
 Der Zweck eines `Using`\-Blocks besteht darin, das Verwerfen einer Systemressource sicherzustellen, wenn der Block beendet wird. Um diesen Zweck zu erfüllen, muss die Ressource die <xref:System.IDisposable.Dispose*>\-Methode verfügbar machen, die von <xref:System.IDisposable> implementiert wird.  
  
 **Fehler\-ID:** BC36010  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die Ressource aus der Ressourcenliste der `Using`\-Anweisung, oder ersetzen Sie sie durch eine Ressource, die <xref:System.IDisposable> implementiert.  
  
## Siehe auch  
 <xref:System.IDisposable>   
 [Using Statement](../Topic/Using%20Statement%20\(Visual%20Basic\).md)   
 [How to: Dispose of a System Resource](../Topic/How%20to:%20Dispose%20of%20a%20System%20Resource%20\(Visual%20Basic\).md)