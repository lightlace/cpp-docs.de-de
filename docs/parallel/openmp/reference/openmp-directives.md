---
title: OpenMP-Direktiven | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 0562c263-344c-466d-843e-de830d918940
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 51d501139d0610d670f7d646dc985a694a5b741c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|[sortiert](../../../parallel/openmp/reference/ordered-openmp-directives.md)|Gibt diesen Code unter einem parallelisierte Schleife wie eine sequenzielle Schleife ausgeführt werden soll.|  
|[parallel](../../../parallel/openmp/reference/parallel.md)|Definiert einen parallelen Bereich, also Code, die durch mehrere Threads parallel ausgeführt wird.|  
|[Abschnitte](../../../parallel/openmp/reference/sections-openmp.md)|Identifiziert die Codeabschnitte auf allen Threads aufgeteilt werden.|  
|[single](../../../parallel/openmp/reference/single.md)|Sie können angeben, dass ein Abschnitt des Codes in einem einzelnen Thread, der nicht unbedingt der master-Thread ausgeführt werden soll.|  
|[threadprivate](../../../parallel/openmp/reference/threadprivate.md)|Gibt an, dass eine Variable einem Thread zugehörig ist.|  
  
## <a name="see-also"></a>Siehe auch  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)