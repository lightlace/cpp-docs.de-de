---
title: "Die New-Einschr&#228;nkung kann nicht mehrmals f&#252;r den gleichen Typparameter angegeben werden."
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
  - "vbc32081"
  - "BC32081"
helpviewer_keywords: 
  - "BC32081"
ms.assetid: afcb30da-3973-4452-9cf3-c027f9866589
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Die New-Einschr&#228;nkung kann nicht mehrmals f&#252;r den gleichen Typparameter angegeben werden.
Eine Einschränkungsliste enthält die [New Operator](../Topic/New%20Operator%20\(Visual%20Basic\).md)\-Einschränkung mehrfach.  
  
 Eine Einschränkungsliste für einen Typparameter kann angeben, dass das an den Typparameter übergebene Typargument einen parameterlosen Konstruktor verfügbar machen muss, auf den der erstellende Code zugreifen kann. Ein Typ kann nicht mehr als einen parameterlosen Konstruktor aufweisen, und Sie können diese Anforderung nicht mehr als einmal angeben.  
  
 **Fehler\-ID:** BC32081  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie alle redundanten `New`\-Schlüsselwörter. In der Einschränkungsliste sollte nur ein Vorkommen enthalten sein.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)