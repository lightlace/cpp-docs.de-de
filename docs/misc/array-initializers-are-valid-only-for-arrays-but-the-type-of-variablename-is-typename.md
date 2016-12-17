---
title: "Arrayinitialisierer sind nur f&#252;r Arrays g&#252;ltig. Der Typ von &quot;&lt;Variablenname&gt;&quot; ist jedoch &quot;&lt;Typname&gt;&quot;"
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
  - "bc30679"
  - "vbc30679"
helpviewer_keywords: 
  - "BC30679"
ms.assetid: 3cf34882-7a58-4074-8ebb-52e58199a506
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Arrayinitialisierer sind nur f&#252;r Arrays g&#252;ltig. Der Typ von &quot;&lt;Variablenname&gt;&quot; ist jedoch &quot;&lt;Typname&gt;&quot;
Es wurde versucht, eine Nicht\-Array\-Variable mit einer Liste von Werten zu initialisieren.  
  
 **Fehler\-ID:** BC30679  
  
### So beheben Sie diesen Fehler  
  
-   Deklarieren und initialisieren Sie die Variable als Array, z. B.:  
  
     `Dim intarray As Integer() = {1, 5, 9}`  
  
-   Initialisieren Sie die Variable als einen einzelnen Wert; z. B.:  
  
     `Dim intvalue As Integer = 1`  
  
## Siehe auch  
 [Dim Statement](../Topic/Dim%20Statement%20\(Visual%20Basic\).md)   
 [Variablendeklaration](../Topic/Variable%20Declaration%20in%20Visual%20Basic.md)   
 [Arrays](../Topic/Arrays%20in%20Visual%20Basic.md)