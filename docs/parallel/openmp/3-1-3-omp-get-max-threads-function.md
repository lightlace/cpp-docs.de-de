---
title: "3.1.3 omp_get_max_threads Function"
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
ms.assetid: 5548897c-546e-4d19-b37b-a76f6b30a0a9
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.3 omp_get_max_threads Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **omp\_get\_max\_threads**\-Funktion gibt eine ganze Zahl zurück, die gewährleistet ist, dass mindestens z. B. die Anzahl von Threads so groß sein, die verwendet werden, um ein Team zu erstellen, wenn ein paralleler Bereich ohne eine **num\_threads**\-Klausel im Code an diesem Punkt unterbrochen werden sollen.  Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
int omp_get_max_threads(void);  
```  
  
 Die folgenden Expresse eine Untergrenze für den Wert von **omp\_get\_max\_threads**:  
  
```  
  
threads-used-for-next-team  
 <= omp_get_max_threads  
  
```  
  
 Beachten Sie, dass, wenn ein nachfolgender parallelen Bereich die **num\_threads**\-Klausel verwendet, um eine bestimmte Anzahl von Threads zu bitten, die Garantie für die Untergrenze des Ergebnisses **omp\_get\_max\_threads** , das nicht über ein langes enthält.  
  
 Der Rückgabewert der **omp\_get\_max\_threads**\-Funktion kann verwendet werden, um genügend Speicher für alle Threads im Team dynamisch zu belegen, das sich am folgenden parallelen Bereich gebildet wird.  
  
## Querverweise:  
  
-   **omp\_get\_num\_threads**\-Funktion finden [Abschnitt 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) auf Seite 37.  
  
-   **omp\_set\_num\_threads**\-Funktion finden [3.1.1 Abschnitt](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) auf Seite 36.  
  
-   **omp\_set\_dynamic**\-Funktion finden [3.1.7 Abschnitt](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.  
  
-   **num\_threads**\-Klausel finden [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite 8.