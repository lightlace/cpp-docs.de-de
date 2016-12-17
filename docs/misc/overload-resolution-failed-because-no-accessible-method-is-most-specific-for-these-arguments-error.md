---
title: "Fehler bei der &#220;berladungsaufl&#246;sung, da keine zugreifbare &#39;&lt;Methode&gt;&#39; f&#252;r diese Argumente am spezifischsten ist: &lt;Fehler&gt;"
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
  - "bc30521"
  - "vbc30521"
helpviewer_keywords: 
  - "Auflösungsfehler"
  - "BC30521"
  - "Fehler bei der Überladungsauflösung"
ms.assetid: b8b41fa0-a64b-4e74-8443-be3afd2b6f11
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Fehler bei der &#220;berladungsaufl&#246;sung, da keine zugreifbare &#39;&lt;Methode&gt;&#39; f&#252;r diese Argumente am spezifischsten ist: &lt;Fehler&gt;
Sie haben eine überladene Methode aufgerufen, aber der Compiler hat zwei oder mehr Überladungen mit Parameterlisten gefunden, in die Ihre Argumentliste konvertiert werden kann, und der Compiler ist nicht in der Lage, die Auswahl zu treffen.  
  
 Der Compiler versucht, die Datentypen in der aufrufenden Argumentliste weitestgehend mit der Liste der Überladungsparameter zu vergleichen. Es ist eine erweiternde Konvertierung jedes Arguments in den entsprechenden Parameter erforderlich, unabhängig davon, ob der Schalter für die Typüberprüfung \([Option Strict Statement](../Topic/Option%20Strict%20Statement.md)\) `On` oder `Off` ist.  
  
 Wenn der Compiler mehrere Überladungen findet, die die Erweiterungsanforderung erfüllen, dann sucht er nach der Überladung, die für die Argumentdatentypen am genauesten bestimmt ist, also die geringste Erweiterung erfordert. Der Compiler generiert diese Fehlermeldung, wenn eine Überladung für einen Argumentdatentyp genauer bestimmt ist, während eine andere Überladung für einen anderen Argumentdatentyp genauer bestimmt ist. Weitere Informationen und ein Beispiel finden Sie unter [Overload Resolution](../Topic/Overload%20Resolution%20\(Visual%20Basic\).md).  
  
 **Fehler\-ID:** BC30521  
  
### So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie alle Überladungen der Methode und bestimmen Sie, welche aufgerufen werden soll.  
  
2.  Stellen Sie in der aufrufenden Anweisung sicher, dass die Datentypen der Argumente mit den Datentypen der Parameter übereinstimmen, die für die gewünschte Überladung definiert wurden. Möglicherweise müssen Sie die [CType\-Funktion](../Topic/CType%20Function%20\(Visual%20Basic\).md) verwenden, um einen oder mehrere Datentypen in die definierten Typen zu konvertieren.  
  
## Siehe auch  
 [Procedure Overloading](../Topic/Procedure%20Overloading%20\(Visual%20Basic\).md)   
 [Considerations in Overloading Procedures](../Topic/Considerations%20in%20Overloading%20Procedures%20\(Visual%20Basic\).md)   
 [Overload Resolution](../Topic/Overload%20Resolution%20\(Visual%20Basic\).md)   
 [Overloads](../Topic/Overloads%20\(Visual%20Basic\).md)   
 [Overloaded Properties and Methods](../Topic/Overloaded%20Properties%20and%20Methods%20\(Visual%20Basic\).md)   
 [Option Strict Statement](../Topic/Option%20Strict%20Statement.md)   
 [CType\-Funktion](../Topic/CType%20Function%20\(Visual%20Basic\).md)