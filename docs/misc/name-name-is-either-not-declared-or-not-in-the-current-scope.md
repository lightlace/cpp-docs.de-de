---
title: "Der Name &#39;&lt;Name&gt;&#39; ist entweder nicht deklariert oder im aktuellen Bereich ung&#252;ltig."
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
  - "vbc36610"
  - "bc36610"
helpviewer_keywords: 
  - "BC36610"
ms.assetid: e66a4b8a-9252-42ae-a30d-341fad4f74be
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "shoag"
manager: "wpickett"
---
# Der Name &#39;&lt;Name&gt;&#39; ist entweder nicht deklariert oder im aktuellen Bereich ung&#252;ltig.
Eine LINQ\-Abfrage bezieht sich auf ein Programmierelement, aber der Compiler kann kein Element mit genau diesem Namen finden.  
  
 **Fehler\-ID:** BC36610  
  
### So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die Schreibweise des Namens in der verweisenden Anweisung. Bei [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] wird die Groß\-\/Kleinschreibung berücksichtigt, aber eine andere Variante der Schreibweise bildet einen anderen Namen. Beachten Sie, dass der Unterstrich \(`_`\) Teil des Namens und daher Teil der Schreibweise ist.  
  
2.  Überprüfen Sie, ob sich das Programmierelement im Gültigkeitsbereich befindet. Wenn die verweisende Anweisung außerhalb des Bereichs liegt, der das Programmierelement deklariert, müssen Sie den Elementnamen möglicherweise qualifizieren. Weitere Informationen finden Sie unter [Scope in Visual Basic](../Topic/Scope%20in%20Visual%20Basic.md).  
  
3.  Stellen Sie sicher, dass Sie den Memberzugriffsoperator \(`.`\) zwischen einem Objekt und seinem Member verwenden. Wenn Sie z. B. ein <xref:System.Windows.Forms.TextBox>\-Steuerelement namens `TextBox1` besitzen, müssen Sie für den Zugriff auf dessen <xref:System.Windows.Forms.TextBoxBase.Text*>\-Eigenschaft `TextBox1.Text` eingeben. Wenn Sie stattdessen `TextBox1Text` eingeben, haben Sie einen anderen Namen erstellt.  
  
## Siehe auch  
 [Introduction to LINQ in Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [Visual Basic Naming Conventions](../Topic/Visual%20Basic%20Naming%20Conventions.md)   
 [References to Declared Elements](../Topic/References%20to%20Declared%20Elements%20\(Visual%20Basic\).md)