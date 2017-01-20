---
title: "Typen, die NULL-Werte zulassen, sind in Ausdr&#252;cken f&#252;r die bedingte Kompilierung nicht zul&#228;ssig."
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
  - "bc33111"
  - "vbc33111"
helpviewer_keywords: 
  - "BC33111"
ms.assetid: 2c2587e5-2179-4a31-bcf7-7004db6f2d73
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "shoag"
manager: "wpickett"
---
# Typen, die NULL-Werte zulassen, sind in Ausdr&#252;cken f&#252;r die bedingte Kompilierung nicht zul&#228;ssig.
Ein Typ, der NULL\-Werte zulässt, kann nicht im Ausdruck eine Direktive für die bedingte Kompilierung verwendet werden. Beispielsweise verursacht der folgende Code diesen Fehler.  
  
```vb#  
'#Const triggerPoint = 0 '' Not valid. '#If CType(triggerpoint, Boolean?) = True Then '        ' Body of the conditional directive. '#End If  
```  
  
 **Fehler\-ID:** BC33111  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die Typbezeichnung, die NULL\-Werte zulässt.  
  
## Siehe auch  
 [Nullable Value Types](../Topic/Nullable%20Value%20Types%20\(Visual%20Basic\).md)   
 [\#If...Then...\#Else Directives](../Topic/%23If...Then...%23Else%20Directives.md)   
 [Conditional Compilation](../Topic/Conditional%20Compilation%20in%20Visual%20Basic.md)