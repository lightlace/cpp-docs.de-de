---
title: "&lt;Typ&gt;-Parameter k&#246;nnen nicht als &#39;Optional&#39; deklariert werden."
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
  - "bc33010"
  - "vbc33010"
helpviewer_keywords: 
  - "BC33010"
ms.assetid: ec4023e7-9ba6-4532-a6b9-4ae6b4f9063a
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;Typ&gt;-Parameter k&#246;nnen nicht als &#39;Optional&#39; deklariert werden.
Eine Definition eines Delegaten, Ereignisses oder Operators deklariert einen [Optional](../Topic/Optional%20\(Visual%20Basic\).md)\-Parameter.  
  
 `Optional`\-Parameter sind nur für `Declare`\-, `Function`\-, `Property`\- und `Sub`\-Parameter gestattet.  
  
 **Fehler\-ID:** BC33010  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie das `Optional`\-Schlüsselwort aus der Parameterliste.  
  
-   Wenn Sie einen Operator definieren, können Sie möglicherweise die `Optional`\-Funktionalität durch eine Reihe von Überladungen erreichen.  
  
-   Wenn Sie einen Delegaten oder ein Ereignis definieren, müssen Sie die Gesamtlogik dieses Teils der Anwendung überarbeiten. Sie können keine `Optional`\- oder [ParamArray](../Topic/ParamArray%20\(Visual%20Basic\).md)\-Parameter oder überladene Versionen für Delegat\- oder Ereignisparameter verwenden.  
  
## Siehe auch  
 [Overloads](../Topic/Overloads%20\(Visual%20Basic\).md)   
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Operator Statement](../Topic/Operator%20Statement.md)