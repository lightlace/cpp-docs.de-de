---
title: "OpenMP Environment Variables"
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
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# OpenMP Environment Variables
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Enthält Links zu den Umgebungsvariablen bereit, die im OpenMP API verwendet werden.  
  
 Die Visual C\+\+\-Implementierung des OpenMP\-Standards beinhaltet die folgenden Umgebungsvariablen.  Diese Umgebungsvariablen werden beim Programmstart gelesen und Änderungen an den Werten werden zur Laufzeit ignoriert \(z. B. mithilfe [\_putenv, \_wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)\).  
  
|Umgebungsvariable|Beschreibung|  
|-----------------------|------------------|  
|[OMP\_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)|Gibt an, ob die OpenMP\-Laufzeit die Anzahl von Threads in einem parallelen Bereichs angepasst werden kann.|  
|[OMP\_NESTED](../../../parallel/openmp/reference/omp-nested.md)|Gibt an, ob geschachtelter Parallelität aktiviert ist, es sei denn, geschachtelter Parallelität mit `omp_set_nested`aktiviert oder deaktiviert wird.|  
|[OMP\_NUM\_THREADS](../../../parallel/openmp/reference/omp-num-threads.md)|Legt die maximale Anzahl von Threads im parallelen Bereichs fest, sofern kein Überschreiben durch [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) oder [num\_threads](../../../parallel/openmp/reference/num-threads.md).|  
|[OMP\_SCHEDULE](../../../parallel/openmp/reference/omp-schedule.md)|Ändert das Verhalten der [schedule](../../../parallel/openmp/reference/schedule.md)\-Klausel, wenn `schedule(runtime)` in `for` oder `parallel for`\-Direktive angegeben wird.|  
  
## Siehe auch  
 [Library Reference](../../../parallel/openmp/reference/openmp-library-reference.md)