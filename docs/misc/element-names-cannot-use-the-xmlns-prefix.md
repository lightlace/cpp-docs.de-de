---
title: "In Elementnamen darf das Pr&#228;fix &quot;xmlns&quot; nicht verwendet werden."
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
  - "vbc31189"
  - "bc31189"
helpviewer_keywords: 
  - "BC31189"
ms.assetid: 88716bb5-6766-4180-b2ed-1d1bee0ff7a6
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "shoag"
manager: "wpickett"
---
# In Elementnamen darf das Pr&#228;fix &quot;xmlns&quot; nicht verwendet werden.
Ein XML\-Elementliteral wurde mit dem XML\-Namespacepräfix `xmlns` angegeben. Zum Beispiel:  
  
```vb#  
Dim elem = <xmlns:ElementName>  
```  
  
 Die XML 1.0\-Spezifikation gibt `xmlns` als ein reserviertes Wort an.  
  
 **Fehler\-ID:** BC31189  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie das XML\-Namespacepräfix in einen gültigen Wert, oder entfernen Sie das Präfix.  
  
## Siehe auch  
 [XML Literals](../Topic/XML%20Literals%20\(Visual%20Basic\).md)   
 [Imports Statement \(XML Namespace\)](../Topic/Imports%20Statement%20\(XML%20Namespace\).md)   
 [XML](../Topic/XML%20in%20Visual%20Basic.md)