---
title: "Includedateien f&#252;r Multithreading"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Includedateien, Multithreading"
  - "Multithreading [C++], Includedateien"
  - "Threading [C++], Includedateien"
ms.assetid: 98d764f9-71f4-4da5-8f3a-8d2d26e96799
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Includedateien f&#252;r Multithreading
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Durch Standardincludedateien werden C\-Laufzeitbibliotheksfunktionen bei der Implementierung in die Bibliotheken deklariert.  Wenn Sie die Option [Komplette Optimierung](../../build/reference/ox-full-optimization.md) \(**\/Ox**\) bzw. die [fastcall\-Aufrufkonvention](../../build/reference/gd-gr-gv-gz-calling-convention.md) \(**\/Gr**\) verwenden, wird vom Compiler angenommen, dass sämtliche Funktionen mithilfe der Registeraufrufkonvention aufgerufen werden sollen.  Die Laufzeitbibliotheksfunktionen wurden mithilfe der C\-Aufrufkonvention kompiliert. Durch die Deklarationen in den Standardincludedateien wird der Compiler angewiesen, die richtigen externen Verweise auf diese Funktionen zu generieren.  
  
## Siehe auch  
 [Multithreading bei C und Win32](../../parallel/multithreading-with-c-and-win32.md)