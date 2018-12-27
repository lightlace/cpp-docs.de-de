---
title: Migrieren von OpenMP zur Concurrency Runtime
ms.date: 11/04/2016
helpviewer_keywords:
- Concurrency Runtime, migrating from OpenMP
- OpenMP, migrating to the Concurrency Runtime
ms.assetid: 9bab7bb1-e45d-44b2-8509-3b226be2c93b
ms.openlocfilehash: 78fa83c30bc55d82ffa5d2ba1e7d65472643f86b
ms.sourcegitcommit: ee0103752884425843556a19cf418a504dc3cd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2018
ms.locfileid: "53737623"
---
# <a name="migrating-from-openmp-to-the-concurrency-runtime"></a>Migrieren von OpenMP zur Concurrency Runtime

Concurrency Runtime ermöglicht eine Vielzahl von Programmiermodellen. Diese Modelle überlappen oder ergänzen die Modelle von anderen Bibliotheken. Die Dokumente in diesem Abschnitt vergleichen [OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp) in die Concurrency Runtime, und geben Sie Beispiele dazu, wie vorhandenen OpenMP-Code, um die Verwendung der Concurrency Runtime zu migrieren.

Das OpenMP-Programmiermodell wird durch einen offenen Standard definiert und verfügt über klar definierte Bindungen zu den Programmiersprachen Fortran und C/C++. OpenMP-Versionen 2.0 und 2.5, das von Visual C++-Compiler unterstützt werden, sind gut geeignet für parallele Algorithmen, die iterativ sind. Das heißt, Sie parallelen Iteration über ein Array von Daten führen. OpenMP 3.0 unterstützt nicht-iterativer Aufgaben zusätzlich zu iterativer Aufgaben.

OpenMP ist am effizientesten, wenn der Grad an Parallelität vorgegeben ist und mit den verfügbaren Ressourcen auf dem System übereinstimmt. Das OpenMP-Modell ist eine besonders gute Übereinstimmung für die High Performance computing, wo sehr große Berechnungsprobleme auf die Verarbeitungsressourcen eines Computers verteilt werden. In diesem Szenario der hardwareumgebung ist im Allgemeinen fest, und der Entwickler kann davon ausgehen, um exklusiven Zugriff auf alle Compute-Ressourcen zu erhalten, wenn der Algorithmus ausgeführt wird.

Jedoch möglicherweise weniger eingeschränkte computerumgebungen eignet sich für OpenMP nicht. Rekursive Probleme (z.B. der Quicksort-Algorithmus oder eine Struktur von Daten zu suchen) sind beispielsweise schwieriger zu implementieren, indem der OpenMP 2.0 und 2.5. Die Concurrency Runtime ergänzt die Funktionen von OpenMP durch die Bereitstellung der [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) und [Parallel Patterns Library](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL). Die Asynchronous Agents Library unterstützten grob strukturierte Aufgabenparallelität Die PPL unterstützt weitere differenzierten Parallele Aufgaben. Die Concurrency Runtime stellt die Infrastruktur, die ist erforderlich, um Vorgänge parallel ausführen, sodass Sie auf die Logik Ihrer Anwendung konzentrieren können. Da die Concurrency Runtime eine Vielzahl von Programmiermodellen ermöglicht, kann seine Planungsaufwand größer als die anderen Concurrency-Bibliotheken wie OpenMP jedoch. Aus diesem Grund empfehlen wir, dass die Leistung inkrementell zu testen, wenn Sie Ihre vorhandenen OpenMP-Code zur Verwendung der Concurrency Runtime konvertieren.

## <a name="when-to-migrate-from-openmp-to-the-concurrency-runtime"></a>Wenn zum Migrieren von OpenMP zur Concurrency Runtime

Es kann zum Migrieren von vorhandenem OpenMP-Code in den folgenden Fällen die Verwendung der Concurrency Runtime vorteilhaft sein.

