---
title: "&#39;&lt;methode1&gt;&#39; und &#39;&lt;methode2&gt;&#39; k&#246;nnen sich nicht gegenseitig &#252;berladen, da sie sich nur durch optionale Parameter unterscheiden."
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
  - "vbc30300"
  - "bc30300"
helpviewer_keywords: 
  - "BC30300"
ms.assetid: adb44ceb-57a0-4123-8fd8-7eb83c3f601f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;methode1&gt;&#39; und &#39;&lt;methode2&gt;&#39; k&#246;nnen sich nicht gegenseitig &#252;berladen, da sie sich nur durch optionale Parameter unterscheiden.
Sie haben versucht, eine Methode mit einer anderen Methode zu überladen, die sich lediglich in ihren optionalen Parametern von der ersten unterscheidet. Eine Methode mit einem optionalen Parameter ist zu zwei überladenen Methoden äquivalent, eine mit dem optionalen Parameter, die andere ohne ihn. Aus diesem Grund können Sie keine Methode mit einer Argumentliste überladen, die einer von beiden entspricht.  
  
 **Fehler\-ID:** BC30300  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass sich die Methoden durch mehr als optionale Parameter unterscheiden.  
  
## Siehe auch  
 [Procedure Overloading](../Topic/Procedure%20Overloading%20\(Visual%20Basic\).md)   
 [Considerations in Overloading Procedures](../Topic/Considerations%20in%20Overloading%20Procedures%20\(Visual%20Basic\).md)