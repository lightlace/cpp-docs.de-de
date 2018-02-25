---
title: OpenMP-Direktiven | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 0562c263-344c-466d-843e-de830d918940
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e8d47e6376b3786b27305e65bdb55f0c292995d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="openmp-directives"></a>OpenMP-Anweisungen
Enthält Links zu Anweisungen, die in der OpenMP-API verwendet.  
  
 Visual C++ unterstützt die folgenden OpenMP-Direktiven:  
  
|Direktive|Beschreibung|  
|---------------|-----------------|  
|[atomic](../../../parallel/openmp/reference/atomic.md)|Gibt an, dass eine Speicheradresse, die automatisch aktualisiert werden.|  
|[barrier](../../../parallel/openmp/reference/barrier.md)|Synchronisiert alle Threads in einem Team. Alle Threads anhalten die Barriere, bis alle Threads die Barriere ausführen.|  
|[critical](../../../parallel/openmp/reference/critical.md)|Gibt an, dass Code nur in einem Thread zu einem Zeitpunkt ausgeführt wird.|  
|[flush](../../../parallel/openmp/reference/flush-openmp.md)|Gibt an, dass alle Threads mit derselben Ansicht des Arbeitsspeichers für alle freigegebenen Objekte haben.|  
|[for](../../../parallel/openmp/reference/for-openmp.md)|Bewirkt, dass die Arbeit in einer for-Schleife innerhalb eines parallelen Bereichs zwischen Threads aufgeteilt werden.|  
|[master](../../../parallel/openmp/reference/master.md)|Gibt an, dass nur die master Threadshould einen Abschnitt des Programms ausgeführt.|  
|[ordered](../../../parallel/openmp/reference/ordered-openmp-directives.md)|Gibt diesen Code unter einem parallelisierte Schleife wie eine sequenzielle Schleife ausgeführt werden soll.|  
|[parallel](../../../parallel/openmp/reference/parallel.md)|Definiert einen parallelen Bereich, also Code, die durch mehrere Threads parallel ausgeführt wird.|  
|[sections](../../../parallel/openmp/reference/sections-openmp.md)|Identifiziert die Codeabschnitte auf allen Threads aufgeteilt werden.|  
|[single](../../../parallel/openmp/reference/single.md)|Sie können angeben, dass ein Abschnitt des Codes in einem einzelnen Thread, der nicht unbedingt der master-Thread ausgeführt werden soll.|  
|[threadprivate](../../../parallel/openmp/reference/threadprivate.md)|Gibt an, dass eine Variable einem Thread zugehörig ist.|  
  
## <a name="see-also"></a>Siehe auch  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)