---
title: "E. Implementation-Defined Behaviors in OpenMP C/C++"
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
ms.assetid: b8d660ca-9bb3-4b6b-87af-45c67d43a731
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# E. Implementation-Defined Behaviors in OpenMP C/C++
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im Anhang wird das Verhalten zusammengefasst, das als „beschriebenen APIs“ in diesem Implementierung\-definiert.  Jedes Verhalten wird auf seine Beschreibung der wichtigsten Spezifikation verwiesen.  
  
## Hinweise  
 Eine Implementierung muss zu definieren und Dokument sein Verhalten in diesen Fällen, aber diese Liste ist unvollständig.  
  
-   **Anzahl von Threads:** , wenn ein paralleler Bereich auftritt, während dynamische Anpassung der Anzahl von Threads deaktiviert ist und die Anzahl der Threads, die für den parallelen Bereich angefordert werden, übersteigt die Zahl, die das Laufzeitsystem bereitstellen kann, das Verhalten des Programms wird Implementierung\-definiert \(siehe Seite 9\).  
  
     In Visual C\+\+ für einen nicht\-geschachtelten parallelen Bereich, werden 64 Threads \(Maximum\) bereitgestellt.  
  
-   **Anzahl von Prozessoren:** die Anzahl der physischen Prozessoren, welche Threads tatsächlich zu einem bestimmten Zeitpunkt hosten, wird Implementierung\-definiert \(siehe Seite 10\).  
  
     In Visual C\+\+ ist diese Zahl nicht konstant und wird vom Betriebssystem gesteuert.  
  
-   **Teams von Threads erstellen:** die Anzahl von Threads in einem Team, die einen geschachtelten parallelen Bereich ausführen, wird Implementierung\-definiert. \(siehe Seite 10\).  
  
     In Visual C\+\+ ist dies vom Betriebssystem bestimmt.  
  
-   **Zeitplan \(Common Language Runtime\):** Planung ist die Entscheidung bezüglich bis zur Laufzeit verzögert.  Der Typ der Zeitplan Segmentgröße und können zur Laufzeit ausgewählt werden, indem die `OMP_SCHEDULE` Umgebungsvariable festgelegt wird.  Diese Umgebungsvariable nicht festgelegt ist, wird der resultierende Zeitplan Implementierung\-definiert \(siehe Seite 13\).  
  
     In Visual C\+\+ ist Typ der Zeitplan `static` ohne Segmentgröße.  
  
-   In Ermangelung**Standard: Planen** der Zeitplan clause, der Standardwert ist Implementierung\-definiert Zeitplan \(siehe Seite 13\).  
  
     In Visual C\+\+ ist der Typ der Zeitplan `static` ohne Segmentgröße.  
  
-   **UNTEILBAR:** wird es Implementierung\-definiert, ob eine Implementierung alle `atomic`\-Direktive durch **Kritisch**\-Direktive ersetzt, die denselben eindeutigen Namen haben \(siehe Seite 20\).  
  
     In Visual C\+\+ wenn die Daten, die von [atomic](../../parallel/openmp/reference/atomic.md) geändert werden, nicht in einer natürlichen Ausrichtung ist oder wenn sie 1 oder 2 Byte lang ist, verwenden alle atomare Operationen mit dieser Eigenschaft entsprechen, einen kritischen Abschnitt.  Andernfalls werden kritische Abschnitte nicht verwendet.  
  
-   **omp\_get\_num\_threads:** , sobald die Anzahl blockierter Threads nicht explizit vom Benutzer festgelegt wurde, der Standardwert ist Implementierung\-definiert \(siehe Seite 9 und [Abschnitt 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) auf Seite 37\).  
  
     In Visual C\+\+ ist die standardmäßige Anzahl von Threads gleich der Anzahl der Prozessoren.  
  
-   **omp\_set\_dynamic:** der Standardwert für dynamische Anpassung der Thread Implementierung\-definiert wird \(siehe [3.1.7 Abschnitt](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39\).  
  
     In Visual C\+\+ ist die Standardeinstellung `FALSE`.  
  
-   **omp\_set\_nested:** , wenn geschachtelter Parallelität aktiviert ist, die Anzahl der Threads, die verwendet werden, um geschachtelte Bereiche parallele Ausführen Implementierung\-definiert wird \(siehe [3.1.9 Abschnitt](../../parallel/openmp/3-1-9-omp-set-nested-function.md) auf Seite 40\).  
  
     In Visual C\+\+ ist die Anzahl der Threads vom Betriebssystem bestimmt.  
  
-   `OMP_SCHEDULE` Umgebungsvariable: Der Standardwert für diese Implementierung\-definiert Umgebungsvariable wird \(siehe [Abschnitt 4.1](../../parallel/openmp/4-1-omp-schedule.md) auf Seite 48\).  
  
     In Visual C\+\+ ist Typ der Zeitplan `static` ohne Segmentgröße.  
  
-   `OMP_NUM_THREADS` Umgebungsvariable: Wenn kein Wert für die `OMP_NUM_THREADS` Umgebungsvariable angegeben ist oder wenn der angegebene Wert keine positive ganze Zahl ist, oder wenn der Wert größer als die maximale Anzahl von Threads ist das System unterstützen kann, wird die Anzahl der zu verwendenden Threads Implementierung\-definiert \(siehe [Abschnitt 4.2](../../parallel/openmp/4-2-omp-num-threads.md) auf Seite 48\).  
  
     In Visual C\+\+ wenn der angegebene Wert keine oder kleiner ist, ist die Anzahl von Threads gleich der Anzahl der Prozessoren.  Wenn der Wert größer als 64 ist, ist die Anzahl von Threads 64.  
  
-   `OMP_DYNAMIC` Umgebungsvariable: Der Standardwert ist Implementierung\-definiert \(siehe [Abschnitt 4.3](../../parallel/openmp/4-3-omp-dynamic.md) auf Seite 49\).  
  
     In Visual C\+\+ ist die Standardeinstellung `FALSE`.