|Cases|Vorteile der Concurrency Runtime|
|-----------|-------------------------------------------|
|Sie benötigen ein erweiterbares Framework zur parallelen Programmierung.|Viele der Funktionen in der Concurrency Runtime können erweitert werden. Sie können auch vorhandene Funktionen zu neuen Funktionen kombinieren. Da OpenMP Compilerdirektiven benötigt, kann nicht es problemlos erweitert werden.|
|Die Anwendung profitiert von Kooperative Blockierung.|Wenn eine Aufgabe blockiert, da es sich um eine Ressource erfordert, die noch nicht verfügbar ist, kann der Concurrency Runtime, andere Aufgaben ausführen, während die erste Aufgabe wartet, bis die Ressource.|
|Die Anwendung profitiert von den dynamischen Lastenausgleich.|Die Concurrency Runtime verwendet einen scheduling-Algorithmus, der angepasst die Zuordnung wird von Computerressourcen wechselnder Arbeitslast ändert. Wenn der Planer die Computerressourcen zum Ausführen eines parallelen Bereichs ist, belegt, sind diese ressourcenzuordnungen in OpenMP während der Berechnung behoben.|
|Sie benötigen Unterstützung für die Ausnahmebehandlung.|Mit der PPL können Sie das Abfangen von Ausnahmen innerhalb und außerhalb einer parallelen Bereichs oder einer-Schleife. In OpenMP müssen Sie die Ausnahme in den parallelen Bereich oder die Schleife behandeln.|
|Sie benötigen einen Abbruchmechanismus.|Die PPL aktiviert Anwendungen, sowohl einzelne Tasks und Strukturen parallele Arbeitsvorgänge abzubrechen. OpenMP ist erforderlich, die Anwendung einen eigenen Abbruchmechanismus implementiert wird.|
|Sie benötigen die parallelen Code in einem anderen Kontext beendet, in dem er beginnt.|Die Concurrency Runtime können Sie eine Startaufgabe in einem Kontext, und warten Sie dann auf, oder kündigen diese Aufgabe in einem anderen Kontext. In OpenMP muss alle paralleler Arbeitsvorgänge im Kontext abschließen, in dem er beginnt.|
|Sie benötigen eine verbesserte Unterstützung für Remotedebuggen.|Visual Studio bietet die **parallele Stapel** und **Parallele Aufgaben** Windows, damit Sie leichter Multithreadanwendungen Debuggen können.<br /><br /> Weitere Informationen zur debugging-Unterstützung für die Concurrency Runtime finden Sie unter [verwenden das Fenster "Aufgaben"](/visualstudio/debugger/using-the-tasks-window), [verwenden das Fenster "Parallele Stapel"](/visualstudio/debugger/using-the-parallel-stacks-window), und [Exemplarische Vorgehensweise: Debuggen einer parallelen Anwendung](/visualstudio/debugger/walkthrough-debugging-a-parallel-application).|

## <a name="when-not-to-migrate-from-openmp-to-the-concurrency-runtime"></a>Wann Sie nicht von OpenMP zur Concurrency Runtime zu migrieren.

Die folgenden Fällen wird beschrieben, wenn es möglicherweise keine entsprechenden vorhandenen OpenMP-Code, um die Verwendung der Concurrency Runtime zu migrieren.

|Cases|Erklärung|
|-----------|-----------------|
|Die Anwendung bereits erfüllt Ihre Anforderungen.|Wenn Sie mit der Anwendungsleistung und aktuellen Debugunterstützung zufrieden sind, möglicherweise Migration nicht geeignet.|
|Ihre parallelen Schleifenkörpern führen wenig Aufwand.|Der Mehraufwand für die Concurrency Runtime-Aufgabenplaner möglicherweise nicht überwinden, die Vorteile der Textkörper der Schleife parallel ausgeführt werden, insbesondere, wenn der Inhalt der Schleife relativ klein ist.|
|Ihre Anwendung ist in c geschrieben.|Da viele C++-Funktionen in der Concurrency Runtime verwendet wird, kann es nicht geeignet sein, wenn Sie keinen Code schreiben können, die die C-Anwendung vollständig verwenden kann.|

## <a name="related-topics"></a>Verwandte Themen

[Vorgehensweise: Konvertieren einer OpenMP-Parallel for-Schleife in der Concurrency Runtime](../../parallel/concrt/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime.md)

Eine einfache Schleife, die die OpenMP verwendet [parallele](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) und [für](../../parallel/openmp/reference/for-openmp.md) Anweisungen veranschaulicht die Verwendung der Concurrency Runtime konvertiert [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) Algorithmus.

[Vorgehensweise: Konvertieren einer OpenMP-Schleife, die Abbruch verwendet wird, um die Verwendung der Concurrency Runtime](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md)<br/>
Erhalten eine OpenMP [parallele](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[für](../../parallel/openmp/reference/for-openmp.md) Schleife, die nicht alle Iterationen ausgeführt wird, erfordert wird veranschaulicht, wie die Concurrency Runtime-Abbruchmechanismus konvertiert.

[Vorgehensweise: Konvertieren einer OpenMP-Schleife, die Ausnahmebehandlung verwendet wird, um die Verwendung der Concurrency Runtime](../../parallel/concrt/convert-an-openmp-loop-that-uses-exception-handling.md)<br/>
Erhalten eine OpenMP [parallele](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[für](../../parallel/openmp/reference/for-openmp.md) Schleife, die zur Behandlung von Ausnahmen wird veranschaulicht, wie der Ausnahmebehandlungsmechanismus von Concurrency Runtime konvertiert.

[Vorgehensweise: Konvertieren einer OpenMP-Schleife, die keine Reduction-Variable verwendet wird, um die Verwendung der Concurrency Runtime](../../parallel/concrt/convert-an-openmp-loop-that-uses-a-reduction-variable.md)<br/>
Erhält eine OpenMP [parallele](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[für](../../parallel/openmp/reference/for-openmp.md) -Schleife, verwendet der [Verringerung](../../parallel/openmp/reference/reduction.md) -Klausel wird veranschaulicht, wie sie zur Verwendung der Concurrency Runtime zu konvertieren.

## <a name="see-also"></a>Siehe auch

[Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)<br/>
[OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp)<br/>
[Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
[Asynchrone Agents Library](../../parallel/concrt/asynchronous-agents-library.md)

