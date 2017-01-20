---
title: "Eine Namespacedeklaration mit Pr&#228;fix darf in einem XML-Literal keinen leeren Wert haben."
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
  - "bc31184"
  - "vbc31184"
helpviewer_keywords: 
  - "BC31184"
ms.assetid: dde656b4-df3b-4a2e-8871-4e14832ca778
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "shoag"
manager: "wpickett"
---
# Eine Namespacedeklaration mit Pr&#228;fix darf in einem XML-Literal keinen leeren Wert haben.
Eine XML\-Namespacedeklaration in einem XML\-Literal enthält keinen Namespacewert. Beispielsweise verursacht der folgende Code diesen Fehler:  
  
```vb#  
Dim book = <book xmlns:ns=""/>  
```  
  
 **Fehler\-ID:** BC31184  
  
### So beheben Sie diesen Fehler  
  
-   Schließen Sie einen gültigen Namespace in die XML\-Namespacedeklaration ein, oder entfernen Sie die XML\-Namespacedeklaration aus dem XML\-Literal.  
  
     Als Alternative können Sie die `Imports`\-Anweisung verwenden, um ein Namespacepräfix für den leeren Namespace zu erkennen. Zum Beispiel:  
  
    ```vb#  
    Imports <xmlns:ns="">  
    ```  
  
## Siehe auch  
 [XML Literals](../Topic/XML%20Literals%20\(Visual%20Basic\).md)   
 [XML](../Topic/XML%20in%20Visual%20Basic.md)   
 [Imports Statement \(XML Namespace\)](../Topic/Imports%20Statement%20\(XML%20Namespace\).md)