---
title: "Die MustOverride-Methode &#39;&lt;Methodenname&gt;&#39; kann nicht mit &#39;MyClass&#39; aufgerufen werden."
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
  - "bc30614"
  - "vbc30614"
helpviewer_keywords: 
  - "BC30614"
ms.assetid: fc57af41-1552-46d1-9727-341f1835e661
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Die MustOverride-Methode &#39;&lt;Methodenname&gt;&#39; kann nicht mit &#39;MyClass&#39; aufgerufen werden.
`MyClass` ist identisch zu `Me`, aber alle zugehörigen Methodenaufrufe werden so behandelt, als wäre `NotOverridable` die aufgerufene Methode.  
  
 **Fehler\-ID:** BC30614  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie den `MustOverride`\-Modifizierer, oder deklarieren Sie die Methode in einer Basisklasse, um diese Klassen anschließend zu vererben und zu überschreiben.  
  
## Siehe auch  
 [MustOverride](../Topic/MustOverride%20\(Visual%20Basic\).md)   
 [MustInherit](../Topic/MustInherit%20\(Visual%20Basic\).md)   
 [NotOverridable](../Topic/NotOverridable%20\(Visual%20Basic\).md)