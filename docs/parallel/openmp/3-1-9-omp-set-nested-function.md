---
title: "3.1.9 omp_set_nested Function"
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
ms.assetid: e4afc3aa-bb96-4314-9849-fd5df5f437d9
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.9 omp_set_nested Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **omp\_set\_nested**\-Funktion aktiviert oder deaktiviert geschachtelten Parallelität.  Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
void omp_set_nested(int nested);  
```  
  
 Wenn Sie *geschachtelt sind,* wertet bis 0, wird geschachtelter Parallelität deaktiviert, der Standardwert ist, und geschachtelten parallelen Bereiche werden vom aktuellen Thread serialisiert und ausgeführt.  Wenn Sie *geschachtelt sind,* wertet auf einen Wert ungleich 0 \(null\), wird geschachtelter Parallelität aktiviert, und parallele Bereiche, die geschachtelt sind, stellen möglicherweise zusätzliche Threads bereit, um geschachtelte Teams zu bilden.  
  
 Diese Funktion besitzt die Auswirkungen, die oben beschriebenen wenn sie von einem Teil des Programms aufgerufen wird, in dem die **omp\_in\_parallel**\-Funktion \(null\) zurückgibt.  Wenn sie für einen Teil des Programms aufgerufen wird, in dem die **omp\_in\_parallel**\-Funktion einen Wert ungleich 0 \(null\) zurückgibt, ist das Verhalten dieser Funktion nicht definiert.  
  
 Dieser Aufruf hat Vorrang vor der **OMP\_NESTED** Umgebungsvariablen.  
  
 Wenn geschachtelter Parallelität aktiviert ist, wird die Anzahl der Threads, die verwendet werden, um geschachtelte Bereiche parallele Ausführen Implementierung\-definiert.  Daher werden OpenMP\-kompatiblen Implementierungen ermöglicht, dass parallele geschachtelte Bereiche zu serialisieren, auch wenn geschachtelter Parallelität aktiviert ist.  
  
## Querverweise:  
  
-   **OMP\_NESTED** Umgebungsvariablen finden [Abschnitt 4.4](../../parallel/openmp/4-4-omp-nested.md) auf Seite 49.  
  
-   **omp\_in\_parallel**\-Funktion finden [3.1.6 Abschnitt](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) auf Seite 38.