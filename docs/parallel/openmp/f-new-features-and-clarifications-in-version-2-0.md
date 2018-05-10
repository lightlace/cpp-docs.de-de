---
title: F. Neue Features und Klarstellungen in Version 2.0 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0d4beb66-f2d5-468c-8cd3-4b00dcbab061
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e48f299e66ed1b4c075757a9cd143d0afe897db
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="f-new-features-and-clarifications-in-version-20"></a>F. Neue Features und Klarstellungen in Version 2.0
In diesem Anhang werden die wichtigsten Änderungen an der OpenMP-C-/C++-Spezifikation bei der Umstellung von Version 1.0 auf Version 2.0 vorgenommen zusammengefasst. Die folgenden Elemente sind neue Funktionen, die von der Spezifikation hinzugefügt:  
  
-   Kommas sind zulässig, in der OpenMP-Direktiven ([Abschnitt 2.1](../../parallel/openmp/2-1-directive-format.md) auf Seite 7).  
  
-   Hinzufügen der `num_threads` Klausel. Diese Klausel kann der Benutzer eine bestimmte Anzahl von Threads eines parallelen Konstrukts anfordern ([Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite "8").  
  
-   Die `threadprivate` Richtlinie zur Aufnahme von statischen Blockbereiche Variablen erweitert wurde ([Abschnitt 2.7.1](../../parallel/openmp/2-7-1-threadprivate-directive.md) auf Seite "23").  
  
-   C99-Arrays mit variabler Länge vollständigen Typen sind, und daher kann angegeben werden an einer beliebigen Stelle vollständige Typen sind zulässig, z. B. in den Listen `private`, `firstprivate`, und `lastprivate` Klauseln ([Abschnitt 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite "25").  
  
-   Eine private Variable in einem parallelen Bereich privat erneut in eine geschachtelte Direktive markiert werden ([Abschnitt 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) auf der Seite "25").  
  
-   Die `copyprivate` -Klausel hinzugefügt wurde. Er bietet einen Mechanismus, um eine private Variable zu verwenden, um einen Wert von einem Mitglied eines Teams mit den anderen Mitgliedern zu übertragen. Es ist eine Alternative zur Verwendung einer freigegebenen Variable für den Wert, wenn eine solche freigegebene Variable bereitstellen (z. B. in eine Rekursion, erfordern eine andere Variable auf jeder Ebene) schwierig wäre. Die `copyprivate` Klausel kann nur verwendet werden, auf die **einzelne** Richtlinie ([Abschnitt 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) auf der Seite "32").  
  
-   Hinzufügen von Routinen zur zeitlichen Steuerung `omp_get_wtick` und `omp_get_wtime` die MPI-Routinen ähnelt. Diese Funktionen sind erforderlich zum Ausführen von Taktraten Wall ([Abschnitt 3.3.1](../../parallel/openmp/3-3-1-omp-get-wtime-function.md) auf Seite 44 und [Abschnitt 3.3.2](../../parallel/openmp/3-3-2-omp-get-wtick-function.md) auf Seite "45").  
  
-   Ein Anhang mit einer Liste der Implementierung definierten Verhalten in OpenMP-C-/C++ wurde hinzugefügt. Eine Implementierung zum Definieren und Dokumentieren Sie das Verhalten in diesen Fällen erforderlich ist ([Anhang E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md) auf Seite "97").  
  
-   Die folgenden Änderungen dienen zur Klärung oder korrigieren in der vorherigen OpenMP-API-Spezifikation für C/C++-Funktionen:  
  
    -   Wurde verdeutlicht, dass das Verhalten des `omp_set_nested` und `omp_set_dynamic` Wenn `omp_in_parallel` gibt, die ungleich NULL ist nicht definiert ([Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39 und [Abschnitt 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) auf der Seite "40").  
  
    -   Richtlinie Schachtelung erläutert, geschachtelten parallelen verwendet wird ([Abschnitt 2.9](../../parallel/openmp/2-9-directive-nesting.md) auf Seite "33").  
  
    -   Die Lock-Initialisierung und Sperre Zerstörung-Funktion können aufgerufen werden, in einem parallelen Bereich ([Abschnitt 3.2.1](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md) auf der Seite "42" und [Abschnitt 3.2.2](../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md) auf Seite "42").  
  
    -   Neue Beispiele wurden hinzugefügt ([Anhang A](../../parallel/openmp/a-examples.md) auf Seite 51).