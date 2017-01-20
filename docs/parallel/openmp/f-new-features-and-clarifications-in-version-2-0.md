---
title: "F. New Features and Clarifications in Version 2.0"
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
ms.assetid: 0d4beb66-f2d5-468c-8cd3-4b00dcbab061
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# F. New Features and Clarifications in Version 2.0
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im Anhang sind die Tonartwechsel zusammengefasst, die der Spezifikation OpenMPs C\/C\+\+ vorgenommen werden, wenn er der Version 1.0 und Version 2.0 verschoben wird.  Die folgenden Elemente sind die neuen Funktionen, die der Spezifikation hinzugefügt werden:  
  
-   Kommas sind in OpenMP\-Direktiven zulässig \([Abschnitt 2.1](../../parallel/openmp/2-1-directive-format.md) auf Seite 7\).  
  
-   Einführung der `num_threads`\-Klausel.  Diese Klausel ermöglicht es Benutzern, eine bestimmte Anzahl von Threads für ein paralleles Konstrukt \(anzufordern[Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite 8\).  
  
-   Die `threadprivate`\-Direktiven sind so erweitert, dass Blockbereichs statische Variablen \([2.7.1 Abschnitt](../../parallel/openmp/2-7-1-threadprivate-directive.md) auf Seite 23\) zu übernehmen.  
  
-   C99 Arrays variabler Länge haben vollständige Typen und können daher beliebig angegebene vollständige Typen zugelassen werden sein, z. B. in den Listen der `private`, `firstprivate`und `lastprivate`\-Klauseln \([2.7.2 Abschnitt](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite 25\).  
  
-   Eine private Variable in einem parallelen Bereich kann in geschachtelten \- Direktive \([2.7.2.1 Abschnitt](../../parallel/openmp/2-7-2-1-private.md) auf Seite 25\) erneut als privat markiert sein.  
  
-   Die `copyprivate`\-Klausel wurde hinzugefügt.  Sie stellt einen Mechanismus bereit, um eine private Variable zu verwenden, um einen Wert aus einköpfigem eines Teams zu den anderen Membern zu übertragen.  Dies ist eine Alternative zur Verwendung einer freigegebenen Variablen für den Wert, wenn eine solche freigegebene Variablen bereitstellen kann schwierig sein \(z. B. in einer Rekursion, die eine andere Variable auf jeder Ebene erforderlich.\)  Die `copyprivate`\-Klausel kann auf dem **Einfach**\-Direktive \([2.7.2.8 Abschnitt](../../parallel/openmp/2-7-2-8-copyprivate.md) auf Seite 32\) nur angezeigt werden.  
  
-   Hinzufügen von Routinen `omp_get_wtick` und `omp_get_wtime` der zeitlichen Steuerung, ähnlich den MPI\-Routinen.  Diese Funktionen sind für das Ausführen von Wanduhr zeitlichen steuerungen notwendig \([Abschnitt 3.3.1](../../parallel/openmp/3-3-1-omp-get-wtime-function.md) auf Seite 44 und [Abschnitt 3.3.2](../../parallel/openmp/3-3-2-omp-get-wtick-function.md) auf Seite 45\).  
  
-   Ein Anhang mit einer Liste von Implementierung\-definierten Verhaltens in C\/C\+\+ OpenMP wurde hinzugefügt.  Eine Implementierung muss zu definieren und Dokument sein Verhalten in diesen Fällen \([Anhang E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md) auf Seite 97\).  
  
-   Die folgenden Änderungen in der vorherigen Funktionen dienen, OpenMPs API für C\/C\+\+ Spezifikation zu bestätigen oder zu korrigieren:  
  
    -   Erläutert, dass das Verhalten von `omp_set_nested` und `omp_set_dynamic` , wenn `omp_in_parallel`\-Wert ungleich 0 \(null\) zurückgibt, undefined ist \([3.1.7 Abschnitt](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39 und [3.1.9 Abschnitt](../../parallel/openmp/3-1-9-omp-set-nested-function.md) auf Seite 40\).  
  
    -   Erklärte richtungweisende Schachtelung, wenn geschachtelte Ähnlichkeit verwendet wird \([Abschnitt 2.9](../../parallel/openmp/2-9-directive-nesting.md) auf Seite 33\).  
  
    -   Die Lock zerstörungs Initialisierung und die Sperren Funktionen können in einem parallelen Bereichs \([3.2.1 Abschnitt](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md) auf Seite 42 und Seite 42 auf [3.2.2 Abschnitt](../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md) \) aufgerufen werden.  
  
    -   Neue Beispiele wurden hinzugefügt \([Anhang A](../../parallel/openmp/a-examples.md) auf Seite 51\).