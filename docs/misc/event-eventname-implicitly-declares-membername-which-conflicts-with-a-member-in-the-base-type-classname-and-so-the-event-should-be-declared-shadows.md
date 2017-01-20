---
title: "Ereignis &#39;&lt;Ereignisname&gt;&#39; deklariert implizit &#39;&lt;Membername&gt;&#39;, was einen Konflikt mit einem Member in Basis &lt;Typ&gt; &#39;&lt;Klassenname&gt;&#39; verursacht. Das Ereignis sollte daher als „Shadows“ deklariert werden."
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
  - "bc40012"
  - "vbc40012"
helpviewer_keywords: 
  - "BC40012"
ms.assetid: 5f14e8bd-a227-4115-af99-cd2b6fe4dc0e
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# Ereignis &#39;&lt;Ereignisname&gt;&#39; deklariert implizit &#39;&lt;Membername&gt;&#39;, was einen Konflikt mit einem Member in Basis &lt;Typ&gt; &#39;&lt;Klassenname&gt;&#39; verursacht. Das Ereignis sollte daher als „Shadows“ deklariert werden.
Ein Ereignis wird mit einem Namen deklariert, der kombiniert einen impliziten Member mit demselben Namen wie für einen Member der Basisklasse bilden soll. Wenn Sie z. B. eine Eigenschaft namens `Event1` deklarieren, generiert der Compiler die impliziten Prozeduren `add_Event1` und `remove_Event1`. Wenn die Basisklasse einen Member mit einem dieser Namen aufweist, muss das Ereignis in dieser Klasse den Basisklassenmember überschatten.  
  
 Diese Meldung ist eine Warnung.`Shadows` wird standardmäßig angenommen. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **Fehler\-ID:** BC40012  
  
### So beheben Sie diesen Fehler  
  
1.  Um den Member der Basisklasse auszublenden, fügen Sie der Deklaration des Ereignisses das `Shadows`\-Schlüsselwort hinzu.  
  
2.  Wenn Sie den Basisklassenmember nicht ausblenden möchten, ändern Sie den Namen des Ereignisses.  
  
## Siehe auch  
 [Event Statement](../Topic/Event%20Statement.md)   
 [Shadows](../Topic/Shadows%20\(Visual%20Basic\).md)   
 [Shadowing in Visual Basic](../Topic/Shadowing%20in%20Visual%20Basic.md)