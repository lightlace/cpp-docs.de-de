---
title: "&#39;Handles&#39; muss in Klassen eine WithEvents-Variable angeben. &#39;MyBase&#39;, &#39;MyClass&#39; oder &#39;Me&#39; wurde durch einen einzelnen Bezeichner qualifiziert."
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
  - "bc31412"
  - "vbc31412"
helpviewer_keywords: 
  - "BC31412"
ms.assetid: acbefc38-448a-4afa-90c2-77389415d618
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Handles&#39; muss in Klassen eine WithEvents-Variable angeben. &#39;MyBase&#39;, &#39;MyClass&#39; oder &#39;Me&#39; wurde durch einen einzelnen Bezeichner qualifiziert.
Um einen Ereignishandler anzugeben, müssen `Handles`\-Anweisungen entweder eine mit dem Schlüsselwort `WithEvents` deklarierte Objektvariable oder einen mit dem Schlüsselwort `MyBase` qualifizierten Member angeben.  
  
 **Fehler\-ID:** BC31412  
  
### So beheben Sie diesen Fehler  
  
1.  Verwenden Sie den `WithEvents`\-Modifizierer, um die Variablen zu deklarieren, die mit der `Handles`\-Anweisung verwendet werden können.  
  
2.  Geben Sie den Namen eines Ereignisses für die aktuelle Klasse in der Basisklasse an.  
  
## Siehe auch  
 [Handles](../Topic/Handles%20Clause%20\(Visual%20Basic\).md)   
 [WithEvents](../Topic/WithEvents%20\(Visual%20Basic\).md)   
 [Events](../Topic/Events%20\(Visual%20Basic\).md)