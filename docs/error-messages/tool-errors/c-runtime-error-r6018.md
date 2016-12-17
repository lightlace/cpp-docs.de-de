---
title: "C-Laufzeitfehler R6018"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "R6018"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6018"
ms.assetid: f6dd40d1-a119-4d8b-b39e-97350ea23349
caps.latest.revision: 7
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# C-Laufzeitfehler R6018
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

unerwarteter Heapfehler  
  
 Beim Durchführen eines Speicherverwaltungsvorgangs ist das Programm auf einen unerwarteten Fehler gestoßen.  
  
 Dieser Fehler tritt in der Regel auf, wenn das Programm unbeabsichtigt die Laufzeit\-Heapdaten ändert.  Er kann jedoch auch durch einen internen Fehler im Laufzeitcode oder durch das Betriebssystem verursacht werden.  
  
 Wenn der Compiler eine Bibliothek bereitstellt, die `_heapchk` und `_heapwalk` enthält, können diese Funktionen zur Fehlerdiagnose verwendet werden.