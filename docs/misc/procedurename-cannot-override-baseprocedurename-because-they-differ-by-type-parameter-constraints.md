---
title: "&quot;&lt;Prozedurname&gt;&quot; kann &quot;&lt;Basisprozedurname&gt;&quot; nicht &#252;berschreiben, da sie unterschiedliche Typparametereinschr&#228;nkungen aufweisen."
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
  - "BC32077"
  - "vbc32077"
helpviewer_keywords: 
  - "BC32077"
ms.assetid: 9be1a88d-c1a4-4f12-8e72-74abb2be565d
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;&lt;Prozedurname&gt;&quot; kann &quot;&lt;Basisprozedurname&gt;&quot; nicht &#252;berschreiben, da sie unterschiedliche Typparametereinschr&#228;nkungen aufweisen.
Eine generische Prozedur versucht, eine generische Basisklassenprozedur zu überschreiben, aber sie verfügen über unterschiedliche Einschränkungslisten für ihre Typparameter.  
  
 Um eine Basisklassenprozedur zu überschreiben, muss die überschreibende Prozedur nicht nur mit der vollständigen Signatur der Basisklassenprozedur, sondern auch mit der Zugriffsebene der Prozedur und dem Übergabemechanismus jedes Parameters übereinstimmen.  
  
 Um eine generische Basisklassenprozedur zu überschreiben, muss die überschreibende Prozedur zusätzlich mit der Anzahl der Typparameter und der Einschränkungsliste jedes Parameters übereinstimmen.  
  
 Weitere Informationen zu Überschreibungsanforderungen finden Sie unter [Overrides](../Topic/Overrides%20\(Visual%20Basic\).md).  
  
 **Fehler\-ID:** BC32077  
  
### So beheben Sie diesen Fehler  
  
-   Wenn Sie beabsichtigen, die Basisklassenprozedur zu überschreiben, überarbeiten Sie die Typparametereinschränkungen, um sie genau auf die Einschränkungen der Basisklassenprozedur abzustimmen.  
  
-   Wenn die Typparametereinschränkungen unverändert beibehalten werden müssen, können Sie die Basisklassenprozedur nicht überschreiben. Entfernen Sie das `Overrides`\-Schlüsselwort aus der Deklaration.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)