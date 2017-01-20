---
title: "&#39;&lt;Methode&gt;&#39; ist in diesem Kontext nicht zugreifbar, da es &#39;&lt;Modifizierer&gt;&#39; ist."
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc30389"
  - "bc30389"
helpviewer_keywords: 
  - "BC30389"
ms.assetid: fae58a68-df91-4741-a8c9-f1bb10e166e2
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;Methode&gt;&#39; ist in diesem Kontext nicht zugreifbar, da es &#39;&lt;Modifizierer&gt;&#39; ist.
Sie haben versucht, auf eine Methode zuzugreifen, auf die in diesem Kontext nicht zugegriffen werden kann, da sie als `Private` deklariert wurde. Eine mögliche Ursache für diesen Fehler ist, dass der [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)]\-Compiler alle Member einer Klasse importiert und die Groß\-\/Kleinschreibung berücksichtigt. Daher können zwischen Namen, die sich nur durch die Groß\-\/Kleinschreibung unterschieden, Konflikte auftreten.  
  
 **Fehler\-ID:** BC30389  
  
### So beheben Sie diesen Fehler  
  
-   Sie können die Methode `Public` deklarieren.  
  
-   Wenn der Fehler durch einen Namenskonflikt verursacht wird, sorgen Sie dafür, dass sich die in Konflikt stehenden Namen nicht nur durch die Groß\-\/Kleinschreibung unterscheiden.  
  
## Siehe auch  
 [Private](../Topic/Private%20\(Visual%20Basic\).md)