---
title: F. Neue Funktionen und erläuterungen in Version 2.0
ms.date: 01/22/2019
ms.assetid: 0d4beb66-f2d5-468c-8cd3-4b00dcbab061
ms.openlocfilehash: 2e186bbc82f4f43e831dd05cdded2a9e946d1dd2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362711"
---
# <a name="f-new-features-and-clarifications-in-version-20"></a>F. Neue Funktionen und erläuterungen in Version 2.0

In diesem Anhang werden die wichtigsten Änderungen bei der Umstellung von Version 1.0 auf Version 2.0 der OpenMP-C-/C++-Spezifikation zusammengefasst. Die folgenden Elemente sind neue Funktionen, die auf die Spezifikation hinzugefügt:

- Kommas sind zulässig, in OpenMP [Direktiven](2-directives.md#21-directive-format).

- Hinzufügen der `num_threads` Klausel. Mit dieser Klausel können Benutzer eine bestimmte Anzahl von Threads zum Anfordern einer [parallelen Konstrukt](2-directives.md#23-parallel-construct).

- Die [Threadprivate](2-directives.md#271-threadprivate-directive) Richtlinie wurde erweitert, um statische Blockbereich-Variablen zu akzeptieren.

- C99-Arrays mit variabler Länge sind vollständige Typen und können angegeben werden an einer beliebigen Stelle vollständigen Typen sind zulässig, z. B. die Liste der `private`, `firstprivate`, und `lastprivate` Klauseln (finden Sie unter [Abschnitt 2.7.2](2-directives.md#272-data-sharing-attribute-clauses)).

- Eine private Variable in einem parallelen Bereich kann gekennzeichnet werden, [private](2-directives.md#2721-private) erneut in einer geschachtelten-Direktive.

- Die `copyprivate` Klausel hinzugefügt wurde. Es bietet einen Mechanismus, um eine private Variable zu verwenden, um einen Wert von einem Mitglied eines Teams an den anderen Elementen zu übertragen. Es ist eine Alternative zur Verwendung von einer freigegebenen Variable für den Wert, wenn diese eine freigegebene Variable bereitstellen (z. B. in eine Rekursion, erfordern eine andere Variable auf jeder Ebene) schwierig wäre. Die [Copyprivate](2-directives.md#2728-copyprivate) Klausel kann nur verwendet werden, auf die `single` Richtlinie.

- Hinzufügen von Routinen zur zeitlichen Steuerung [Omp_get_wtick](3-run-time-library-functions.md#332-omp_get_wtick-function) und [Omp_get_wtime](3-run-time-library-functions.md#331-omp_get_wtime-function) ähnelt die MPI-Routinen. Diese Funktionen sind erforderlich, um die Uhr Zeitangaben wall.

- Ein Anhang mit einer Liste von [die Implementierung definiertes Verhalten](e-implementation-defined-behaviors-in-openmp-c-cpp.md) in OpenMP C-/C++ wurde hinzugefügt. Eine Implementierung ist erforderlich, um zu definieren und Dokumentieren Sie das Verhalten in diesen Fällen.

- Die folgenden Änderungen dienen, um zu verdeutlichen, oder Korrigieren von Funktionen in der vorherigen OpenMP-API-Spezifikation für C/C++:

  - Es wird erläutert, die das Verhalten der [Omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) und [Omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) beim `omp_in_parallel` gibt, die ungleich NULL ist nicht definiert.

  - Es wird erläutert [-Direktive Schachtelung](2-directives.md#29-directive-nesting) Wenn geschachtelte gleichzeitig verwendet wird.

  - Die [Sperren Initialisierung](3-run-time-library-functions.md#321-omp_init_lock-and-omp_init_nest_lock-functions) und [Sperren Zerstörung](3-run-time-library-functions.md#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions) Funktionen können in einem parallelen Bereich aufgerufen werden.

  - Neue Beispiele wurden hinzugefügt, um [Anhang A](a-examples.md).