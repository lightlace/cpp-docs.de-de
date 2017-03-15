---
title: "OMP_NUM_THREADS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OMP_NUM_THREADS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OMP_NUM_THREADS OpenMP environment variable"
ms.assetid: 4b558124-1387-4c30-a6a5-ff5345a9ced6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# OMP_NUM_THREADS
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Legt die maximale Anzahl von Threads im parallelen Bereichs fest, sofern kein Überschreiben durch [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) oder [num\_threads](../../../parallel/openmp/reference/num-threads.md).  
  
## Syntax  
  
```  
set OMP_NUM_THREADS[=num]  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `num`  
 Die maximale Anzahl von Threads, die Sie im parallelen Bereich soll, und 64 in der Visual C\+\+\-Implementierung.  
  
## Hinweise  
 Die **OMP\_NUM\_THREADS** Umgebungsvariable kann über die [omp\_set\_num\_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)\-Funktion oder durch [num\_threads](../../../parallel/openmp/reference/num-threads.md)überschrieben werden.  
  
 Der Standardwert von `num` in der Visual C\+\+\-Implementierung des OpenMP\-Standards ist die Anzahl der virtuellen Prozessoren, darunter die Hyperthreading CPUs.  
  
 Weitere Informationen finden Sie unter [4.2 OMP\_NUM\_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md).  
  
## Beispiel  
 Mit dem folgenden Befehl wird die **OMP\_NUM\_THREADS** Umgebungsvariable auf 16 fest:  
  
```  
set OMP_NUM_THREADS=16  
```  
  
 Der folgende Befehl zeigt die aktuelle Einstellung der **OMP\_NUM\_THREADS** Umgebungsvariablen an:  
  
```  
set OMP_NUM_THREADS  
```  
  
## Siehe auch  
 [Environment Variables](../../../parallel/openmp/reference/openmp-environment-variables.md)