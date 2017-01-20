---
title: "Ein IsNot-Operand vom Typ &lt;Typparametername&gt; kann nur mit „Nothing“ verglichen werden, da &lt;Typparametername&gt; ein Typparameter ohne Klasseneinschr&#228;nkung ist."
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
  - "vbc32097"
  - "bc32097"
helpviewer_keywords: 
  - "BC32097"
ms.assetid: 50283a4b-70e3-4e59-9b9b-65e7cacf5ce1
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "shoag"
manager: "wpickett"
---
# Ein IsNot-Operand vom Typ &lt;Typparametername&gt; kann nur mit „Nothing“ verglichen werden, da &lt;Typparametername&gt; ein Typparameter ohne Klasseneinschr&#228;nkung ist.
Ein Typparameter wird als Operand für den [IsNot Operator](../Topic/IsNot%20Operator%20\(Visual%20Basic\).md) verwendet, wenn der Typparameter ohne das [Class\-Schlüsselwort \(Visual Basic\)](assetId:///0777c6e6-46bc-451b-ad70-57b49d4ef4f7) oder einen bestimmten Klassennamen in der Einschränkungsliste definiert wird.  
  
 `IsNot` vergleicht zwei Verweistypen, um zu bestimmen, ob sie auf unterschiedliche Objektinstanzen im Arbeitsspeicher verweisen. Ein Operand, der kein Verweistyp ist, wird nicht akzeptiert, es sei denn, der andere Operand ist [Nothing](../Topic/Nothing%20\(Visual%20Basic\).md).  
  
 **Fehler\-ID:** BC32097  
  
### So beheben Sie diesen Fehler  
  
-   Wenn Sie festlegen können, dass das für diesen Typparameter angegebene Typargument immer ein Verweistyp sein muss, fügen Sie entweder das `Class`\-Schlüsselwort oder einen bestimmten Klassennamen zur Einschränkungsliste für den Typparameter hinzu.  
  
-   Wenn Sie nicht festlegen können, dass das für diesen Typparameter angegebene Typargument immer ein Verweistyp sein muss, entfernen Sie es aus dem `IsNot`\-Ausdruck. Sie können es nicht mithilfe des `IsNot`\-Operators mit anderen Verweistypen vergleichen.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)   
 [Value Types and Reference Types](../Topic/Value%20Types%20and%20Reference%20Types.md)   
 [Comparison Operators in Visual Basic](../Topic/Comparison%20Operators%20in%20Visual%20Basic.md)