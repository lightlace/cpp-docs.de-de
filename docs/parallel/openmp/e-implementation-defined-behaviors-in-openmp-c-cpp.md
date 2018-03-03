---
title: E. Die Implementierung definiertes Verhalten in OpenMP-C-/C++ | Microsoft Docs
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
ms.assetid: b8d660ca-9bb3-4b6b-87af-45c67d43a731
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8fe890248ad2eb3bcee024bf12ccf4039484e7b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="e-implementation-defined-behaviors-in-openmp-cc"></a>E. Die Implementierung definiertes Verhalten in OpenMP-C-/C++
Dieser Anhang enthält eine Zusammenfassung der Verhaltensweisen, die als "implementierungsdefinierte" in dieser API beschrieben werden.  Jedes Verhalten wird Querverweis zurück an seine Beschreibung in der main-Spezifikation.  
  
## <a name="remarks"></a>Hinweise  
 Eine Implementierung zum Definieren und Dokumentieren Sie das Verhalten in diesen Fällen erforderlich ist, aber diese Liste kann unvollständig sein.  
  
-   **Anzahl der Threads:** Wenn ein paralleles Bereichs gefunden wird, während dynamische Anpassung der Anzahl von Threads ist deaktiviert, und die Anzahl der Threads, die für den parallelen Bereich angeforderten die Anzahl, die das Laufzeitsystem angeben können überschreitet, wird das Verhalten von das Programm wird implementierungsdefinierte (siehe Seite 9).  
  
     In Visual C++ werden für einen nicht geschachtelten parallelen Bereichs 64 Threads (Maximum) bereitgestellt werden.  
  
-   **Anzahl der Prozessoren:** die Anzahl der physischen Prozessoren, die tatsächlich hosting Threads zu einem beliebigen Zeitpunkt ist implementierungsdefinierte (siehe Seite 10).  
  
     In Visual C++ ist diese Nummer ist nicht konstant und wird vom Betriebssystem gesteuert.  
  
-   **Erstellen von Teams von Threads:** die Anzahl der Threads in einem Team, das Ausführen ein geschachtelten paralleles Bereichs ist implementierungsdefiniert. () Siehe Seite 10).  
  
     In Visual C++ ist dies vom Betriebssystem bestimmt.  
  
-   **Schedule(Runtime):** die Entscheidung zur Planung bis zur Laufzeit verzögert wird. Die Zeitplan-Typ und Block-Größe zur Laufzeit ausgewählt werden kann, durch Festlegen der `OMP_SCHEDULE` -Umgebungsvariablen angegeben. Wenn diese Umgebungsvariable nicht festgelegt ist, ist die daraus resultierende Zeitplan implementierungsdefinierte (siehe Seite 13).  
  
     In Visual C++ Zeitplantyp ist `static` mit keine Segmentgröße.  
  
-   **Standardplanungs-:** Schedule-Klausel vorhanden ist, der Standardzeitplan ist implementierungsdefinierte (siehe Seite 13).  
  
     In Visual C++ ist der Standardtyp für den Zeitplan ist `static` mit keine Segmentgröße.  
  
-   **ATOMIC:** er gibt an, ob eine Implementierung ersetzt ist implementierungsdefiniert `atomic` Direktiven mit **kritische** Direktiven, die den gleichen eindeutigen Namen (siehe Seite 20) aufweisen.  
  
     In Visual C++, wenn Daten durch geändert [atomic](../../parallel/openmp/reference/atomic.md) befindet sich nicht auf eine natürliche Ausrichtung oder ist er 1 oder 2 Bytes verwenden lange alle atomarische Vorgänge, die diese Eigenschaft erfüllen einen kritischen Abschnitt. Andernfalls werden die kritische Abschnitte nicht verwendet werden.  
  
-   **Omp_get_num_threads:** , wenn die Anzahl der Threads explizit nicht vom Benutzer festgelegt wurde, der Standardwert ist die Implementierung definiertes (siehe Seite 9, und [Abschnitt 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) auf Seite 37).  
  
     In Visual C++ wird die Standardanzahl von Threads gleich der Anzahl der Prozessoren.  
  
-   **Omp_set_dynamic:** die Standardeinstellung für dynamische Thread Anpassung ist die Implementierung definiertes (finden Sie unter [Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39).  
  
     In Visual C++ ist die Standardeinstellung ist `FALSE`.  
  
-   **Omp_set_nested:** Wenn geschachtelte Parallelität aktiviert ist, die Anzahl der Threads, die zum Ausführen von geschachtelten paralleler Regions ist implementierungsdefiniert (finden Sie unter [Abschnitt 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) auf der Seite "40").  
  
     In Visual C++ wird die Anzahl der Threads vom Betriebssystem bestimmt.  
  
-   `OMP_SCHEDULE`Umgebungsvariable: der Standardwert für diese Umgebungsvariable ist implementierungsdefiniert (finden Sie unter [Abschnitt 4.1](../../parallel/openmp/4-1-omp-schedule.md) auf Seite 48).  
  
     In Visual C++ Zeitplantyp ist `static` mit keine Segmentgröße.  
  
-   `OMP_NUM_THREADS`Umgebungsvariable: Wenn kein Wert, für angegeben wird die `OMP_NUM_THREADS` Umgebungsvariable, oder wenn der angegebene Wert eine positive ganze Zahl ist, oder wenn der Wert größer als die maximale Anzahl von Threads das System unterstützen kann ist, die Anzahl von Threads zur Verwendung wird die Implementierung definiertes (finden Sie unter [Abschnitt 4.2](../../parallel/openmp/4-2-omp-num-threads.md) auf Seite 48).  
  
     In Visual C++ wenn angegebene Wert ist 0 (null) oder weniger, die Anzahl der Threads ist gleich der Anzahl der Prozessoren.  Wenn der Wert größer als 64 ist, ist die Anzahl der Threads 64.  
  
-   `OMP_DYNAMIC`Umgebungsvariable: der Standardwert ist die Implementierung definiertes (finden Sie unter [Abschnitt 4.3](../../parallel/openmp/4-3-omp-dynamic.md) auf Seite "49").  
  
     In Visual C++ ist die Standardeinstellung ist `FALSE`.