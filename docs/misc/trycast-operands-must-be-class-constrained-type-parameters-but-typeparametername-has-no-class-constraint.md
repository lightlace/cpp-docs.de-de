---
title: "TryCast-Operanden m&#252;ssen Typparameter mit Klasseneinschr&#228;nkung sein, aber &quot;&lt;Typparametername&gt;&quot; hat keine Klasseneinschr&#228;nkung."
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
  - "BC30793"
  - "vbc30793"
helpviewer_keywords: 
  - "BC30793"
ms.assetid: a38a1da9-4413-4a69-a2ce-0b6d51c2c4ef
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# TryCast-Operanden m&#252;ssen Typparameter mit Klasseneinschr&#228;nkung sein, aber &quot;&lt;Typparametername&gt;&quot; hat keine Klasseneinschr&#228;nkung.
Der [TryCast Operator](../Topic/TryCast%20Operator%20\(Visual%20Basic\).md)\-Operator wird mit einem Operanden und Typparameter verwendet, der nicht unbedingt ein Verweistyp ist.  
  
 `TryCast` kann nur bei Verweistypen, z. B. Klassen oder Schnittstellen, verwendet werden. Wenn Sie einen Typparameter als Argument an `TryCast` übergeben, müssen Sie den Typparameter auf den Verweistyp einschränken. Dazu können Sie eines oder mehrere der folgenden Elemente in die Einschränkungsliste des Typparameters aufnehmen:  
  
-   Ein oder mehrere Schnittstellennamen \(alle müssen mit dem Typargument implementiert werden\)  
  
-   Maximal ein Klassenname \(das Typargument muss von ihm erben\)  
  
-   Die Einschränkung "[New Operator](../Topic/New%20Operator%20\(Visual%20Basic\).md)" \(das Typargument muss einen parameterlosen Konstruktor aufweisen, auf den der erstellende Code zugreifen kann, und muss daher eine Klasse sein\)  
  
-   Die Einschränkung [Classe \(Visual Basic\)](assetId:///0777c6e6-46bc-451b-ad70-57b49d4ef4f7) \(das Typargument muss ein Verweistyp sein\)  
  
 **Fehler\-ID:** BC30793  
  
### So beheben Sie diesen Fehler  
  
-   Wenn Sie diesen Typparameter an `TryCast` übergeben müssen, schränken Sie ihn mithilfe einer oder mehrerer Einschränkungen aus obiger Liste ein.  
  
-   Wenn Sie den Typparameter nicht soweit einschränken können, dass er nur den Verweistyp akzeptiert, können Sie ihn mit `TryCast` nicht verwenden. Vielleicht bietet sich stattdessen die [CType\-Funktion](../Topic/CType%20Function%20\(Visual%20Basic\).md) an.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)   
 [Value Types and Reference Types](../Topic/Value%20Types%20and%20Reference%20Types.md)   
 [Widening and Narrowing Conversions](../Topic/Widening%20and%20Narrowing%20Conversions%20\(Visual%20Basic\).md)   
 [Implicit and Explicit Conversions](../Topic/Implicit%20and%20Explicit%20Conversions%20\(Visual%20Basic\).md)