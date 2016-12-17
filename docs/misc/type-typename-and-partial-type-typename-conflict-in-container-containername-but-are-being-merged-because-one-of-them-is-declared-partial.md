---
title: "Typ &#39;&lt;Typname&gt;&#39; und der partielle Typ &#39;&lt;Typname&gt;&#39; verursachen einen Konflikt in Container &#39;&lt;Containername&gt;&#39;, werden jedoch zusammengef&#252;hrt, da eines der Elemente als partiell deklariert ist."
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
  - "bc40046"
  - "vbc40046"
helpviewer_keywords: 
  - "BC40046"
ms.assetid: c243e70b-ecd5-49ef-a260-a7bb12a4a3b1
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Typ &#39;&lt;Typname&gt;&#39; und der partielle Typ &#39;&lt;Typname&gt;&#39; verursachen einen Konflikt in Container &#39;&lt;Containername&gt;&#39;, werden jedoch zusammengef&#252;hrt, da eines der Elemente als partiell deklariert ist.
Eine Klasse oder Struktur ist in mehreren Definitionen desselben Containertyps enthalten, und mindestens zwei Definitionen sind nicht als `Partial` gekennzeichnet.  
  
 Sie müssen das [Partial](../Topic/Partial%20\(Visual%20Basic\).md)\-Schlüsselwort für mindestens eine der Definitionen einer Klasse oder Struktur verwenden, allerdings empfiehlt es sich, das Schlüsselwort für alle partiellen Definitionen zu verwenden.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **Fehler\-ID:** BC40046  
  
### So beheben Sie diesen Fehler  
  
-   Verwenden Sie das [Partial](../Topic/Partial%20\(Visual%20Basic\).md)\-Schlüsselwort für jede partielle Definition der Klasse oder Struktur.  
  
## Siehe auch  
 [Partial](../Topic/Partial%20\(Visual%20Basic\).md)