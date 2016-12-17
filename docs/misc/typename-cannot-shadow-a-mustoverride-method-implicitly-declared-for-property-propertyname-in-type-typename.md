---
title: "&lt;Typname&gt; kann kein Shadowing f&#252;r eine MustOverride-Methode vornehmen, die implizit f&#252;r die Eigenschaft &lt;Eigenschaftsname&gt; in &lt;Typ&gt; &lt;Typname&gt; deklariert wurde."
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
  - "bc31416"
  - "vbc31416"
helpviewer_keywords: 
  - "BC31416"
ms.assetid: a52aee3c-a19e-412d-bb91-ef1b79e8675f
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;Typname&gt; kann kein Shadowing f&#252;r eine MustOverride-Methode vornehmen, die implizit f&#252;r die Eigenschaft &lt;Eigenschaftsname&gt; in &lt;Typ&gt; &lt;Typname&gt; deklariert wurde.
Der angegebene Methodenname steht in Konflikt mit einer `MustOverride`\-Methode, die von einer Eigenschaft in der Basisklasse implizit generiert wurde. Wenn Sie z. B. eine Eigenschaft mit dem Namen `Prop1` deklarieren, generiert der Compiler die impliziten Prozeduren `get_Prop1` und `set_Prop1`.  
  
 **Fehler\-ID:** BC31416  
  
### So beheben Sie diesen Fehler  
  
1.  Geben Sie der Methode einen eindeutigen Namen.  
  
2.  Entfernen Sie den `MustOverride`\-Modifizierer aus der Eigenschaft in der Basisklasse.  
  
## Siehe auch  
 [MustOverride](../Topic/MustOverride%20\(Visual%20Basic\).md)   
 [Shadows](../Topic/Shadows%20\(Visual%20Basic\).md)   
 [Eigenschaftenprozeduren](../Topic/Property%20Procedures%20\(Visual%20Basic\).md)