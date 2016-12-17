---
title: "Ung&#252;ltiger Aufruf- oder Indexausdruck."
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
  - "vbc32303"
  - "bc32303"
helpviewer_keywords: 
  - "BC32303"
ms.assetid: eed6a16e-4a44-4f72-b1de-d4212940da37
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# Ung&#252;ltiger Aufruf- oder Indexausdruck.
Ein Wert in Klammern folgt auf einen Ausdruck, der weder Prozedur, Eigenschaft noch Array ist.  
  
 Dieser Fehler kann durch folgenden Code generiert werden.  
  
 `Dim testVariable As Object = Nothing(1)`  
  
 Da `Nothing` keine Argumente oder Indizes akzeptiert, können Sie es nicht mit Klammern verwenden.  
  
 **Fehler\-ID:** BC32303  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die Klammern und alle darin enthaltenen Werte.  
  
## Siehe auch  
 [How to: Call a Procedure That Returns a Value](../Topic/How%20to:%20Call%20a%20Procedure%20That%20Returns%20a%20Value%20\(Visual%20Basic\).md)   
 [How to: Call a Procedure that Does Not Return a Value](../Topic/How%20to:%20Call%20a%20Procedure%20that%20Does%20Not%20Return%20a%20Value%20\(Visual%20Basic\).md)   
 [NOTINBUILD Gewusst wie: Ablegen eines Werts in einem Array](assetId:///6dddc79c-cf60-41c2-b572-8bfa49b4fe7e)   
 [NOTINBUILD Gewusst wie: Abrufen eines Werts aus einem Array](assetId:///202a6468-8ccb-4864-bd8b-eab3b42d4288)   
 [How to: Put a Value in a Property](../Topic/How%20to:%20Put%20a%20Value%20in%20a%20Property%20\(Visual%20Basic\).md)   
 [How to: Get a Value from a Property](../Topic/How%20to:%20Get%20a%20Value%20from%20a%20Property%20\(Visual%20Basic\).md)