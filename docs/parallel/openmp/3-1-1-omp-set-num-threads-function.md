---
title: "3.1.1 omp_set_num_threads Function"
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
ms.assetid: b94cf2b5-8011-4a3b-ba56-676982642857
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.1 omp_set_num_threads Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `omp_set_num_threads`\-Funktion legt die Standardanzahl von Threads fest, der für parallele folgenden Bereiche zu verwenden, die keine `num_threads`\-Klausel angeben.  Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
void omp_set_num_threads(int num_threads);  
```  
  
 Der Wert der Parameter *num\_threads* muss eine positive ganze Zahl sein.  Der Effekt ist auf ab, ob dynamische Anpassung der Anzahl von Threads aktiviert ist.  Für einen umfassenden Satz von Regeln zur Interaktion zwischen der `omp_set_num_threads`\-Funktion und der dynamischen Anpassung von Threads finden Sie im Abschnitt 2.3 auf Seite 8.  
  
 Diese Funktion besitzt die Auswirkungen, die oben beschriebenen wenn sie von einem Teil des Programms aufgerufen wird, in dem die `omp_in_parallel`\-Funktion \(null\) zurückgibt.  Wenn sie für einen Teil des Programms aufgerufen wird, in dem die `omp_in_parallel`\-Funktion einen Wert ungleich 0 \(null\) zurückgibt, ist das Verhalten dieser Funktion nicht definiert.  
  
 Dieser Aufruf hat Vorrang vor der `OMP_NUM_THREADS` Umgebungsvariablen.  Der Standardwert für die Anzahl von Threads, die möglicherweise eingerichtet werden, indem `omp_set_num_threads` aufrufen oder indem die `OMP_NUM_THREADS` Umgebungsvariable festgelegt wird, kann für einzelne **Ähnlichkeit**\-Direktive explizit überschrieben werden, indem die `num_threads`\-Klausel angegeben.  
  
## Querverweise:  
  
-   `omp_set_dynamic`\-Funktion finden [3.1.7 Abschnitt](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.  
  
-   `omp_get_dynamic`\-Funktion finden [3.1.8 Abschnitt](../../parallel/openmp/3-1-8-omp-get-dynamic-function.md) auf Seite 40.  
  
-   `OMP_NUM_THREADS` Umgebungsvariablen finden [Abschnitt 4.2](../../parallel/openmp/4-2-omp-num-threads.md) auf Seite 48 und Seite 8, Abschnitt 2.3 auf.  
  
-   `num_threads`\-Klausel finden [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite 8