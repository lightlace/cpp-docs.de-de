---
title: "&lt;Typ1&gt; &#39;&lt;Membername&gt;&#39; steht in Konflikt mit &lt;Typ2&gt; &#39;&lt;Membername&gt;&#39; in der Basisklasse &lt;Typ3&gt; &#39;&lt;Klassenname&gt;&#39; und sollte als &#39;Shadows&#39; deklariert werden."
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
  - "bc40004"
  - "vbc40004"
helpviewer_keywords: 
  - "BC40004"
ms.assetid: 24d10f31-3b3d-448c-b928-fc937e1f4a92
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;Typ1&gt; &#39;&lt;Membername&gt;&#39; steht in Konflikt mit &lt;Typ2&gt; &#39;&lt;Membername&gt;&#39; in der Basisklasse &lt;Typ3&gt; &#39;&lt;Klassenname&gt;&#39; und sollte als &#39;Shadows&#39; deklariert werden.
Ein Programmierelement wird mit demselben Namen wie ein Element deklariert, das in der Basisklasse definiert ist. In diesem Fall muss das Element in dieser Klasse das Element der Basisklasse überschatten.  
  
 Diese Meldung ist eine Warnung.`Shadows` wird standardmäßig angenommen. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **Fehler\-ID:** BC40004  
  
### So beheben Sie diesen Fehler  
  
-   Fügen Sie das `Shadows`\-Schlüsselwort zur Deklaration hinzu, oder ändern Sie den Namen des zu deklarieren Elements.  
  
## Siehe auch  
 [Shadows](../Topic/Shadows%20\(Visual%20Basic\).md)   
 [Shadowing in Visual Basic](../Topic/Shadowing%20in%20Visual%20Basic.md)