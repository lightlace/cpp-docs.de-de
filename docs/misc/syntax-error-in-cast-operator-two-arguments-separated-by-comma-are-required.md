---
title: "Syntaxfehler in Umwandlungsoperator; zwei durch Komma getrennte Argumente sind erforderlich."
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
  - "vbc30944"
  - "bc30944"
helpviewer_keywords: 
  - "BC30944"
ms.assetid: 1f7ed4a1-6ff5-4836-8424-21618c68ff45
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "shoag"
manager: "wpickett"
---
# Syntaxfehler in Umwandlungsoperator; zwei durch Komma getrennte Argumente sind erforderlich.
Ein Ausdruck verwendet die `CType`\-Konvertierungsfunktion oder das Konvertierungsschlüsselwort `DirectCast` oder `TryCast`, gibt jedoch nur ein Argument an.  
  
 Für `CType`, `DirectCast` und `TryCast` sind jeweils zwei Argumente erforderlich. Das erste ist ein zu konvertierender Ausdruck, und das zweite ist der Datentyp oder Klassentyp, zu dem die Konvertierung erfolgen soll.  
  
 **Fehler\-ID:** BC30944  
  
### So beheben Sie diesen Fehler  
  
-   Geben Sie beide Argumente als für die Konvertierung erforderlich an.  
  
-   Wenn Sie eine der spezifischen [Type Conversion Functions](../Topic/Type%20Conversion%20Functions%20\(Visual%20Basic\).md), wie etwa `CString`, verwenden möchten, müssen Sie diesen Funktionsnamen anstelle von `CType` verwenden. Dann ist nur ein Argument erforderlich.  
  
## Siehe auch  
 [CType\-Funktion](../Topic/CType%20Function%20\(Visual%20Basic\).md)   
 [DirectCast Operator](../Topic/DirectCast%20Operator%20\(Visual%20Basic\).md)   
 [TryCast Operator](../Topic/TryCast%20Operator%20\(Visual%20Basic\).md)   
 [Type Conversion Functions](../Topic/Type%20Conversion%20Functions%20\(Visual%20Basic\).md)