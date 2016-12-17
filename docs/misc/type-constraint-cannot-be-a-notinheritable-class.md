---
title: "Eine Typeinschr&#228;nkung kann keine NotInheritable-Klasse sein."
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
  - "vbc32060"
  - "bc32060"
helpviewer_keywords: 
  - "BC32060"
ms.assetid: f45cc0b6-7df1-462a-b3df-c526c143e16a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Eine Typeinschr&#228;nkung kann keine NotInheritable-Klasse sein.
Eine Einschränkungsliste enthält eine Klasse, die als [NotInheritable](../Topic/NotInheritable%20\(Visual%20Basic\).md) gekennzeichnet ist.  
  
 Eine Einschränkungsliste für einen Typparameter kann höchstens eine Klasse akzeptieren. Ein für den Typparameter angegebenes Typargument muss von dieser Klasse erben. Aus diesem Grund kann der Typparameter keine *versiegelte* oder `NotInheritable` Klasse als Einschränkung annehmen.  
  
 **Fehler\-ID:** BC32060  
  
### So beheben Sie diesen Fehler  
  
-   Wenn der Typparameter in der Lage sein muss, von der Klasse zu erben, und Sie die Kontrolle über die Definition der Klasse haben, entfernen Sie die `NotInheritable`\-Deklaration aus der Klasse.  
  
-   Wenn für die Klasse weiterhin „`NotInheritable`“ gelten muss, können Sie sie nicht als Einschränkung verwenden. Entfernen Sie den Klassennamen aus der Einschränkungsliste.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)