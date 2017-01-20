---
title: "Die Struktur &quot;&lt;Strukturename&gt;&quot; kann keine Instanz von sich selbst enthalten: &lt;Fehler&gt;"
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
  - "vbc30294"
  - "bc30294"
helpviewer_keywords: 
  - "BC30294"
ms.assetid: 17780e11-2425-4860-9345-b5db019d2bf3
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Die Struktur &quot;&lt;Strukturename&gt;&quot; kann keine Instanz von sich selbst enthalten: &lt;Fehler&gt;
In einer Struktur wird eine Variable deklariert und mit einer Instanz der Struktur initialisiert.  
  
 Eine Struktur kann Instanzen anderer Strukturen, aber keine interne Instanz von sich selbst enthalten. Ein Versuch, dies zu tun, würde zu einer Endlosschleife führen.  
  
 **Fehler\-ID:** BC30294  
  
### So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die Schreibweise des Initialisierungsausdrucks in der Deklarationsanweisung.  
  
2.  Wenn Sie eine weitere Instanz derselben Struktur erstellen möchten, müssen Sie diese außerhalb der Struktur deklarieren und erstellen.  
  
## Siehe auch  
 [Structures](../Topic/Structures%20\(Visual%20Basic\).md)   
 [Structure Statement](../Topic/Structure%20Statement.md)