---
title: "„Microsoft.VisualBasic.ComClassAttribute“ kann nicht auf eine Klasse angewendet werden, die generisch ist oder innerhalb eines generischen Typs geschachtelt ist."
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
  - "vbc31527"
  - "bc31527"
helpviewer_keywords: 
  - "BC31527"
ms.assetid: ea125bff-d020-4933-b277-6e24943eea88
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "shoag"
manager: "wpickett"
---
# „Microsoft.VisualBasic.ComClassAttribute“ kann nicht auf eine Klasse angewendet werden, die generisch ist oder innerhalb eines generischen Typs geschachtelt ist.
Eine Klasse wird mit <xref:Microsoft.VisualBasic.ComClassAttribute> deklariert, ist jedoch entweder generisch oder in einer generischen Klasse bzw. Struktur enthalten.  
  
 Die Eignung einer .NET Framework\-Klasse für COM\-Interop setzt die Erfüllung der folgenden Anforderungen voraus:  
  
-   Sie muss `Public` sein, alle ihre Container müssen `Public` sein, und sie muss mindestens einen `Public`\-Member verfügbar machen.  
  
-   Sie darf nicht *abstrakt* sein, d. h., sie darf nicht mit `MustInherit` deklariert werden.  
  
-   Sie darf nicht generisch sein oder in einem generischen Containertyp deklariert werden.  
  
 **Fehler\-ID:** BC31527  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie die Deklaration der Klasse, sodass sie nicht generisch ist, und stellen Sie sicher, dass ihr enthaltendes Element nicht generisch ist.  
  
     \- oder \-  
  
-   Wenn die Klasse oder ihr enthaltendes Element generisch sein muss, entfernen Sie das <xref:Microsoft.VisualBasic.ComClassAttribute> aus der Klassendeklaration. Sie können sie nicht für COM verfügbar machen.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.ComClassAttribute>   
 [COM Interop](../Topic/COM%20Interop%20\(Visual%20Basic\).md)   
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)