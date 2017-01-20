---
title: "Das Typargument &quot;&lt;Typargumentname&gt;&quot; muss einen &#246;ffentlichen parameterlosen Instanzenkonstruktor aufweisen, um der New-Einschr&#228;nkung f&#252;r den &lt;Typparametername&gt;-Typparameter zu entsprechen."
ms.custom: na
ms.date: "12/08/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc32083"
  - "BC32083"
helpviewer_keywords: 
  - "BC32083"
ms.assetid: 56bf25f1-375c-4b5d-9969-45eba8b3b66c
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Das Typargument &quot;&lt;Typargumentname&gt;&quot; muss einen &#246;ffentlichen parameterlosen Instanzenkonstruktor aufweisen, um der New-Einschr&#228;nkung f&#252;r den &lt;Typparametername&gt;-Typparameter zu entsprechen.
Ein Typargument stellt einen Typ, der keinen aufrufbaren parameterlosen Konstruktor hat, einem Typparameter mit der [New Operator](../Topic/New%20Operator%20\(Visual%20Basic\).md)\-Einschränkung bereit.  
  
 Eine Einschränkungsliste erzwingt Anforderungen für das Typargument, das an den Typparameter übergeben wird. Eine mögliche Anforderung besteht darin, dass das Typargument einen parameterlosen Konstruktor verfügbar machen muss, auf den der erstellende Code zugreifen kann. Um diese Anforderung anzugeben, enthält die Einschränkungsliste die `New`\-Einschränkung.  
  
 **Fehler\-ID:** BC32083  
  
### So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass der Name des generischen Typs und der Typname im Typargument richtig geschrieben sind.  
  
2.  Wählen Sie einen Typ für das Typargument, der einen aufrufbaren parameterlosen Konstruktor verfügbar macht. Dieser spezielle generische Typ kann nur dann aufgerufen werden, wenn Sie ein solches Typargument für diesen Typparameter bereitstellen können.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)   
 [Gewusst wie: Verwenden einer generischen Klasse](../Topic/How%20to:%20Use%20a%20Generic%20Class%20\(Visual%20Basic\).md)