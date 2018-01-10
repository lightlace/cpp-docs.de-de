---
title: "Die Überprüfung auf Speicherüberschreibung | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 573710ae62384c8674009770b3c4fb29100db446
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="checking-for-memory-overwrites"></a>Suchen nach Speicherüberschreibungen
Wenn Sie eine zugriffsverletzung bei einem Aufruf an eine Funktion der Heap Manipulation erhalten, ist es möglich, dass das Programm auf den Heap beschädigt ist. Ein häufig auftretendes Problem diese Situation würde folgendermaßen lauten:  
  
```  
Access Violation in _searchseg  
```  
  
 Die [_heapchk](../../c-runtime-library/reference/heapchk.md) -Funktion steht in sowohl Debug- und Releasebuilds (nur Windows NT) zum Überprüfen der Integrität des Heaps zur Laufzeit-Bibliothek. Können Sie `_heapchk` im großen und ganzen genauso wie die `AfxCheckMemory` Funktion, um einen Heap überschreiben, z. B. zu isolieren:  
  
```  
if(_heapchk()!=_HEAPOK)  
   DebugBreak();  
```  
  
 Wenn diese Funktion einmal ein Fehler auftritt, müssen Sie isolieren an diesem, die Punkt der Heap beschädigt wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [Beheben von Problemen mit dem Releasebuild](../../build/reference/fixing-release-build-problems.md)