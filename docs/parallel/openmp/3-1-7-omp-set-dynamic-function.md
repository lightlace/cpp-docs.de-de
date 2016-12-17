---
title: "3.1.7 omp_set_dynamic Function"
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
ms.assetid: 1fba961b-b82c-4a1e-ab0f-e4be826e50ab
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.7 omp_set_dynamic Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **omp\_set\_dynamic**\-Funktion aktiviert oder deaktiviert dynamische Anpassung der Anzahl von Threads, die für die Ausführung paralleler Bereichen verfügbar sind.  Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
void omp_set_dynamic(int dynamic_threads);  
```  
  
 Wenn *dynamic\_threads* auf einen Wert ungleich 0 \(null\) ergibt, wird die Anzahl von Threads, die zum Ausführen von folgenden parallelen Bereichen verwendet werden, automatisch von der Laufzeitumgebung auf Systemressourcen verwenden Bestes angepasst werden.  Folglich ist die Anzahl der Threads, die vom Benutzer angegeben werden, die maximale Threadanzahl.  Die Anzahl von Threads im Team, das einen parallelen Bereich ausgeführt wird, bleibt für die Dauer des parallelen Bereichs fest und wird von der **omp\_get\_num\_threads**\-Funktion gemeldet.  
  
 Wenn *dynamic\_threads* auf 0 \(null\) ergibt, wird die dynamische Anpassung deaktiviert.  
  
 Diese Funktion besitzt die Auswirkungen, die oben beschriebenen wenn sie von einem Teil des Programms aufgerufen wird, in dem die **omp\_in\_parallel**\-Funktion \(null\) zurückgibt.  Wenn sie für einen Teil des Programms aufgerufen wird, in dem die **omp\_in\_parallel**\-Funktion einen Wert ungleich 0 \(null\) zurückgibt, ist das Verhalten dieser Funktion nicht definiert.  
  
 Ein Aufruf von **omp\_set\_dynamic** hat Vorrang vor der **OMP\_DYNAMIC** Umgebungsvariablen.  
  
 Der Standardwert für die dynamische Anpassung von Threads wird Implementierung\-definiert.  Daher sollten Benutzercodes, die von einer bestimmten Anzahl von Threads für eine ordnungsgemäße Ausführung abhängen, dynamische Threads explizit deaktivieren.  Implementierungen müssen nicht die Möglichkeit zu geben, die Anzahl der Threads dynamisch anpassen, aber sie sind erforderlich, um die Schnittstelle bereitzustellen, um Portabilität über allen Plattformen zu unterstützen.  
  
## Querverweise:  
  
-   **omp\_get\_num\_threads**\-Funktion finden [Abschnitt 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) auf Seite 37.  
  
-   **OMP\_DYNAMIC** Umgebungsvariablen finden [Abschnitt 4.3](../../parallel/openmp/4-3-omp-dynamic.md) auf Seite 49.  
  
-   **omp\_in\_parallel**\-Funktion finden [3.1.6 Abschnitt](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) auf Seite 38.