---
title: "Suchen nach Speicher&#252;berschreibungen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Speicher, Überschreibungen"
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Suchen nach Speicher&#252;berschreibungen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn beim Aufruf einer Funktion, durch die der Heap geändert wird, eine Zugriffsverletzung auftritt, wurde der Heap möglicherweise durch das Programm beschädigt.  Im Folgenden sehen Sie ein übliches Symptom für diese Situation:  
  
```  
Access Violation in _searchseg  
```  
  
 Mithilfe der [\_heapchk](../../c-runtime-library/reference/heapchk.md)\-Funktion kann die Integrität des Heaps für die Laufzeitbibliothek sowohl im Debug\- als auch im Releasebuild \(nur Windows NT\) überprüft werden.  `_heapchk` kann auf ähnliche Weise wie die `AfxCheckMemory`\-Funktion verwendet werden, um eine Heapüberschreibung zu isolieren. Beispiel:  
  
```  
if(_heapchk()!=_HEAPOK)  
   DebugBreak();  
```  
  
 Sollte diese Funktion einmal fehlschlagen, müssen Sie feststellen, an welchem Punkt der Heap beschädigt wurde.  
  
## Siehe auch  
 [Beheben von Problemen mit dem Releasebuild](../../build/reference/fixing-release-build-problems.md)