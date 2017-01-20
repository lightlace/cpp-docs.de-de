---
title: "Variablendeklaration ohne As-Klausel. Typ &#39;Object&#39; wird angenommen."
ms.custom: na
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "BC42020"
  - "vbc42020"
helpviewer_keywords: 
  - "BC42020"
ms.assetid: 9422b16d-39b5-4d49-b697-608226ccafea
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# Variablendeklaration ohne As-Klausel. Typ &#39;Object&#39; wird angenommen.
In einer Variablendeklaration ist keine `As`\-Klausel angegeben.  
  
 Eine `As`\-Klausel bezeichnet einen Datentyp, der einem Programmierelement zugeordnet werden soll. In einem [Dim Statement](../Topic/Dim%20Statement%20\(Visual%20Basic\).md) gibt sie den Datentyp der einen oder mehreren Variablen an. Wenn Sie keine `As`\-Klausel in die `Dim`\-Anweisung einfügen, ist der Datentyp der Variablen standardmäßig `Object`.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **Fehler\-ID:** BC42020  
  
### So beheben Sie diesen Fehler  
  
-   Fügen Sie eine `As`\-Klausel in die `Dim`\-Anweisung ein, um den Datentyp der Variablen anzugeben.  
  
## Siehe auch  
 [Dim Statement](../Topic/Dim%20Statement%20\(Visual%20Basic\).md)   
 [Variablendeklaration](../Topic/Variable%20Declaration%20in%20Visual%20Basic.md)