---
title: 3.1.7 Omp_set_dynamic-Funktion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 1fba961b-b82c-4a1e-ab0f-e4be826e50ab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 87cdd627dd01697fa3d3718a2dc769f4017630a1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="317-ompsetdynamic-function"></a>3.1.7 omp_set_dynamic-Funktion
Die **Omp_set_dynamic** Funktion aktiviert oder deaktiviert die dynamische Anpassung der Anzahl der Threads, die für die Ausführung von parallelen Regionen verfügbar. Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
void omp_set_dynamic(int dynamic_threads);  
```  
  
 Wenn *Dynamic_threads* ergibt einen Wert ungleich NULL, die Anzahl der Threads, die zum Ausführen der nachfolgenden parallele Bereiche verwendet werden kann angepasst werden automatisch von der Umgebung zur Laufzeit auf die Systemressourcen optimal zu nutzen. Daher ist die Anzahl der Threads, die vom Benutzer angegebenen der maximalen Threadanzahl. Die Anzahl der Threads im Team Ausführen eines parallelen Bereichs bleibt für die Dauer von dieser parallelen Bereichs fest und wird gemeldet, indem Sie die **Omp_get_num_threads** Funktion.  
  
 Wenn *Dynamic_threads* ergibt 0, dynamische Anpassung ist deaktiviert.  
  
 Diese Funktion wirkt sich die oben beschriebenen, beim Aufrufen durch einen Teil des Programms, in dem die **Omp_in_parallel** Funktion gibt 0 (null) zurück. Wenn sie von einem Teil des Programms aufgerufen wird, in dem die **Omp_in_parallel** Funktion gibt einen Wert ungleich NULL zurück, das Verhalten dieser Funktion ist nicht definiert.  
  
 Ein Aufruf von **Omp_set_dynamic** hat Vorrang gegenüber der **OMP_DYNAMIC** -Umgebungsvariablen angegeben.  
  
 Die Standardeinstellung für die dynamische Anpassung von Threads ist implementierungsdefiniert. Daher sollten Benutzer-Codes, die von einer bestimmten Anzahl von Threads für die korrekte Ausführung abhängen dynamische Threads explizit deaktivieren. Implementierungen sind nicht erforderlich, um die Möglichkeit, passen Sie die Anzahl der Threads dynamisch bereitzustellen, aber sie sind erforderlich, um die Schnittstelle bereitzustellen, um Portabilität auf allen Plattformen zu unterstützen.  
  
## <a name="cross-references"></a>Referenzen:  
  
-   **Omp_get_num_threads** funktionieren, finden Sie unter [Abschnitt 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) auf Seite 37.  
  
-   **OMP_DYNAMIC** Umgebung-Variable verwenden, finden Sie unter [Abschnitt 4.3](../../parallel/openmp/4-3-omp-dynamic.md) auf Seite "49".  
  
-   **Omp_in_parallel** funktionieren, finden Sie unter [Abschnitt 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) auf Seite 38.