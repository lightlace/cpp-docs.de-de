---
title: "In Ausdr&#252;cken f&#252;r Select- oder Case-Anweisungen werden Operanden vom Typ „Object“ verwendet. Dies kann Laufzeitfehler verursachen."
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
  - "vbc42036"
  - "bc42036"
helpviewer_keywords: 
  - "BC42036"
ms.assetid: f11e9c9f-aa66-4eb1-8f49-abf713bef885
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "shoag"
manager: "wpickett"
---
# In Ausdr&#252;cken f&#252;r Select- oder Case-Anweisungen werden Operanden vom Typ „Object“ verwendet. Dies kann Laufzeitfehler verursachen.
Eine `Select`...`Case`\-Konstruktion verwendet einen oder mehrere Ausdrücke des [Object Data Type](../Topic/Object%20Data%20Type.md).  
  
 Wenn eine Variable oder ein Ausdruck `Object` ergibt, muss der Compiler die *späte Bindung* durchführen, die zur Laufzeit zusätzliche Vorgänge verursacht. Sie setzt die Anwendung zudem möglichen Laufzeitfehlern aus. Wenn Sie z. B. ein <xref:System.Windows.Forms.Form> einer `Object`\-Variablen zuweisen und es dann mit einer Zahl vergleichen, löst die Laufzeit eine <xref:System.InvalidCastException> aus, da Visual Basic ein <xref:System.Windows.Forms.Form>\-Objekt nicht in einen numerischen Wert konvertieren kann.  
  
 Die Ausdrücke in einer `Select`...`Case`\-Konstruktion sollten alle denselben Datentyp oder eng verbundene Datentypen verwenden, die untereinander konvertiert werden können. Der Grund hierfür ist, dass jede `Case`\-Anweisung mindestens einen Wert mit dem Testausdruck vergleicht, auf dem die `Select`...`Case`\-Konstruktion basiert.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **Fehler\-ID:** BC42036  
  
### So beheben Sie diesen Fehler  
  
-   Ordnen Sie nach Möglichkeit alle auszuwertenden Ausdrücke zu Datentypen zu, für die Vergleichsoperatoren definiert sind.  
  
## Siehe auch  
 [Select...Case Statement](../Topic/Select...Case%20Statement%20\(Visual%20Basic\).md)   
 [Arithmetic Operators in Visual Basic](../Topic/Arithmetic%20Operators%20in%20Visual%20Basic.md)   
 [Comparison Operators in Visual Basic](../Topic/Comparison%20Operators%20in%20Visual%20Basic.md)