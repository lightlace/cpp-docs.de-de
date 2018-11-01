---
title: E. Die Implementierung definiertes Verhalten in OpenMP C/C++
ms.date: 11/04/2016
ms.assetid: b8d660ca-9bb3-4b6b-87af-45c67d43a731
ms.openlocfilehash: 704062f36102a06e6e7b8cf015f6330f925a6bba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619348"
---
# <a name="e-implementation-defined-behaviors-in-openmp-cc"></a>E. Die Implementierung definiertes Verhalten in OpenMP C/C++

In diesem Anhang werden zusammengefasst, die Verhaltensweisen, die als "implementierungsdefinierte" in dieser API beschrieben werden.  Jedes Verhalten ist, um zu der Beschreibung in der main-Spezifikation.

## <a name="remarks"></a>Hinweise

Eine Implementierung ist erforderlich, um zu definieren und Dokumentieren Sie das Verhalten in diesen Fällen, aber diese Liste kann unvollständig sein.

- **Anzahl der Threads:** Wenn ein paralleles Bereichs gefunden wird, während dynamische Anpassung der Anzahl von Threads ist deaktiviert, und die Anzahl der Threads, die für den parallelen Bereich angeforderten die Anzahl, die das Laufzeitsystem angeben können überschreitet, wird das Verhalten von das Programm wird implementierungsdefinierte (siehe Seite 9).

   In Visual C++ werden für einen nicht geschachtelten parallelen Bereichs 64 Threads (die maximale Anzahl) angegeben werden.

- **Anzahl der Prozessoren:** die Anzahl der physischen Prozessoren tatsächlich die Threads hosten, zu jedem Zeitpunkt ist implementierungsdefinierte (siehe Seite 10).

   In Visual C++ wird diese Anzahl ist nicht konstant und wird vom Betriebssystem gesteuert.

- **Erstellen von Teams von Threads:** die Anzahl der Threads in einem Team, das Ausführen ein geschachtelten paralleles Bereichs ist implementierungsdefiniert. () Siehe Seite "10").

   In Visual C++ wird dies vom Betriebssystem bestimmt.

- **Schedule(Runtime)"::** die Entscheidung zur Planung bis zur Laufzeit verzögert wird. Die Zeitplan-Typ und die Block-Größe kann zur Laufzeit ausgewählt werden, durch Festlegen der `OMP_SCHEDULE` -Umgebungsvariablen angegeben. Wenn diese Umgebungsvariable nicht festgelegt ist, ist der daraus resultierende Zeitplan implementierungsdefinierte (siehe Seite 13).

   In Visual C++ Zeitplantyp ist `static` mit keine Segmentgröße.

- **Standardplanungs-:** In der Schedule-Klausel vorhanden ist, der Standardzeitplan wird implementierungsdefinierte (siehe Seite 13).

   In Visual C++ ist der Zeitplan ist `static` mit keine Segmentgröße.

- **ATOMARISCH:** es Implementierung definiert ist, gibt an, ob eine Implementierung ersetzt alle `atomic` Direktiven mit **kritische** Direktiven, die den gleichen eindeutigen Namen (siehe Seite 20) haben.

   In Visual C++, wenn Daten durch geändert [atomic](../../parallel/openmp/reference/atomic.md) befindet sich nicht auf einen natürlichen Ausrichtung, oder ist dies 1 oder 2 Bytes lange alle atomarer Vorgänge, die diese Eigenschaft zu erfüllen einen kritischen Abschnitt verwendet. Andernfalls werden die kritische Abschnitte nicht verwendet werden.

- **Omp_get_num_threads:** , wenn die Anzahl der Threads explizit nicht vom Benutzer festgelegt wurde, der Standardwert ist implementierungsdefiniert (siehe Seite 9, und [Abschnitt 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) auf Seite 37).

   In Visual C++ ist die standardmäßige Anzahl der Threads gleich der Anzahl der Prozessoren.

- **Omp_set_dynamic:** die Standardeinstellung für dynamische Thread Anpassung ist implementierungsdefiniert (finden Sie unter [Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39).

   In Visual C++ ist der Standardwert ist `FALSE`.

- **Omp_set_nested:** Wenn geschachtelte Parallelität aktiviert ist, die Anzahl der Threads, die zum Ausführen von geschachtelten paralleler Bereichen verwendet ist implementierungsdefiniert (finden Sie unter [Abschnitt 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) auf Seite 40).

   In Visual C++ wird die Anzahl der Threads vom Betriebssystem bestimmt.

- `OMP_SCHEDULE` Umgebungsvariable: der Standardwert für diese Umgebungsvariable ist implementierungsdefiniert (finden Sie unter [Abschnitt 4.1](../../parallel/openmp/4-1-omp-schedule.md) auf 48).

   In Visual C++ Zeitplantyp ist `static` mit keine Segmentgröße.

- `OMP_NUM_THREADS` Umgebungsvariable: Wenn kein Wert, für angegeben wird die `OMP_NUM_THREADS` Umgebungsvariablen, oder wenn der angegebene Wert eine positive ganze Zahl ist, oder wenn der Wert größer als die maximale Anzahl von Threads das System unterstützen kann ist, die Anzahl von Threads zur Verwendung wird implementierungsdefinierte (finden Sie unter [Abschnitt 4.2](../../parallel/openmp/4-2-omp-num-threads.md) auf 48).

   In Visual C++ wenn angegebene Wert ist 0 (null) oder weniger, die Anzahl von Threads entspricht der Anzahl der Prozessoren.  Wenn der Wert größer als 64 ist, ist die Anzahl der Threads 64.

- `OMP_DYNAMIC` Umgebungsvariable: der Standardwert ist implementierungsdefiniert (finden Sie unter [Abschnitt-4.3](../../parallel/openmp/4-3-omp-dynamic.md) auf 49).

   In Visual C++ ist der Standardwert ist `FALSE`.