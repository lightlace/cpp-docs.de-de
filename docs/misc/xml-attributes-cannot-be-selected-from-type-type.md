---
title: "XML-Attribute k&#246;nnen nicht vom Typ &quot;type&quot; ausgew&#228;hlt werden"
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
  - "bc36808"
  - "vbc36808"
helpviewer_keywords: 
  - "BC36808"
ms.assetid: 76b2605c-3d9b-4e56-ba3f-99c60c668290
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "shoag"
manager: "wpickett"
---
# XML-Attribute k&#246;nnen nicht vom Typ &quot;type&quot; ausgew&#228;hlt werden
Mit einem XML\-Attribut wurde auf ein Objekt verwiesen, das nicht vom Typ <xref:System.Xml.Linq.XElement> oder `IEnumerable(Of XElement)` ist. Weitere Informationen finden Sie unter [XML Attribute Axis Property](../Topic/XML%20Attribute%20Axis%20Property%20\(Visual%20Basic\).md).  
  
```vb#  
' Generates an error. Dim var = "sample text".@attr  
```  
  
 **Fehler\-ID:** BC36808  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass das Objekt, mit dem Sie auf ein Attribut verweisen, stark typisiert als <xref:System.Xml.Linq.XElement> oder `IEnumerable(Of XElement)` ist. Beachten Sie folgendes Beispiel:  
  
    ```vb#  
    Dim elem As XElement = <root attr="value"/> Dim var = elem.@attr  
    ```  
  
## Siehe auch  
 [XML Attribute Axis Property](../Topic/XML%20Attribute%20Axis%20Property%20\(Visual%20Basic\).md)   
 [XML Axis Properties](../Topic/XML%20Axis%20Properties%20\(Visual%20Basic\).md)   
 [XML](../Topic/XML%20in%20Visual%20Basic.md)