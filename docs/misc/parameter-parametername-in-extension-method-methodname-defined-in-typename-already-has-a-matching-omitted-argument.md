---
title: "Der Parameter &quot;&lt;Parametername&gt;&quot; in der in &quot;&lt;Typname&gt;&quot; definierten Erweiterungsmethode &quot;&lt;Methodenname&gt;&quot; hat bereits ein entsprechendes ausgelassenes Argument."
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
  - "bc36583"
  - "vbc36583"
helpviewer_keywords: 
  - "BC36583"
ms.assetid: 662072fa-abb8-43c3-8ca2-aefb20f2e902
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "shoag"
manager: "wpickett"
---
# Der Parameter &quot;&lt;Parametername&gt;&quot; in der in &quot;&lt;Typname&gt;&quot; definierten Erweiterungsmethode &quot;&lt;Methodenname&gt;&quot; hat bereits ein entsprechendes ausgelassenes Argument.
Bei einem Prozeduraufruf einer Erweiterungsmethode wird ein Argument nach Position ausgelassen und dann anhand des Namens bereitgestellt. Beispiel: Beim folgenden Aufruf der Erweiterungsmethode `ABC` wird zuerst ein Argument für den Parameter `Y` ausgelassen und dann anhand seines Namens bereitgestellt.  
  
```  
<Extension()> _ Public Sub ABC(ByVal X As Integer, Optional ByVal Y As Byte = 0, _ Optional ByVal Z As Byte = 0) End Sub ' . . . ' Calling extension method ABC. Dim number As Integer ' Not valid. ' number.ABC(, 4, Y:=5)  
```  
  
 **Fehler\-ID:** BC36583  
  
### So beheben Sie diesen Fehler  
  
-   Geben Sie das Argument nach Position an, oder entfernen Sie das Komma, durch das es ausgelassen wird.  
  
## Siehe auch  
 [Erweiterungsmethoden](../Topic/Extension%20Methods%20\(Visual%20Basic\).md)   
 [Passing Arguments by Position and by Name](../Topic/Passing%20Arguments%20by%20Position%20and%20by%20Name%20\(Visual%20Basic\).md)