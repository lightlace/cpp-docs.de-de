---
title: Die Überprüfung auf Speicherüberschreibung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 258aa6ae01d48df6717135f7dc8b73fc3f9e697a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369850"
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