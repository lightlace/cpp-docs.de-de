---
title: E. Die Implementierung definiertes Verhalten in OpenMP C/C++
ms.date: 01/22/2019
ms.assetid: b8d660ca-9bb3-4b6b-87af-45c67d43a731
ms.openlocfilehash: 3d8e9493cad1fce02e5d482cd5e612afb44bb37b
ms.sourcegitcommit: 382e247c0f1b4cb7c2dab837b8b6fdff24bff47a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2019
ms.locfileid: "55087222"
---
# <a name="e-implementation-defined-behaviors-in-openmp-cc"></a>E. Die Implementierung definiertes Verhalten in OpenMP C/C++

In diesem Anhang werden zusammengefasst, die Verhaltensweisen, die als "implementierungsdefinierte" in dieser API beschrieben werden.  Jedes Verhalten ist, um zu der Beschreibung in der main-Spezifikation.

## <a name="remarks"></a>Hinweise

Eine Implementierung ist erforderlich, um zu definieren und Dokumentieren Sie das Verhalten in diesen Fällen, aber diese Liste kann unvollständig sein.

- **Anzahl von Threads:** Wenn es sich bei ein paralleler Bereich gefunden wird, während dynamische Anpassung der Anzahl von Threads ist deaktiviert, und die Anzahl der Threads, die für den parallelen Bereich angefordert wird, mehr als die Zahl, die das System zur Laufzeit bereitstellen kann, ist das Verhalten des Programms Implementierung definiert (siehe Seite 9).

   In Visual C++ werden für einen nicht geschachtelten parallelen Bereichs 64 Threads (die maximale Anzahl) angegeben werden.

- **Die Anzahl der Prozessoren:** Die Anzahl der physischen Prozessoren tatsächlich die Threads hosten, zu jedem Zeitpunkt ist implementierungsdefinierte (siehe Seite 10).

   In Visual C++ diese Nummer ist nicht konstant und wird vom Betriebssystem gesteuert.

- **Erstellen von Teams von Threads aus:** Die Anzahl der Threads in einem Team, die ausführen ein geschachtelten paralleles Bereichs ist implementierungsdefinierte (siehe Seite 10).

   In Visual C++ wird diese Zahl vom Betriebssystem bestimmt.

- **schedule(runtime):** Die Entscheidung zum Erstellen eines Zeitplans wird erst zur Laufzeit verzögert. Die Zeitplan-Typ und die Block-Größe kann zur Laufzeit ausgewählt werden, durch Festlegen der `OMP_SCHEDULE` -Umgebungsvariablen angegeben. Wenn diese Umgebungsvariable nicht festgelegt ist, ist der daraus resultierende Zeitplan implementierungsdefinierte (siehe Seite 13).

   In Visual C++ Zeitplantyp ist `static` mit keine Segmentgröße.

- **Standardmäßig planen:** In der Schedule-Klausel vorhanden ist wird der Standardzeitplan implementierungsdefinierte (siehe Seite 13).

   In Visual C++ ist der Zeitplan ist `static` mit keine Segmentgröße.

- **ATOMIC:** Es gibt an, ob eine Implementierung ersetzt alle ist implementierungsdefiniert `atomic` Direktiven mit `critical` Direktiven, die den gleichen eindeutigen Namen (siehe Seite 20) haben.

   In Visual C++, wenn Daten durch geändert [atomic](reference/openmp-directives.md#atomic) befindet sich nicht in einer natürlichen Ausrichtung oder wenn sie ein oder zwei Bytes lang ist, verwenden alle atomarer Vorgänge, die diese Eigenschaft entsprechen einem kritischen Abschnitt. Andernfalls wird nicht kritische Abschnitte verwendet werden.

- **[omp_get_num_threads](3-run-time-library-functions.md#312-omp_get_num_threads-function):** Wenn die Anzahl der Threads nicht explizit vom Benutzer festgelegt wurde, ist der Standardwert implementierungsdefinierte (siehe Seite 9).

   In Visual C++ ist die standardmäßige Anzahl der Threads gleich der Anzahl der Prozessoren.

- **[omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function):** Die Standardeinstellung für dynamische Thread Anpassung ist implementierungsdefiniert.

   In Visual C++ ist der Standardwert ist `FALSE`.

- **[omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function):** Wenn geschachtelte Parallelität aktiviert ist, wird die Anzahl der Threads, die zum Ausführen von geschachtelten paralleler Bereichen verwendet die Implementierung definiert.

   In Visual C++ wird die Anzahl der Threads vom Betriebssystem bestimmt.

- [OMP_SCHEDULE](4-environment-variables.md#41-omp_schedule) -Umgebungsvariablen angegeben: Der Standardwert für diese Umgebungsvariable wird die Implementierung definiert.

   In Visual C++ Zeitplantyp ist `static` mit keine Segmentgröße.

- [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads) -Umgebungsvariablen angegeben: Wenn kein Wert, für angegeben wird die `OMP_NUM_THREADS` Umgebungsvariablen, oder wenn der angegebene Wert ist eine positive ganze Zahl nicht oder wenn der Wert größer als die maximale Anzahl von Threads das System unterstützen kann ist, die Anzahl der zu verwendenden Threads implementierungsdefiniert ist.

   In Visual C++ wenn angegebene Wert ist 0 (null) oder weniger, die Anzahl von Threads entspricht der Anzahl der Prozessoren.  Wenn der Wert größer als 64 ist, ist die Anzahl der Threads 64.

- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic) -Umgebungsvariablen angegeben: Der Standardwert ist die Implementierung definiert.

   In Visual C++ ist der Standardwert ist `FALSE`.