---
title: "4.2 OMP_NUM_THREADS"
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
ms.assetid: 49dd55dd-25d5-4a5a-a998-cc7f47b2dae2
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 4.2 OMP_NUM_THREADS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **OMP\_NUM\_THREADS** Umgebungsvariable wird die standardmäßige Anzahl von Threads fest, die während der Ausführung zu verwenden, es sei denn, diese Zahl explizit geändert werden, indem Sie die **omp\_set\_num\_threads** routine Bibliothek oder durch eine explizite **num\_threads**\-Klausel auf **Ähnlichkeit**\-Direktive aufrufen.  
  
 Der Wert der **OMP\_NUM\_THREADS** Umgebungsvariable muss eine positive ganze Zahl sein.  Der Effekt ist auf ab, ob dynamische Anpassung der Anzahl von Threads aktiviert ist.  Für einen umfassenden Satz von Regeln zur Interaktion zwischen der **OMP\_NUM\_THREADS** Umgebungsvariablen und die dynamische Anpassung von Threads finden Sie im Abschnitt 2.3 auf Seite 8.  
  
 Wenn kein Wert für die **OMP\_NUM\_THREADS** Umgebungsvariable angegeben ist oder wenn der angegebene Wert keine positive ganze Zahl ist, oder wenn der Wert größer als die maximale Anzahl von Threads ist das System unterstützen kann, wird die Anzahl der zu verwendenden Threads Implementierung\-definiert.  
  
 Beispiel:  
  
```  
setenv OMP_NUM_THREADS 16  
```  
  
## Querverweise:  
  
-   **num\_threads**\-Klausel finden [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite 8.  
  
-   **omp\_set\_num\_threads**\-Funktion finden [3.1.1 Abschnitt](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) auf Seite 36.  
  
-   **omp\_set\_dynamic**\-Funktion finden [3.1.7 Abschnitt](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.