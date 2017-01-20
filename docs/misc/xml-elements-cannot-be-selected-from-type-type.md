---
title: "XML-Elemente k&#246;nnen nicht vom Typ &quot;Typ&quot; ausgew&#228;hlt werden."
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
  - "vbc36807"
  - "bc36807"
helpviewer_keywords: 
  - "BC36807"
ms.assetid: 01c19899-2b44-41e9-a99c-35edfa0deaf1
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "shoag"
manager: "wpickett"
---
# XML-Elemente k&#246;nnen nicht vom Typ &quot;Typ&quot; ausgew&#228;hlt werden.
Für ein Objekt, das nicht vom Typ <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XDocument> oder `IEnumerable(Of XElement)` ist, wurde auf ein untergeordnetes XML\-Element verwiesen. Weitere Informationen finden Sie unter [XML Child Axis Property](../Topic/XML%20Child%20Axis%20Property%20\(Visual%20Basic\).md).  
  
```vb#  
' Generates an error. Dim var = "sample text".<child>  
```  
  
 **Fehler\-ID:** BC36807  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass das Objekt, auf dessen Attribut Sie verweisen, als <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XDocument> oder `IEnumerable(Of XElement)` stark typisiert ist. Beachten Sie folgendes Beispiel:  
  
    ```vb#  
    Dim elem As XElement = <root> <child /> </root> Dim var = elem.<child>  
    ```  
  
## Siehe auch  
 [XML Child Axis Property](../Topic/XML%20Child%20Axis%20Property%20\(Visual%20Basic\).md)   
 [XML Axis Properties](../Topic/XML%20Axis%20Properties%20\(Visual%20Basic\).md)   
 [XML](../Topic/XML%20in%20Visual%20Basic.md)