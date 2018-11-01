---
title: F. Neue Funktionen und Erläuterungen in Version 2.0
ms.date: 11/04/2016
ms.assetid: 0d4beb66-f2d5-468c-8cd3-4b00dcbab061
ms.openlocfilehash: c8a597c6af397bd162d92a945d96409b1839e2a3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657147"
---
# <a name="f-new-features-and-clarifications-in-version-20"></a>F. Neue Funktionen und Erläuterungen in Version 2.0

In diesem Anhang werden die wichtigsten Änderungen bei der Umstellung von Version 1.0 auf Version 2.0 der OpenMP-C-/C++-Spezifikation zusammengefasst. Die folgenden Elemente sind neue Funktionen, die auf die Spezifikation hinzugefügt:

- Kommas sind in OpenMP-Anweisungen zulässig ([Abschnitt 2.1](../../parallel/openmp/2-1-directive-format.md) auf Seite 7).

- Hinzufügen der `num_threads` Klausel. Mit dieser Klausel können Benutzer eine bestimmte Anzahl von Threads für eine parallele Konstrukt anfordern ([Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite "8").

- Die `threadprivate` Richtlinie wurde erweitert, um statische Blockbereich-Variablen zu akzeptieren ([Abschnitt 2.7.1](../../parallel/openmp/2-7-1-threadprivate-directive.md) auf Seite 23).

- C99-Arrays mit variabler Länge vollständigen Typen sind, und daher kann angegeben werden an einer beliebigen Stelle vollständige Typen sind zulässig, z. B. in der `private`, `firstprivate`, und `lastprivate` Klauseln ([Abschnitt 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite 25).

- Eine private Variable in einem parallelen Bereich erneut in eine geschachtelte Anweisung privat gekennzeichnet werden kann ([Abschnitt 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) auf Seite 25).

- Die `copyprivate` Klausel hinzugefügt wurde. Es bietet einen Mechanismus, um eine private Variable zu verwenden, um einen Wert von einem Mitglied eines Teams an den anderen Elementen zu übertragen. Es ist eine Alternative zur Verwendung von einer freigegebenen Variable für den Wert, wenn diese eine freigegebene Variable bereitstellen (z. B. in eine Rekursion, erfordern eine andere Variable auf jeder Ebene) schwierig wäre. Die `copyprivate` Klausel kann nur verwendet werden, auf die **einzelne** Richtlinie ([Abschnitt 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) auf Seite "32").

- Hinzufügen von Routinen zur zeitlichen Steuerung `omp_get_wtick` und `omp_get_wtime` ähnelt die MPI-Routinen. Diese Funktionen sind erforderlich, für die Durchführung von Wall-Clock Zeitangaben ([Abschnitt 3.3.1](../../parallel/openmp/3-3-1-omp-get-wtime-function.md) auf Seite 44 und [im Abschnitt 3.3.2](../../parallel/openmp/3-3-2-omp-get-wtick-function.md) auf 45).

- Ein Anhang mit einer Liste von die Implementierung definiertes Verhalten in OpenMP C-/C++ wurde hinzugefügt. Eine Implementierung ist erforderlich, um zu definieren und Dokumentieren Sie das Verhalten in diesen Fällen ([Anhang E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md) auf 97).

- Die folgenden Änderungen dienen, um zu verdeutlichen, oder Korrigieren von Funktionen in der vorherigen OpenMP-API-Spezifikation für C/C++:

   - Wurde verdeutlicht, dass das Verhalten der `omp_set_nested` und `omp_set_dynamic` beim `omp_in_parallel` gibt, die ungleich NULL ist nicht definiert ([Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39, und [Abschnitt 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) auf Seite 40).

   - Direktive Schachtelung erläutert, wenn die geschachtelten parallelen verwendet wird ([Abschnitt 2.9](../../parallel/openmp/2-9-directive-nesting.md) auf Seite 33).

   - Die Zerstörung-Funktionen für die Sperre Initialisierungs- und Sperren können aufgerufen werden, in einem parallelen Bereich ([Abschnitt 3.2.1](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md) auf Seite 42 und [Abschnitt 3.2.2](../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md) auf Seite 42).

   - Neue Beispiele wurden hinzugefügt ([Anhang A](../../parallel/openmp/a-examples.md) auf 51).