---
title: "TryCast erfordert einen Verweistyp als Operanden, &quot;&lt;Typname&gt;&quot; ist jedoch ein Werttyp."
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
  - "BC30792"
  - "vbc30792"
helpviewer_keywords: 
  - "BC30792"
ms.assetid: 3325fce5-dbc0-4d1d-9530-31f4720bfe6e
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# TryCast erfordert einen Verweistyp als Operanden, &quot;&lt;Typname&gt;&quot; ist jedoch ein Werttyp.
Der `TryCast`\-Operator wird mit einem Werttyp für mindestens eines der Argumente verwendet.  
  
 `TryCast` überprüft, ob eine Vererbungs\- oder Implementierungsbeziehung zwischen den beiden Argumenten vorliegt. Daher sind nur Verweistypen für die Argumente zulässig. Weitere Informationen finden Sie unter [Value Types and Reference Types](../Topic/Value%20Types%20and%20Reference%20Types.md).  
  
 **Fehler\-ID:** BC30792  
  
### So beheben Sie diesen Fehler  
  
-   Verwenden Sie `DirectCast` oder `CType`, um die Konvertierung auszuführen. In beiden Fällen sind Werttypen zulässig.  
  
## Siehe auch  
 [TryCast Operator](../Topic/TryCast%20Operator%20\(Visual%20Basic\).md)   
 [DirectCast Operator](../Topic/DirectCast%20Operator%20\(Visual%20Basic\).md)   
 [CType\-Funktion](../Topic/CType%20Function%20\(Visual%20Basic\).md)   
 [Value Types and Reference Types](../Topic/Value%20Types%20and%20Reference%20Types.md)