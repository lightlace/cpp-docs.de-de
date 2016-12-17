---
title: "Der Variablentyp f&#252;r Using-Ressourcen kann kein Arraytyp sein."
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
  - "vbc36012"
  - "bc36012"
helpviewer_keywords: 
  - "BC36012"
ms.assetid: f98c54b0-6ede-48b6-aa31-438664c219f3
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# Der Variablentyp f&#252;r Using-Ressourcen kann kein Arraytyp sein.
Eine `Using`\-Anweisung gibt eine Arrayvariable für eine Ressource an.  
  
 Die <xref:System.Array>\-Klasse implementiert die <xref:System.IDisposable>\-Schnittstelle nicht, daher kann der `Using`\-Block die <xref:System.IDisposable.Dispose*>\-Methode für eine Arrayressource nicht aufrufen.  
  
 **Fehler\-ID:** BC36012  
  
### So beheben Sie diesen Fehler  
  
-   Verwenden Sie einen anderen Typ von Systemressource im `Using`\-Block.  
  
## Siehe auch  
 [Using Statement](../Topic/Using%20Statement%20\(Visual%20Basic\).md)   
 [How to: Dispose of a System Resource](../Topic/How%20to:%20Dispose%20of%20a%20System%20Resource%20\(Visual%20Basic\).md)   
 [NOTINBUILD: Übersicht über Arrays in Visual Basic](assetId:///ca50e2f2-b4d2-4c57-9169-9abbcc3392d8)