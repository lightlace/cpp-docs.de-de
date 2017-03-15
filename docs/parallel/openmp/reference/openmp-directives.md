---
title: "OpenMP Directives | Microsoft Docs"
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
ms.assetid: 0562c263-344c-466d-843e-de830d918940
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# OpenMP Directives
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Enthält Links zu \- Direktive bereit, die im OpenMP API verwendet werden.  
  
 Visual C\+\+ unterstützt die folgenden OpenMP\-Direktive:  
  
|Direktive|Beschreibung|  
|---------------|------------------|  
|[atomic](../../../parallel/openmp/reference/atomic.md)|Gibt an, dass eine Speicheradresse an, die atomar aktualisiert wird.|  
|[barrier](../../../parallel/openmp/reference/barrier.md)|Synchronisiert alle Threads in einem Team; Alle Thread pause an der Grenze, bis alle Threads die Barriere ausführen.|  
|[critical](../../../parallel/openmp/reference/critical.md)|Gibt an, dass Code nur auf einem Thread gleichzeitig ausgeführt wird.|  
|[flush](../../../parallel/openmp/reference/flush-openmp.md)|Gibt an, dass alle Threads die gleiche Ansicht des Arbeitsspeichers für alle freigegebenen Objekte haben.|  
|[for](../../../parallel/openmp/reference/for-openmp.md)|Bewirkt, dass die Arbeit, die in eine for\-Schleife innerhalb eines parallelen Bereichs unter Threads aufgeteilt werden sollen.|  
|[master](../../../parallel/openmp/reference/master.md)|Gibt an, dass nur das Vorlagen\-threadshould einen Abschnitt des Programms ausführen.|  
|[ordered](../../../parallel/openmp/reference/ordered-openmp-directives.md)|Gibt an, dass Code mit einer parallelisierten Schleife z. B. für eine sequenzielle Schleife ausgeführt werden soll.|  
|[parallel](../../../parallel/openmp/reference/parallel.md)|Definiert einen parallelen Bereich mit dem Code, der von mehreren Threads parallel ausgeführt werden.|  
|[sections](../../../parallel/openmp/reference/sections-openmp.md)|Identifiziert die von allen Threads aufgeteilt werden soll, Codeabschnitten.|  
|[single](../../../parallel/openmp/reference/single.md)|Hiermit können Sie nicht angeben, dass ein Abschnitt des Codes auf einem einzigen Thread Masterthread, der ausgeführt werden soll.|  
|[threadprivate](../../../parallel/openmp/reference/threadprivate.md)|Gibt an, dass eine Variable zu einem Thread privat ist.|  
  
## Siehe auch  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)