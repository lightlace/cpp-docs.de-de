---
title: "An „New“ in einem Typparameter k&#246;nnen keine Argumente &#252;bergeben werden."
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
  - "BC32085"
  - "vbc32085"
helpviewer_keywords: 
  - "BC32085"
ms.assetid: a60bf62d-2b2e-4621-b8db-e67720b918fb
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# An „New“ in einem Typparameter k&#246;nnen keine Argumente &#252;bergeben werden.
Eine Deklaration oder Zuweisungsanweisung ruft einen generischen Typ auf und stellt Konstruktorargumente für einen Typparameter bereit, der die [New Operator](../Topic/New%20Operator%20\(Visual%20Basic\).md)\-Einschränkung aufweist.  
  
 Eine Einschränkungsliste für einen Typparameter kann angeben, dass das an den Typparameter übergebene Typargument einen parameterlosen Konstruktor verfügbar machen muss, auf den der erstellende Code zugreifen kann. Ein Typparameter kann keinen Konstruktor erfordern, der Parameter aufweist, und ein Typparameter mit der `New`\-Einschränkung kann einen solchen Konstruktor nicht annehmen.  
  
 **Fehler\-ID:** BC32085  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die Argumentliste nach dem Typargument in der Anweisung, mit der der generische Typ aufgerufen wird. Sie können keine Konstruktorargumente an den entsprechenden Typparameter übergeben.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Value Types and Reference Types](../Topic/Value%20Types%20and%20Reference%20Types.md)