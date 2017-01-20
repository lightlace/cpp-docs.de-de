---
title: "Die Variable &#39;&lt;variablenname&gt;&#39; wurde als Verweis &#252;bergeben, bevor ihr ein Wert (Strukturvariable) zugewiesen wurde."
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
  - "bc42108"
  - "vbc42108"
helpviewer_keywords: 
  - "BC42108"
ms.assetid: 8f858dd7-db04-408e-ae67-e4ff2f0e5e30
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Die Variable &#39;&lt;variablenname&gt;&#39; wurde als Verweis &#252;bergeben, bevor ihr ein Wert (Strukturvariable) zugewiesen wurde.
Die Variable '\<variablenname\>' wurde als Verweis übergeben, bevor ihr ein Wert zugewiesen wurde. Zur Laufzeit kann eine null\-Verweisausnahme auftreten. Achten Sie darauf, dass die Struktur oder alle referenzierten Member vor der Verwendung initialisiert werden  
  
 Ein Prozeduraufruf übergibt eine Strukturvariable als Argument an einen `ByRef`\-Parameter, bevor der Variablen ein Wert zugewiesen wird.  
  
 Wenn einer Strukturvariablen nie ein Wert zugewiesen wurde, enthält jeder Strukturmember den Standardwert für seinen Datentyp. Bei Verweisdatentypen ist dieser Standardwert [Nothing](../Topic/Nothing%20\(Visual%20Basic\).md). Das Lesen eines Verweismembers, der den Wert `Nothing` aufweist, kann unter bestimmten Umständen zu einer <xref:System.NullReferenceException> führen.  
  
 Beim Übergeben eines Arguments an eine Prozedur `ByRef` wird die Variable, die dem Argument zugrunde liegt, für mögliche Änderungen durch die Prozedur verfügbar gemacht.  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **Fehler\-ID:** BC42108  
  
### So beheben Sie diesen Fehler  
  
-   Wenn die Prozedur Strukturmembern Werte mithilfe des `ByRef`\-Arguments zuweisen soll und es keine Rolle spielt, ob die Member bereits Werte enthalten, ist keine Aktion erforderlich.  
  
-   Wenn die Logik in der Prozedur einen Strukturmember ausliest, bevor sie ihm einen Wert zuweist, und der Member einen Werttyp besitzt, achten Sie darauf, dass die Prozedurlogik nicht davon abhängt, ob der Member seinen Standardwert oder einen anderen Wert enthält.  
  
-   Wenn die Logik in der Prozedur einen Strukturmember ausliest, bevor sie ihm einen Wert zuweist, und es sich bei dem Member um einen Verweistyp handelt, stellen Sie sicher, dass die Prozedurlogik den Wert `Nothing` verarbeiten kann. Beispielsweise kann sie ein [Try...Catch...Finally Statement](../Topic/Try...Catch...Finally%20Statement%20\(Visual%20Basic\).md) zum Abfangen einer <xref:System.NullReferenceException> verwenden.  
  
## Siehe auch  
 [Dim Statement](../Topic/Dim%20Statement%20\(Visual%20Basic\).md)   
 [Value Types and Reference Types](../Topic/Value%20Types%20and%20Reference%20Types.md)   
 [Passing Arguments by Value and by Reference](../Topic/Passing%20Arguments%20by%20Value%20and%20by%20Reference%20\(Visual%20Basic\).md)   
 [ByRef](../Topic/ByRef%20\(Visual%20Basic\).md)   
 [Variablendeklaration](../Topic/Variable%20Declaration%20in%20Visual%20Basic.md)   
 [Structures](../Topic/Structures%20\(Visual%20Basic\).md)   
 [Structure Statement](../Topic/Structure%20Statement.md)   
 [Problembehandlung bei Variablen](../Topic/Troubleshooting%20Variables%20in%20Visual%20Basic.md)