---
title: "Declare-Anweisungen in einem Modul d&#252;rfen nicht als &quot;&lt;Spezifizierer&gt;&quot; deklariert werden."
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
  - "vbc30786"
  - "bc30786"
helpviewer_keywords: 
  - "BC30786"
ms.assetid: 488b855f-72ea-414b-bffc-a5b63e97d289
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "shoag"
manager: "wpickett"
---
# Declare-Anweisungen in einem Modul d&#252;rfen nicht als &quot;&lt;Spezifizierer&gt;&quot; deklariert werden.
Eine `Declare`\-Deklaration enthält einen Spezifizierer, der in einer `Module`\-Deklaration ungültig ist. Module können nie instanziiert werden, unterstützen keine Vererbung und können keine Schnittstellen implementieren.  
  
 **Fehler\-ID:** BC30786  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie den Spezifizierer.  
  
## Siehe auch  
 [Delegate Statement](../Topic/Delegate%20Statement.md)   
 [Module Statement](../Topic/Module%20Statement.md)