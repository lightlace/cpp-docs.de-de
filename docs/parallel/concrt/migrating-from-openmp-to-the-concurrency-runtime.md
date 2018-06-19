---
title: Migrieren von OpenMP zur Concurrency Runtime | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Concurrency Runtime, migrating from OpenMP
- OpenMP, migrating to the Concurrency Runtime
ms.assetid: 9bab7bb1-e45d-44b2-8509-3b226be2c93b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 16e10287526e6b815ba56183a8e3d590102507aa
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690487"
---
# <a name="migrating-from-openmp-to-the-concurrency-runtime"></a>Migrieren von OpenMP zur Concurrency Runtime
Concurrency Runtime ermöglicht eine Vielzahl von Programmiermodellen. Diese Modelle überlappen oder ergänzen die Modelle von anderen Bibliotheken. Die Dokumente in diesem Abschnitt vergleichen [OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp) in die Concurrency Runtime und Beispiele zur Vorgehensweise beim Migrieren von vorhandenem OpenMP-Code, um die Verwendung der Concurrency Runtime.  
  
 Das OpenMP-Programmiermodell wird durch einen offenen Standard definiert und verfügt über klar definierte Bindungen zu den Programmiersprachen Fortran und C/C++. OpenMP-Versionen 2.0 und 2.5, die vom Visual C++-Compiler unterstützt werden, eignen sich gut für parallele Algorithmen, die iterativ sind; Das heißt, Sie parallelen Iteration über ein Array von Daten führen. OpenMP 3.0 unterstützt zusätzlich zu iterative Aufgaben nicht iterative Aufgaben.  
  
 OpenMP ist am effizientesten, wenn der Grad an Parallelität vorgegeben ist und mit den verfügbaren Ressourcen auf dem System übereinstimmt. Die OpenMP-Modell ist eine besonders gut geeignet für High Performance computing, in denen sehr große rechnerischen Probleme werden auf der Verarbeitungsressourcen von einem Computer verteilt. In diesem Szenario der hardwareumgebung ist im Allgemeinen fest, und Entwickler kann davon ausgehen, um exklusiven Zugriff auf alle computing-Ressourcen verfügen, wenn der Algorithmus ausgeführt wird.  
  
 Allerdings weniger eingeschränkte computerumgebungen möglichst optimal OpenMP möglicherweise nicht. Rekursive Probleme (z. B. den Quicksort-Algorithmus oder suchen eine Struktur mit Daten) werden z. B. schwieriger zu implementieren, indem der OpenMP 2.0 und 2.5. Die Concurrency Runtime ergänzt die Funktionen von OpenMP durch die Bereitstellung der [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) und [Parallel Patterns Library](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL). Die Asynchronous Agents Library unterstützt groben Aufgabenparallelität; Die PPL unterstützt weitere differenzierten parallelen Aufgaben. Die Concurrency Runtime bietet die Infrastruktur, die ist erforderlich, um Vorgänge parallel ausführen, sodass Sie sich auf die Logik Ihrer Anwendung konzentrieren können. Da der Concurrency Runtime eine Vielzahl von Programmiermodellen ermöglicht, kann seine Planungsaufwand größer als andere Parallelitätsbibliotheken, z. B. von OpenMP jedoch. Aus diesem Grund wird empfohlen, die Leistung inkrementell testen, beim Konvertieren von vorhandenen OpenMP-Codes zur Verwendung der Concurrency Runtime.  
  
## <a name="when-to-migrate-from-openmp-to-the-concurrency-runtime"></a>Wenn zum Migrieren von OpenMP in Concurrency Runtime  
 Es kann zum Migrieren von vorhandenem OpenMP-Code in den folgenden Fällen die Verwendung der Concurrency Runtime vorteilhaft sein.  
  
