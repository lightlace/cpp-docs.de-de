---
title: "Kein(e) &quot;Prozedurname&quot; (zugreifbar) ist am spezifischsten: &lt;Signaturliste&gt;"
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
  - "vbc30794"
  - "BC30794"
helpviewer_keywords: 
  - "BC30794"
ms.assetid: 51d54cbb-b530-4661-9952-5ccc17e4220b
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Kein(e) &quot;Prozedurname&quot; (zugreifbar) ist am spezifischsten: &lt;Signaturliste&gt;
In einer Zuweisungsanordnung wird einer Delegatenvariablen die Adresse einer überladenen Prozedur zugewiesen, aber der Compiler kann nicht zwischen den überladenen Versionen auflösen.  
  
 Wenn in Code die Adresse einer Prozedur verwendet wird, die in mehreren überladenen Versionen definiert ist, muss der Compiler entscheiden, welche der Überladungen zu verwenden sind. Er versucht, eine einzelne Version anhand einer Parameterliste zu finden, die mit der Delegatenparameterliste übereinstimmt. Weitere Informationen finden Sie unter [Overload Resolution](../Topic/Overload%20Resolution%20\(Visual%20Basic\).md).  
  
 Findet der Compiler mehrere Versionen der Prozedur mit einer übereinstimmenden Signatur, generiert er diesen Fehler. Dies kann z. B. vorkommen, wenn eine der Überladungen generisch ist und ein Typargument an sie übergeben wird, mit dem ihr eine Signatur mitgeteilt wird, die mit derjenigen einer anderen Überladung übereinstimmt.  
  
 **Fehler\-ID:** BC30794  
  
### So beheben Sie diesen Fehler  
  
-   Wird der Konflikt durch eine generische Überladung verursacht, die dieselbe Signatur hat wie eine andere Überladung, ändern Sie das Typargument, das an diese generische Überladung übergeben wird.  
  
## Siehe auch  
 [AddressOf Operator](../Topic/AddressOf%20Operator%20\(Visual%20Basic\).md)   
 [Delegate Statement](../Topic/Delegate%20Statement.md)   
 [NICHT IM BUILD: Delegaten und der AddressOf\-Operator](assetId:///7b2ed932-8598-4355-b2f7-5cedb23ee86f)   
 [Overload Resolution](../Topic/Overload%20Resolution%20\(Visual%20Basic\).md)   
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)