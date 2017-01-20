---
title: "Die Eigenschaft kann nicht als &quot;&lt;Eigenschaftenmodifizierer&gt;&quot; deklariert werden, da sie einen &quot;Private&quot;-Accessor enth&#228;lt"
ms.custom: na
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc31108"
  - "bc31108"
helpviewer_keywords: 
  - "BC31108"
ms.assetid: 74fb36f4-54cd-4fda-bcc6-e965b5c7c37b
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Die Eigenschaft kann nicht als &quot;&lt;Eigenschaftenmodifizierer&gt;&quot; deklariert werden, da sie einen &quot;Private&quot;-Accessor enth&#228;lt
Eine Eigenschaft mit einer `Private`\-Eigenschaftenprozedur \(`Get` oder `Set`\) wird als [Overridable](../Topic/Overridable%20\(Visual%20Basic\).md) gekennzeichnet.  
  
 Ist eine Eigenschaft oder Prozedur einer Basisklasse als [Private](../Topic/Private%20\(Visual%20Basic\).md) deklariert, kann diese Eigenschaft oder Prozedur nicht von einer abgeleiteten Klasse überschrieben werden, da diese nicht auf die Eigenschaft oder Prozedur zugreifen kann. Daher können Sie `Private` nicht in Verbindung mit `Overridable` verwenden. Dies gilt nicht nur für die Eigenschaft selbst, sondern auch für die einzelnen Eigenschaftenprozeduren.  
  
 **Fehler\-ID:** BC31108  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie das `Overridable`\-Schlüsselwort aus der [Property Statement](../Topic/Property%20Statement.md), oder entfernen Sie das `Private`\-Schlüsselwort aus der [Get Statement](../Topic/Get%20Statement.md) oder der [Set Statement](../Topic/Set%20Statement%20\(Visual%20Basic\).md).  
  
## Siehe auch  
 [Eigenschaftenprozeduren](../Topic/Property%20Procedures%20\(Visual%20Basic\).md)   
 [How to: Declare a Property with Mixed Access Levels](../Topic/How%20to:%20Declare%20a%20Property%20with%20Mixed%20Access%20Levels%20\(Visual%20Basic\).md)