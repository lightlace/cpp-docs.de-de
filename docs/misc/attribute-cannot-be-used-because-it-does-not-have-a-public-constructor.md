---
title: "Das Attribut konnte nicht verwendet werden, da es keinen Public-Konstruktor hat."
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc30758"
  - "bc30758"
helpviewer_keywords: 
  - "BC30758"
ms.assetid: b72d1ff2-f6b2-4a89-9ac2-8765f77bcc97
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "shoag"
manager: "wpickett"
---
# Das Attribut konnte nicht verwendet werden, da es keinen Public-Konstruktor hat.
Der Konstruktor für das verwendete Attribut ist `Private` und kann nicht verwendet werden.  
  
 **Fehler\-ID:** BC30758  
  
### So beheben Sie diesen Fehler  
  
1.  Wenn dieser Fehler mit einem benutzerdefinierten Attribut angezeigt wird, das Sie entwickelt haben, ändern Sie den Zugriffsmodifizierer seines `Sub``New`\-Konstruktors in `Public`.  
  
## Siehe auch  
 [NICHT IM BUILD: Attribute in Visual Basic](assetId:///620bfc0e-4582-4c8b-8432-ebc5c3dccc22)   
 [Object Lifetime: How Objects Are Created and Destroyed](../Topic/Object%20Lifetime:%20How%20Objects%20Are%20Created%20and%20Destroyed%20\(Visual%20Basic\).md)