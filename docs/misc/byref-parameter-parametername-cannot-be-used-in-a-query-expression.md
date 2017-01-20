---
title: "Der ByRef-Parameter &quot;&lt;Parametername&gt;&quot; kann in einem Abfrageausdruck nicht verwendet werden."
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
  - "vbc36533"
  - "bc36533"
helpviewer_keywords: 
  - "BC36533"
ms.assetid: 8067ac87-dd6b-4869-87d0-8a4ce272de41
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "shoag"
manager: "wpickett"
---
# Der ByRef-Parameter &quot;&lt;Parametername&gt;&quot; kann in einem Abfrageausdruck nicht verwendet werden.
Ein Parameter in einer LINQ\-Abfrage ist ein Zeigertyp. In Abfrageausdrücken verwendete Parameter können nicht per Verweis übergeben werden.  
  
 **Fehler\-ID:** BC36533  
  
### So beheben Sie diesen Fehler  
  
1.  Deklarieren Sie eine neue Variable, und weisen Sie den Wert der neuen Variablen einer Kopie des Werts zu, der per Verweis übergeben wird. Verwenden Sie die kopierte Variable in der LINQ\-Abfrage. Im Folgenden finden Sie ein Beispiel dazu:  
  
    ```vb#  
    Sub RunQuery(ByVal collection As List(Of Integer), _  
                 ByRef filterValue As Integer)  
        Dim fv = filterValue  
        Dim queryResult = From num In collection _  
                          Where num < fv  
    End Sub  
    ```  
  
### So beheben Sie diesen Fehler  
  
1.  Ersetzen Sie bei dem in der Abfrage verwendeten Parameter das `ByRef`\-Schlüsselwort durch das `ByVal`\-Schlüsselwort.  
  
## Siehe auch  
 [Differences Between Passing an Argument By Value and By Reference](../Topic/Differences%20Between%20Passing%20an%20Argument%20By%20Value%20and%20By%20Reference%20\(Visual%20Basic\).md)   
 [Introduction to LINQ in Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [LINQ](../Topic/LINQ%20in%20Visual%20Basic.md)