|Cases|Vorteile der Concurrency Runtime|  
|-----------|-------------------------------------------|  
|Es ist ein erweiterbares Framework zur parallelen Programmierung erforderlich.|Viele der Funktionen in der Concurrency Runtime können erweitert werden. Sie können auch vorhandene Funktionen zu neuen Funktionen kombinieren. Da OpenMP Compilerdirektiven abhängig ist, kann nicht es leicht erweitert werden.|  
|Ihre Anwendung vorteilhaft Kooperative Blockierung.|Wenn eine Aufgabe blockiert, weil eine Ressource erforderlich ist, die noch nicht verfügbar ist, kann der Concurrency Runtime andere Aufgaben ausführen, während die erste Aufgabe wartet, bis die Ressource.|  
|Die Anwendung profitiert von dynamischen Lastenausgleich.|Die Concurrency Runtime verwendet einen Planungsalgorithmus, die die Zuordnung von Computerressourcen, wie die Arbeitslasten ändern anpasst. Wenn der Planer Verarbeitungsressourcen einem parallelen Bereich belegt, werden diese Ressource Zuordnungen in OpenMP während der Berechnung behoben.|  
|Unterstützung für die Ausnahmebehandlung ist erforderlich.|Die PPL können Sie das Abfangen von Ausnahmen, die sowohl innerhalb als auch außerhalb einer parallelen Bereich oder eine Schleife. In OpenMP müssen die Ausnahme in der parallelen Bereichs oder der Schleife behandelt werden.|  
|Sie benötigen einen Abbruchmechanismus.|Die PPL kann Anwendungen einzelne Tasks und paralleler Arbeit-Strukturen "Abbrechen". OpenMP muss die Anwendung einen eigenen Abbruchmechanismus implementieren.|  
|Sie benötigen parallelen Code in einem anderen Kontext abgeschlossen werden, von dem er startet.|Die Concurrency Runtime können Sie die Startaufgabe in einem Kontext, und klicken Sie dann auf warten oder dieses Abbrechen diese Aufgabe in einem anderen Kontext. In OpenMP muss parallelen im Kontext die Fertigstellung aller Aufgaben aus dem er gestartet wird.|  
|Verbesserte debugging-Unterstützung ist erforderlich.|Visual Studio bietet die **parallele Stapel** und **Parallele Aufgaben** Windows, damit Sie leichter Debuggen von Multithreadanwendungen können.<br /><br /> Weitere Informationen zur debugging-Unterstützung für die Concurrency Runtime finden Sie unter [über das Fenster "Aufgaben"](/visualstudio/debugger/using-the-tasks-window), [verwenden das Fenster "Parallele Stapel"](/visualstudio/debugger/using-the-parallel-stacks-window), und [Exemplarische Vorgehensweise: Debuggen einer paralleles Anwendung](/visualstudio/debugger/walkthrough-debugging-a-parallel-application).|  
  
## <a name="when-not-to-migrate-from-openmp-to-the-concurrency-runtime"></a>Wenn nicht zum Migrieren von OpenMP in Concurrency Runtime  
 Die folgenden Fällen beschreiben, wenn es nicht zum Migrieren von vorhandenem OpenMP-Code, um die Verwendung der Concurrency Runtime geeignet sein könnte.  
  
|Cases|Erklärung|  
|-----------|-----------------|  
|Die Anwendung bereits erfüllt Ihre Anforderungen.|Wenn Sie mit der Leistung der Anwendung und der aktuellen Debugunterstützung zufrieden sind, möglicherweise Migration nicht geeignet.|  
|Die parallele Schleifenkörper ausführen wenig Arbeit.|Der Aufwand des Taskplaners der Concurrency Runtime die Vorteile der Schleifentext parallel ausgeführt werden, insbesondere, wenn die Schleife relativ klein ist möglicherweise nicht behoben ist.|  
|Die Anwendung ist in c geschrieben.|Da die Concurrency Runtime viele C++-Funktionen verwenden, nicht geeignet ist möglicherweise, wenn Sie keinen Code schreiben können, die die C-Anwendung vollständig verwenden können.|  
  
## <a name="related-topics"></a>Verwandte Themen  
 [Vorgehensweise: Konvertieren einer parallel-for-Schleife in OpenMP zur Verwendung der Concurrency Runtime](../../parallel/concrt/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime.md)  

 Eine einfache Schleife, die die OpenMP verwendet [parallele](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) und [für](../../parallel/openmp/reference/for-openmp.md) Direktiven veranschaulicht die Verwendung der Concurrency Runtime konvertiert [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) Algorithmus.  

  
 [Vorgehensweise: Konvertieren einer OpenMP-Schleife mit Abbruch zur Verwendung der Concurrency Runtime](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md)  
 Erhält eine OpenMP [parallele](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[für](../../parallel/openmp/reference/for-openmp.md) -Schleife, die nicht alle Iterationen ausgeführt wird, erfordert wird veranschaulicht, wie die Verwendung der Concurrency Runtime-Abbruchmechanismus konvertiert.  
  
 [Vorgehensweise: Konvertieren einer OpenMP-Schleife, in der die Ausnahmebehandlung verwendet wird, zur Verwendung der Concurrency Runtime](../../parallel/concrt/convert-an-openmp-loop-that uses-exception-handling.md)  
 Erhält eine OpenMP [parallele](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[für](../../parallel/openmp/reference/for-openmp.md) Schleife, in der Behandlung von Ausnahmen, führt veranschaulicht, wie die Verwendung der Concurrency Runtime-Ausnahmebehandlungsmechanismus konvertiert.  
  
 [Vorgehensweise: Konvertieren einer OpenMP-Schleife, in der eine reduction-Variable verwendet wird, zur Verwendung der Concurrency Runtime](../../parallel/concrt/convert-an-openmp-loop-that-uses-a-reduction-variable.md)  
 Erhält eine OpenMP [parallele](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[für](../../parallel/openmp/reference/for-openmp.md) -Schleife, verwendet der [Verringerung](../../parallel/openmp/reference/reduction.md) -Klausel, veranschaulicht, wie die Verwendung der Concurrency Runtime konvertiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)   
 [OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp)   
 [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [Asynchrone Agents Library](../../parallel/concrt/asynchronous-agents-library.md)

