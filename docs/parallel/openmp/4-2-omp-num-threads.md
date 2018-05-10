---
title: 4.2 OMP_NUM_THREADS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 49dd55dd-25d5-4a5a-a998-cc7f47b2dae2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6b4208d7fe7d453dd1f701d820a85fce5cd68ba
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="42-ompnumthreads"></a>4.2 OMP_NUM_THREADS
Die **OMP_NUM_THREADS** -Umgebungsvariablen angegeben wird die Standardanzahl von Threads zur Verwendung während der Ausführung, sofern diese Anzahl durch den Aufruf nicht explizit geändert wird die **Omp_set_num_threads** Bibliotheksroutine oder ein expliziter **Num_threads** -Klausel für eine **parallele** Richtlinie.  
  
 Der Wert, der die **OMP_NUM_THREADS** -Umgebungsvariable muss eine positive ganze Zahl sein. Seine Auswirkungen hängt davon ab, ob die dynamische Anpassung der Anzahl der Threads aktiviert ist. Für einen umfassenden Satz von Regeln über die Interaktion zwischen der **OMP_NUM_THREADS** Umgebung Variable und dynamische Anpassung der Threads, siehe Abschnitt 2.3 auf Seite "8".  
  
 Wenn kein Wert, für angegeben wird die **OMP_NUM_THREADS** Umgebungsvariable, oder wenn der angegebene Wert eine positive ganze Zahl ist oder wenn der Wert größer als die maximale Anzahl von Threads ist das System kann unterstützt werden, die Anzahl von Threads zur Verwendung ist die Implementierung definiert.  
  
 Beispiel:  
  
```  
setenv OMP_NUM_THREADS 16  
```  
  
## <a name="cross-references"></a>Referenzen:  
  
-   **Num_threads** -Klausel finden Sie unter [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite "8".  
  
-   **Omp_set_num_threads** funktionieren, finden Sie unter [Abschnitt 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) auf Seite 36.  
  
-   **Omp_set_dynamic** funktionieren, finden Sie unter [Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.