---
title: "Der Modifizierer „?“, der NULL-Werte zul&#228;sst, und die Arraymodifizierer „(“ und „)“ k&#246;nnen nicht f&#252;r eine Variable und ihren Typ gleichzeitig festgelegt werden."
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
  - "vbc33102"
  - "bc33102"
helpviewer_keywords: 
  - "BC33102"
ms.assetid: fd3f65a4-63f9-41dc-ba15-98d86f097ba8
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "shoag"
manager: "wpickett"
---
# Der Modifizierer „?“, der NULL-Werte zul&#228;sst, und die Arraymodifizierer „(“ und „)“ k&#246;nnen nicht f&#252;r eine Variable und ihren Typ gleichzeitig festgelegt werden.
Der Typmodifizierer, der NULL\-Werte zulässt \(?\), wird für die Variable in einer Variablendeklaration einbezogen, in der die Arraymodifizierer \(Klammern\) für den angegebenen Variablentyp einbezogen werden. Oder der Typmodifizierer, der NULL\-Werte zulässt, wird für den angegebenen Variablentyp in einer Variablendeklaration einbezogen, in der die Arraymodifizierer für die Variable einbezogen werden.  
  
 **Fehler\-ID:** BC33102  
  
### So beheben Sie diesen Fehler  
  
1.  Geben Sie sowohl den NULL\-Werte zulassenden Typmodifizierer \(?\) als auch die Arraymodifizierer \(Klammern\) für die deklarierte Variable oder den angegebenen Variablentyp an, wie im folgenden Beispiel gezeigt.  
  
    ```vb#  
    ' These are incorrect. ' Dim numbers? As Integer() ' Dim values() As Integer? 'These are correct. Dim numbers?() As Integer Dim values As Integer?()  
    ```  
  
## Siehe auch  
 [Nullable Value Types](../Topic/Nullable%20Value%20Types%20\(Visual%20Basic\).md)