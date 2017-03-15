---
title: "Abw&#228;rtskompatibilit&#228;t | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.programs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Abwärtskompatibilität"
  - "Abwärtskompatibilität, Laufzeitbibliotheken in C"
  - "Kompatibilität, Laufzeitbibliotheken in C"
  - "CRT, Kompatibilität"
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Abw&#228;rtskompatibilit&#228;t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um Kompatibilität zwischen Produktversionen, ordnet die Bibliothek OLDNAMES.LIB alten Namen den neuen Namen zu.  Beispielsweise `open` Zuordnungen zu `_open`.  Sie müssen mit OLDNAMES.LIB explizite Verknüpfung, wenn Sie mit den folgenden Befehlszeilenoptionen von Kombinationen kompilieren:  
  
-   `/Zl` \(lassen Sie Standard\-Bibliotheksnamen aus der Objektdatei\) weg und `/Ze` \(Standardwert \- Verwenden Sie Microsoft\-Erweiterungen\)  
  
-   `/link` \(LinkerSteuerelement\), `/NOD` \(keine StandardBibliothekssuche\) und `/Ze`  
  
 Weitere Informationen über Compilerbefehlszeilenoptionen, finden Sie unter [Compiler\-Verweis](../build/reference/compiler-options.md).  
  
## Siehe auch  
 [Kompatibilität](../c-runtime-library/compatibility.md)