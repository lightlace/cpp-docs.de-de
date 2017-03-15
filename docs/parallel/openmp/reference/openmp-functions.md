---
title: "OpenMP Functions | Microsoft Docs"
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
ms.assetid: a55a2e5c-a260-44ee-bbd6-de7e2351b384
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# OpenMP Functions
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Enthält Links zu den Features bereit, die im OpenMP API verwendet werden.  
  
 Die Visual C\+\+\-Implementierung des OpenMP\-Standards enthält die folgenden Funktionen.  
  
|Funktion|Beschreibung|  
|--------------|------------------|  
|[omp\_destroy\_lock](../../../parallel/openmp/reference/omp-destroy-lock.md)|Deinitialisiert eine Sperre.|  
|[omp\_destroy\_nest\_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)|Deinitialisiert eine schachtelbare Sperre.|  
|[omp\_get\_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md)|Gibt einen Wert zurück, der angibt, ob die Anzahl der Threads, die im Folgenden parallelen Bereich verfügbar sind, von der Laufzeit angepasst werden kann.|  
|[omp\_get\_max\_threads](../../../parallel/openmp/reference/omp-get-max-threads.md)|Gibt eine ganze Zahl ist, die größer oder gleich der Anzahl von Threads zurück, die verfügbar sein, wenn ein paralleler Bereich ohne [num\_threads](../../../parallel/openmp/reference/num-threads.md) an dieser Stelle im Code definiert wurden.|  
|[omp\_get\_nested](../../../parallel/openmp/reference/omp-get-nested.md)|Gibt einen Wert zurück, der angibt, ob ein geschachtelter Parallelität aktiviert ist.|  
|[omp\_get\_num\_procs](../../../parallel/openmp/reference/omp-get-num-procs.md)|Gibt die Anzahl der Prozessoren zurück, die verfügbar sind, wenn die Funktion aufgerufen wird.|  
|[omp\_get\_num\_threads](../../../parallel/openmp/reference/omp-get-num-threads.md)|Gibt die Anzahl der Threads im parallelen Bereichs zurück.|  
|[omp\_get\_thread\_num](../../../parallel/openmp/reference/omp-get-thread-num.md)|Gibt die Thread Nummer des Threads zurück, der innerhalb des Teams Thread ausgeführt wird.|  
|[omp\_get\_wtick](../../../parallel/openmp/reference/omp-get-wtick.md)|Gibt die Anzahl der Sekunden zwischen Prozessor teilstrichen zurück.|  
|[omp\_get\_wtime](../../../parallel/openmp/reference/omp-get-wtime.md)|Gibt den Wert der verstrichenen Zeit in Sekunden zwischen einem Punkt zurück.|  
|[omp\_in\_parallel](../../../parallel/openmp/reference/omp-in-parallel.md)|Gibt Wert ungleich 0 \(null\) zurück, wenn Sie innerhalb eines parallelen Bereichs aufgerufen werden.|  
|[omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md)|Initialisiert eine einfache Zuweisung.|  
|[omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)|Initialisiert eine Sperre.|  
|[omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)|Gibt an, dass die Anzahl der Threads, die im Folgenden parallelen Bereich verfügbar sind, von der Laufzeit angepasst werden kann.|  
|[omp\_set\_lock](../../../parallel/openmp/reference/omp-set-lock.md)|Threads blockiert die Ausführung, bis die Sperre verfügbar ist.|  
|[omp\_set\_nest\_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)|Threads blockiert die Ausführung, bis die Sperre verfügbar ist.|  
|[omp\_set\_nested](../../../parallel/openmp/reference/omp-set-nested.md)|Ermöglicht geschachtelten Parallelität.|  
|[omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)|Legt die Anzahl der Threads in den folgenden Bereichen paralleler fest, sofern kein Überschreiben durch eine [num\_threads](../../../parallel/openmp/reference/num-threads.md)\-Klausel.|  
|[omp\_test\_lock](../../../parallel/openmp/reference/omp-test-lock.md)|Versucht, eine Sperre festzulegen, blockiert aber nicht Thread ausgeführt werden.|  
|[omp\_test\_nest\_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)|Versucht, eine Sperre festzulegen schachtelbare Ausführung der Thread blockiert aber nicht.|  
|[omp\_unset\_lock](../../../parallel/openmp/reference/omp-unset-lock.md)|Gibt eine Sperre.|  
|[omp\_unset\_nest\_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)|Gibt eine schachtelbare Sperre.|  
  
## Siehe auch  
 [Library Reference](../../../parallel/openmp/reference/openmp-library-reference.md)