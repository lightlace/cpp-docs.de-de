---
title: "F&#252;r den &#39;&lt;Operatorsymbol&gt;&#39;-Operator werden Operanden vom Typ „Object“ verwendet. Dies kann Laufzeitfehler verursachen."
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
  - "BC42019"
  - "vbc42019"
helpviewer_keywords: 
  - "BC42019"
ms.assetid: f61944ba-863b-4a82-aae4-249bda52ec8d
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# F&#252;r den &#39;&lt;Operatorsymbol&gt;&#39;-Operator werden Operanden vom Typ „Object“ verwendet. Dies kann Laufzeitfehler verursachen.
Ein Ausdruck verwendet einen Operator, für den ein oder beide Operanden vom [Object Data Type](../Topic/Object%20Data%20Type.md) sind.  
  
 Wenn eine Variable oder ein Ausdruck `Object` ergibt, muss der Compiler die *späte Bindung* durchführen, die zur Laufzeit zusätzliche Vorgänge verursacht. Sie setzt die Anwendung zudem möglichen Laufzeitfehlern aus. Angenommen, Sie weisen ein <xref:System.Windows.Forms.Form> zu einer `Object`\-Variable zu und versuchen dann, sie mit dem [\/ Operator](../Topic/-%20Operator%20\(Visual%20Basic\)3.md) zu verwenden. In diesem Fall löst die Laufzeit eine <xref:System.InvalidCastException> aus, da Visual Basic ein <xref:System.Windows.Forms.Form>\-Objekt nicht in einen numerischen Wert konvertieren kann.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **Fehler\-ID:** BC42019  
  
### So beheben Sie diesen Fehler  
  
-   Ordnen Sie nach Möglichkeit alle auszuwertenden Operanden zu Datentypen zu, für die der Operator definiert ist.  
  
## Siehe auch  
 [Arithmetic Operators in Visual Basic](../Topic/Arithmetic%20Operators%20in%20Visual%20Basic.md)