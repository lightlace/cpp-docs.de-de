---
title: "Microsoft.VisualBasic.ComClassAttribute kann nicht auf eine Klasse angewendet werden, die als &quot;MustInherit&quot; deklariert ist"
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
  - "BC32508"
  - "vbc32508"
helpviewer_keywords: 
  - "BC32508"
ms.assetid: c8af606d-f448-4703-98df-e594fd511f92
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Microsoft.VisualBasic.ComClassAttribute kann nicht auf eine Klasse angewendet werden, die als &quot;MustInherit&quot; deklariert ist
Eine Klasse ist mit dem <xref:Microsoft.VisualBasic.ComClassAttribute> deklariert, aber in ihrer Deklaration wird `MustInherit` angegeben.  
  
 Die Eignung einer .NET Framework\-Klasse für COM\-Interop setzt die Erfüllung der folgenden Anforderungen voraus:  
  
-   Sie muss `Public` sein, alle ihre Container müssen `Public` sein, und sie muss mindestens einen `Public`\-Member verfügbar machen.  
  
-   Sie darf nicht *abstrakt* sein, d. h., sie darf nicht mit `MustInherit` deklariert werden.  
  
-   Sie darf nicht generisch sein oder in einem generischen Containertyp deklariert werden.  
  
 **Fehler\-ID:** BC32508  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie das `MustInherit`\-Schlüsselwort aus der Klassendeklaration.  
  
     \- oder \-  
  
-   Wenn die Klasse oder ihr enthaltendes Element generisch sein muss, entfernen Sie das <xref:Microsoft.VisualBasic.ComClassAttribute> aus der Klassendeklaration. Sie können sie nicht für COM verfügbar machen.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.ComClassAttribute>   
 [COM Interop](../Topic/COM%20Interop%20\(Visual%20Basic\).md)   
 [MustInherit](../Topic/MustInherit%20\(Visual%20Basic\).md)