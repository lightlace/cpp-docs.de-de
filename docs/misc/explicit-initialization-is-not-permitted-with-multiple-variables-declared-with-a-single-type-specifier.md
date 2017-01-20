---
title: "Explizites Initialisieren mit mehreren Variablen, die mit nur einem Typspezifizierer deklariert wurden, ist nicht zul&#228;ssig."
ms.custom: na
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc30671"
  - "vbc30671"
helpviewer_keywords: 
  - "BC30671"
ms.assetid: 57bbdd58-b58d-4144-8fa6-366a7167df27
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Explizites Initialisieren mit mehreren Variablen, die mit nur einem Typspezifizierer deklariert wurden, ist nicht zul&#228;ssig.
Die Initialisierung ist nicht zulässig, wenn mehrere Variablen in der gleichen Zeile deklariert werden.  
  
 **Fehler\-ID:** BC30671  
  
### So beheben Sie diesen Fehler  
  
1.  Deklarieren und initialisieren Sie jedes Element einzeln.  
  
2.  Deklarieren Sie mehrere Elemente zusammen, und initialisieren Sie die Elemente dann einzeln; Beispiel:  
  
    ```  
    Dim x, b, i As Integer x = 9 : b = 9 : i = 9 ' ":" is the same as a new line.  
    ```  
  
## Siehe auch  
 [Dim Statement](../Topic/Dim%20Statement%20\(Visual%20Basic\).md)   
 [Variablendeklaration](../Topic/Variable%20Declaration%20in%20Visual%20Basic.md)