---
title: "&#39;prefix&#39; ist ein XML-Pr&#228;fix und kann nicht als Ausdruck verwendet werden"
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
  - "bc30114"
  - "vbc30114"
helpviewer_keywords: 
  - "BC30114"
ms.assetid: 5cb7c89e-c61b-483a-9369-5285b7cbcf45
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;prefix&#39; ist ein XML-Pr&#228;fix und kann nicht als Ausdruck verwendet werden
'prefix' ist ein XML\-Präfix und kann nicht als Ausdruck verwendet werden. Verwenden Sie die GetXmlNamespace\-Operator, um ein Namespaceobjekt zu erstellen.  
  
 Das Präfix für einen XML\-Namespace, der mithilfe der `Imports`\-Anweisung importiert wird, kann nicht außerhalb eines XML\-Literals verwendet werden.  
  
 **Fehler\-ID:** BC30114  
  
### So beheben Sie diesen Fehler  
  
-   Wenn Sie auf einen Teil des importierten XML\-Namespaces verweisen müssen, verwenden Sie den `GetXmlNamespace`\-Operator, um ein <xref:System.Xml.Linq.XNamespace>\-Objekt abzurufen. Verwenden Sie dieses Objekt anstelle des XML\-Namespacepräfixes.  
  
-   Wenn Sie das XML\-Namespacepräfix verwenden, um ein XML\-Literal zu qualifizieren, stellen Sie sicher, dass Sie die entsprechende Syntax für das XML\-Literal verwenden.  
  
## Siehe auch  
 [XML Literals](../Topic/XML%20Literals%20\(Visual%20Basic\).md)   
 [Imports Statement \(XML Namespace\)](../Topic/Imports%20Statement%20\(XML%20Namespace\).md)   
 [GetXmlNamespace Operator](../Topic/GetXmlNamespace%20Operator%20\(Visual%20Basic\).md)   
 [XML](../Topic/XML%20in%20Visual%20Basic.md)   
 [Introduction to LINQ in Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)