---
title: "&#39;&lt;Klassenname1&gt;&#39; kann nicht vom &lt;Typ&gt; &#39;&lt;Klassenname2&gt;&#39; erben, da &#39;&lt;Klassenname2&gt;&#39; als &#39;NotInheritable&#39; deklariert ist."
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
  - "vbc30299"
  - "bc30299"
helpviewer_keywords: 
  - "BC30299"
ms.assetid: 627d50f5-9e75-495d-93f7-50096ba2ea08
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;Klassenname1&gt;&#39; kann nicht vom &lt;Typ&gt; &#39;&lt;Klassenname2&gt;&#39; erben, da &#39;&lt;Klassenname2&gt;&#39; als &#39;NotInheritable&#39; deklariert ist.
Eine Klasse versucht, von einer anderen Klasse zu erben, aber die gewünschte Basisklasse ist als `NotInheritable` angegeben.`NotInheritable`\-Klassen dienen in erster Linie zum Verhindern von unbeabsichtigten Ableitungen.  
  
 **Fehler\-ID:** BC30299  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie das `NotInheritable`\-Schlüsselwort aus der Definition der gewünschten Basisklasse, oder entfernen Sie die `Inherits`\-Anweisung.  
  
## Siehe auch  
 [Inheritance Basics](../Topic/Inheritance%20Basics%20\(Visual%20Basic\).md)   
 [NotInheritable](../Topic/NotInheritable%20\(Visual%20Basic\).md)   
 [Inherits Statement](../Topic/Inherits%20Statement.md)