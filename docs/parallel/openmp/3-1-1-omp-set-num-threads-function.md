---
title: 3.1.1 Omp_set_num_threads-Funktion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b94cf2b5-8011-4a3b-ba56-676982642857
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2510c2ed49f7b46f2ca3d853c9b78ff3c09cb62a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="311-ompsetnumthreads-function"></a>3.1.1 omp_set_num_threads-Funktion
Die `omp_set_num_threads` Funktion legt die Standardanzahl von Threads zur Verwendung für nachfolgende parallele Bereiche, die keinen angeben einer `num_threads` Klausel. Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
void omp_set_num_threads(int num_threads);  
```  
  
 Der Wert des Parameters *Num_threads* muss eine positive ganze Zahl sein. Seine Auswirkungen hängt davon ab, ob die dynamische Anpassung der Anzahl der Threads aktiviert ist. Für einen umfassenden Satz von Regeln über die Interaktion zwischen der `omp_set_num_threads` -Funktion und die dynamische Anpassung der Threads, finden Sie in Abschnitt 2.3 auf der Seite "8".  
  
 Diese Funktion wirkt sich die oben beschriebenen, beim Aufrufen durch einen Teil des Programms, in dem die `omp_in_parallel` Funktion gibt 0 (null) zurück. Wenn sie von einem Teil des Programms aufgerufen wird, in dem die `omp_in_parallel` Funktion gibt einen Wert ungleich NULL zurück, das Verhalten dieser Funktion ist nicht definiert.  
  
 Dieser Aufruf hat Vorrang gegenüber der `OMP_NUM_THREADS` -Umgebungsvariablen angegeben. Der Standardwert für die Anzahl der Threads, die durch den Aufruf hergestellt werden kann `omp_set_num_threads` oder durch Festlegen der `OMP_NUM_THREADS` Umgebungsvariablen kann explizit überschrieben werden, auf einem einzelnen **parallele** Richtlinie durch Angabe der `num_threads` Klausel.  
  
## <a name="cross-references"></a>Referenzen:  
  
-   `omp_set_dynamic`funktionieren, finden Sie unter [Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.  
  
-   `omp_get_dynamic`funktionieren, finden Sie unter [Abschnitt 3.1.8](../../parallel/openmp/3-1-8-omp-get-dynamic-function.md) auf Seite "40".  
  
-   `OMP_NUM_THREADS`Umgebung-Variable verwenden, finden Sie unter [Abschnitt 4.2](../../parallel/openmp/4-2-omp-num-threads.md) auf Seite 48 und Abschnitt 2.3 auf Seite "8".  
  
-   `num_threads`-Klausel finden Sie unter [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite 8