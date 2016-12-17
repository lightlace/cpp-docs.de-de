---
title: "Die Class-Einschr&#228;nkung kann nicht mehrmals f&#252;r den gleichen Typparameter angegeben werden."
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc32101"
  - "vbc32101"
helpviewer_keywords: 
  - "BC32101"
ms.assetid: fac2330a-e397-4bd9-8166-934407575f9e
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Die Class-Einschr&#228;nkung kann nicht mehrmals f&#252;r den gleichen Typparameter angegeben werden.
Eine Einschränkungsliste enthält die [Class \(Visual Basic\)](assetId:///0777c6e6-46bc-451b-ad70-57b49d4ef4f7)\-Einschränkung mehrfach.  
  
 Eine Einschränkungsliste für einen Typparameter kann angeben, dass das an den Typparameter übergebene Argument ein Werttyp \(mit der [Structure \(Visual Basic\)](assetId:///263ce115-ac36-4c05-8cb7-0e0eead5c6d0)\-Einschränkung\) oder ein Verweistyp sein muss \(mit der `Class`\-Einschränkung\). Sie dürfen nicht beide Einschränkungen für den gleichen Typparameter angeben, und Sie dürfen keine dieser Einschränkungen mehrmals angeben.  
  
 Fehler\-ID: BC32101  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie alle redundanten `Class`\-Schlüsselwörter. In der Einschränkungsliste sollte nur ein Vorkommen enthalten sein.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Value Types and Reference Types](../Topic/Value%20Types%20and%20Reference%20Types.md)