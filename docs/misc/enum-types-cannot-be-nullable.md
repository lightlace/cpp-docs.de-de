---
title: "Enumerationstypen k&#246;nnen keine NULL-Werte zulassen"
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
  - "vbc32129"
  - "bc32129"
helpviewer_keywords: 
  - "BC32129"
ms.assetid: 9e0fe5c9-72c7-4905-b177-d00cc3469ea9
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "shoag"
manager: "wpickett"
---
# Enumerationstypen k&#246;nnen keine NULL-Werte zulassen
Der zugrunde liegende Typ, der verwendet wird, um eine Enumeration zu deklarieren, kann keine NULL\-Werte zulassen. Beispielsweise verursacht der folgende Code diesen Fehler:  
  
```vb#  
'' Not valid. ' Enum exampleEnum As Integer? '     Member declarations. ' End Enum  
```  
  
 **Fehler\-ID:** BC32129  
  
### So beheben Sie diesen Fehler  
  
-   Verwenden Sie in einer `Enum`\-Deklaration keinen zugrunde liegenden Typ, der keine NULL\-Werte zulassen kann.  
  
## Siehe auch  
 [Nullable Value Types](../Topic/Nullable%20Value%20Types%20\(Visual%20Basic\).md)   
 [Enum Statement](../Topic/Enum%20Statement%20\(Visual%20Basic\).md)