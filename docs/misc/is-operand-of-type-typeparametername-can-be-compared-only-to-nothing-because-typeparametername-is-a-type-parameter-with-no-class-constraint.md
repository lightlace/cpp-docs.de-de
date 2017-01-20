---
title: "Ein Is-Operand vom Typ &quot;&lt;Typparameter&gt;&quot; kann nur mit &quot;Nothing&quot; verglichen werden, da &quot;&lt;Typparametername&gt;&quot; ein Typparameter ohne Klasseneinschr&#228;nkung ist"
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
  - "vbc32052"
  - "bc32052"
helpviewer_keywords: 
  - "BC32052"
ms.assetid: 0bbf2249-eb0d-4b74-a555-8868c7ebe91d
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "shoag"
manager: "wpickett"
---
# Ein Is-Operand vom Typ &quot;&lt;Typparameter&gt;&quot; kann nur mit &quot;Nothing&quot; verglichen werden, da &quot;&lt;Typparametername&gt;&quot; ein Typparameter ohne Klasseneinschr&#228;nkung ist
Ein Typparameter wird als Operand für den [Is Operator](../Topic/Is%20Operator%20\(Visual%20Basic\).md) verwendet, wenn der Typparameter in der Einschränkungsliste ohne das [Class\-Schlüsselwort \(Visual Basic\)](assetId:///0777c6e6-46bc-451b-ad70-57b49d4ef4f7) oder einen bestimmten Klassennamen definiert ist.  
  
 `Is` vergleicht zwei Verweistypen, um zu bestimmen, ob sie im Arbeitsspeicher auf dieselbe Objektinstanz verweisen. Ein Operand, der kein Verweistyp ist, wird nicht akzeptiert, es sei denn, der andere Operand ist [Nothing](../Topic/Nothing%20\(Visual%20Basic\).md).  
  
 **Fehler\-ID:** BC32052  
  
### So beheben Sie diesen Fehler  
  
-   Wenn Sie festlegen können, dass das für diesen Typparameter angegebene Typargument immer ein Verweistyp sein muss, fügen Sie der Einschränkungsliste für den Typparameter entweder das `Class`\-Schlüsselwort oder einen bestimmten Klassennamen hinzu.  
  
-   Wenn Sie nicht festlegen können, dass das für diesen Typparameter angegebene Typargument immer ein Verweistyp sein muss, entfernen Sie es aus dem `Is`\-Ausdruck. Sie können es nicht mithilfe des `Is`\-Operators mit anderen Verweistypen vergleichen.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)   
 [Value Types and Reference Types](../Topic/Value%20Types%20and%20Reference%20Types.md)   
 [Comparison Operators in Visual Basic](../Topic/Comparison%20Operators%20in%20Visual%20Basic.md)