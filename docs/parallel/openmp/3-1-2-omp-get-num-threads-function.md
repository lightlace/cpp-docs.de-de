---
title: "3.1.2 omp_get_num_threads Function"
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
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.2 omp_get_num_threads Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **omp\_get\_num\_threads**\-Funktion gibt die Anzahl der Threads gerade im Team zurück, das den parallelen Bereich ausführt, von dem sie aufgerufen wird.  Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
int omp_get_num_threads(void);  
```  
  
 Die **num\_threads**\-Klausel, die **omp\_set\_num\_threads**\-Funktion und die **OMP\_NUM\_THREADS** Umgebungsvariablen die Steuerung der Anzahl von Threads in einem Team.  
  
 Wenn die Anzahl der Threads nicht explizit vom Benutzer festgelegt wurde, wird der Standardwert Implementierung\-definiert.  Diese Funktion zum nächsten übergeordneten **Ähnlichkeit** bindet die Direktive.  Wenn sie aus einem seriellen Teil eines Programms oder einem geschachtelten parallelen Bereich aufgerufen wird, der serialisiert wird, gibt die Funktion 1 zurück.  
  
## Querverweise:  
  
-   **OMP\_NUM\_THREADS** Umgebungsvariablen finden [Abschnitt 4.2](../../parallel/openmp/4-2-omp-num-threads.md) auf Seite 48.  
  
-   **num\_threads**\-Klausel finden [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite 8.  
  
-   **Ähnlichkeit** Konstrukt finden [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite 8.