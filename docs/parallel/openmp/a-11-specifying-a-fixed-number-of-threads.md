---
title: "A.11   Specifying a Fixed Number of Threads"
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
ms.assetid: 1d06b142-4c35-44b8-994b-20f2aed5462b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# A.11   Specifying a Fixed Number of Threads
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Einige Programme, prespecified basieren auf einer festen Anzahl von Threads ordnungsgemäß ausgeführt wird.  Da die Standardeinstellung für die dynamische Anpassung der Anzahl von Threads Implementierung\-definiert wird, können solche Programme die dynamische Thread Funktion zu deaktivieren und die Anzahl von Threads explizit festzulegen, um Portabilität sicherzustellen.  Im folgenden Beispiel wird gezeigt, wie dies mit `omp_set_dynamic` \([3.1.7 Abschnitt](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39\) und hat `omp_set_num_threads` \([3.1.1 Abschnitt](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) auf Seite 36\):  
  
```  
omp_set_dynamic(0);  
omp_set_num_threads(16);  
#pragma omp parallel shared(x, npoints) private(iam, ipoints)  
{  
    if (omp_get_num_threads() != 16)   
      abort();  
    iam = omp_get_thread_num();  
    ipoints = npoints/16;  
    do_by_16(x, iam, ipoints);  
}  
```  
  
 In diesem Beispiel führt das Programm einwandfrei nur ausgeführt, wenn er von 16 Threads ausgeführt wird.  Wenn die Implementierung nicht zu unterstützenden 16 Threads Lage ist, ist das Verhalten dieses Beispiels Implementierung\-definiert.  
  
 Beachten Sie, dass die Anzahl der Threads, die einen parallelen Bereich beim Ausführen eines parallelen Bereichs konstant bleibt, unabhängig davon, welche dynamischen Thread festlegen.  Der Mechanismus für den Thread dynamische bestimmt die Anzahl der Threads, die am Anfang des parallelen Bereichs zu verwenden und behält sie konstant für die Dauer des Bereichs.