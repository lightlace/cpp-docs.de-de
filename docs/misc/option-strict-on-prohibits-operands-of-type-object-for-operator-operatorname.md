---
title: "„Option Strict On“ l&#228;sst keine Operanden des Typs &#39;Object&#39; f&#252;r den &#39;&lt;Operatorname&gt;&#39;-Operator zu."
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
  - "bc30038"
  - "vbc30038"
helpviewer_keywords: 
  - "BC30038"
ms.assetid: eb047d36-1fb4-460d-ae98-c76f31a89bed
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# „Option Strict On“ l&#228;sst keine Operanden des Typs &#39;Object&#39; f&#252;r den &#39;&lt;Operatorname&gt;&#39;-Operator zu.
Die einzigen für Objektvariablen definierten Operatoren sind `Is` und `TypeOf...Is`. Wenn `Option Strict` dem Wert `On` entspricht, müssen alle Operanden Datentypen sein, die für den angegebenen Operator definiert wurden.  
  
 **Fehler\-ID:** BC30038  
  
### So beheben Sie diesen Fehler  
  
-   Verwenden Sie die entsprechenden Typkonvertierungsfunktionen wie `CInt` oder `CStr`, um die Operanden in Datentypen zu konvertieren, die für den Operator definiert wurden.  
  
## Siehe auch  
 [Is Operator](../Topic/Is%20Operator%20\(Visual%20Basic\).md)   
 [Comparison Operators in Visual Basic](../Topic/Comparison%20Operators%20in%20Visual%20Basic.md)   
 [Type Conversion Functions](../Topic/Type%20Conversion%20Functions%20\(Visual%20Basic\).md)