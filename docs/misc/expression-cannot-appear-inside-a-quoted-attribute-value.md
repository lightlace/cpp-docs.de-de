---
title: "In einem Attributwert in Anf&#252;hrungszeichen d&#252;rfen keine Ausdr&#252;cke enthalten sein."
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
  - "bc31155"
  - "vbc31155"
helpviewer_keywords: 
  - "BC31155"
ms.assetid: ed3e618e-de94-4e4e-afaf-72b11073fb1d
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "shoag"
manager: "wpickett"
---
# In einem Attributwert in Anf&#252;hrungszeichen d&#252;rfen keine Ausdr&#252;cke enthalten sein.
In einem Attributwert in Anführungszeichen dürfen keine Ausdrücke enthalten sein. Entfernen Sie die Anführungszeichen.  
  
 Ein eingebetteter Ausdruck in einem Attributwert für ein XML\-Literal wird in Anführungszeichen eingeschlossen.  
  
 **Fehler\-ID:** BC31155  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die begrenzenden Anführungszeichen aus dem Attributwert. Im Folgenden finden Sie ein Beispiel dazu:  
  
    ```vb#  
    ' Generates an error. Dim elem = <outer attr="<%= value %>" /> ' Does not generate an error. Dim elem = <outer attr=<%= value %> />  
    ```  
  
## Siehe auch  
 [Embedded Expressions in XML](../Topic/Embedded%20Expressions%20in%20XML%20\(Visual%20Basic\).md)   
 [XML Literals](../Topic/XML%20Literals%20\(Visual%20Basic\).md)   
 [XML](../Topic/XML%20in%20Visual%20Basic.md)