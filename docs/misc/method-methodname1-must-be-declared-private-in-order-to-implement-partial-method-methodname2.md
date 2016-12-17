---
title: "Die Methode &lt;Methodenname1&gt; muss als „Private“ deklariert werden, um die partielle Methode &lt;Methodenname2&gt; zu implementieren."
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
  - "vbc31441"
  - "bc31441"
helpviewer_keywords: 
  - "BC31441"
ms.assetid: 4d8d19ad-0c3b-4eba-ada8-2cfa6ae795c4
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "shoag"
manager: "wpickett"
---
# Die Methode &lt;Methodenname1&gt; muss als „Private“ deklariert werden, um die partielle Methode &lt;Methodenname2&gt; zu implementieren.
Die Implementierung einer partiellen Methode muss als `Private` deklariert werden. Beispielsweise verursacht der folgende Code einen Compilerfehler:  
  
```vb#  
Partial Class Product ' Declaration of the partial method. Partial Private Sub valueChanged() End Sub End Class  
```  
  
```vb#  
Partial Class Product ' Implementation of the partial method, with Private missing, ' causes this error. 'Sub valueChanged() '    MsgBox(Value was changed to " & Me.Quantity) 'End Sub End Class  
```  
  
 **Fehler\-ID:** BC31441  
  
### So beheben Sie diesen Fehler  
  
1.  Verwenden Sie den Zugriffsmodifizierer `Private` in der Implementierung der partiellen Methode, wie im folgenden Beispiel gezeigt.  
  
    ```vb#  
    Private Sub valueChanged() MsgBox(Value was changed to " & Me.Quantity) End Sub  
    ```  
  
## Siehe auch  
 [Partial Methods](../Topic/Partial%20Methods%20\(Visual%20Basic\).md)   
 [Access Levels in Visual Basic](../Topic/Access%20Levels%20in%20Visual%20Basic.md)