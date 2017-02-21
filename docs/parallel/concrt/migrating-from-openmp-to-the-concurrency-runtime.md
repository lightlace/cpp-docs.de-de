---
title: "Migrieren von OpenMP zur Concurrency Runtime | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Concurrency Runtime, Migrieren aus OpenMP"
  - "OpenMP, Migrieren in die Concurrency Runtime"
ms.assetid: 9bab7bb1-e45d-44b2-8509-3b226be2c93b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Migrieren von OpenMP zur Concurrency Runtime
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Durch die Concurrency Runtime wird eine Vielzahl von Programmiermodellen ermöglicht.  Diese Modelle können sich mit den Modellen anderer Bibliotheken überschneiden oder diese ergänzen.  In den Dokumenten in diesem Abschnitt wird [OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md) mit der Concurrency Runtime verglichen, und sie enthalten Beispiele, in denen das Migrieren von vorhandenem OpenMP\-Code für die Verwendung der Concurrency Runtime gezeigt wird.  
  
 Das OpenMP\-Programmiermodell ist durch einen offenen Standard definiert und hat klar definierte Verknüpfungen zu den Programmiersprachen Fortran und C\/C\+\+.  Version 2.0 und 2.5 von OpenMP, die vom Visual C\+\+\-Compiler unterstützt werden, eignen sich gut für parallele Algorithmen, die iterativ sind, d. h. eine parallele Iteration über einem Array von Daten ausführen.  OpenMP 3.0 unterstützt zusätzlich zu iterativen Aufgaben auch nicht iterative Aufgaben.  
  
 OpenMP ist am effizientesten, wenn der Grad der Parallelität vordefiniert ist und den auf dem System verfügbaren Ressourcen entspricht.  Das OpenMP\-Modell ist besonders für anspruchsvolle Berechnungen geeignet, wenn äußerst umfangreiche Rechenaufgaben auf die Verarbeitungsressourcen eines Computers verteilt werden.  In diesem Szenario ist die Hardwareumgebung keinen Änderungen unterworfen, und der Entwickler kann davon ausgehen, beim Ausführen des Algorithmus exklusiven Zugriff auf alle Computerressourcen zu haben.  
  
 Andere weniger eingeschränkte Computerumgebungen sind für OpenMP jedoch eventuell weniger geeignet.  Rekursive Probleme \(wie der quicksort\-Algorithmus oder das Suchen einer Datenstruktur\) lassen sich mit OpenMP 2.0 und 2.5 beispielsweise weniger leicht implementieren.  Die Concurrency Runtime ergänzt die Funktionen von OpenMP, indem die [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) und die [Parallel Patterns Library](../../parallel/concrt/parallel-patterns-library-ppl.md) \(PPL\) bereitgestellt werden.  Die Asynchronous Agents Library unterstützt grob strukturierte Aufgabenparallelität, während die PPL differenziertere parallele Aufgaben unterstützt.  Die Concurrency Runtime stellt eine Infrastruktur bereit, die für die parallele Ausführung von Vorgängen erforderlich ist, sodass Sie sich auf die Logik der Anwendung konzentrieren können.  Da die Concurrency Runtime eine Vielzahl von Programmiermodellen ermöglicht, kann der Planungsmehraufwand größer als bei anderen Parallelitätsbibliotheken wie z. B. OpenMP sein.  Daher wird empfohlen, die Leistung inkrementell zu testen, wenn Sie vorhandenen OpenMP\-Code für die Verwendung der Concurrency Runtime konvertieren.  
  
## Wann es sich empfiehlt, OpenMP zur Concurrency Runtime zu migrieren  
 Das Migrieren von vorhandenem OpenMP\-Code zur Concurrency Runtime kann in den folgenden Fällen von Vorteil sein.  
  
|Fälle|Vorteile der Concurrency Runtime|  
|-----------|--------------------------------------|  
|Sie benötigen ein erweiterbares Framework zur parallelen Programmierung.|Viele der in der Concurrency Runtime zur Verfügung stehenden Funktionen können erweitert werden.  Darüber hinaus können Sie durch die Kombination bereits vorhandener Funktionen neue Funktionen schaffen.  Da OpenMP Compilerdirektiven benötigt, lässt es sich nicht so leicht erweitern.|  
|Die Anwendung profitiert von kooperativer Blockierung.|Wenn eine Aufgabe blockiert wird, da sie eine Ressource benötigt, die noch nicht verfügbar ist, kann die Concurrency Runtime andere Aufgaben ausführen, während die erste Aufgabe auf die Ressource wartet.|  
|Die Anwendung profitiert von dynamischem Lastenausgleich.|Die Concurrency Runtime verwendet einen Planungsalgorithmus, der die Zuordnung von Computerressourcen an Änderungen der Arbeitsauslastung anpasst.  Wenn in OpenMP der Planer Computerressourcen einem parallelen Bereich zuordnet, bleiben diese Ressourcen während der Berechnung starr zugeordnet.|  
|Sie benötigen Unterstützung für Ausnahmebehandlung.|Mit der PPL können Sie Ausnahmen sowohl innerhalb als auch außerhalb eines parallelen Bereichs oder einer parallelen Schleife abfangen.  In OpenMP müssen Sie die Ausnahme innerhalb des parallelen Bereichs bzw. innerhalb der parallelen Schleife behandeln.|  
|Sie benötigen einen Abbruchmechanismus.|Die PPL ermöglicht Anwendungen das Abbrechen sowohl von einzelnen Aufgaben als auch von parallelen Arbeitssträngen.  Bei OpenMP muss die Anwendung einen eigenen Abbruchmechanismus implementieren.|  
|Paralleler Code muss in einem anderen Context als dem Anfangskontext beendet werden.|Mit der Concurrency Runtime können Sie eine Aufgabe in einem Kontext beginnen und dann in einem anderen Kontext auf die Aufgabe warten bzw. die Aufgabe in einem anderen Kontext abbrechen.  In OpenMP müssen sämtliche Vorgänge in dem Kontext beendet werden, in dem sie begonnen wurden.|  
|Sie benötigen erweiterte Debugunterstützung.|Visual Studio stellt die Fenster **Parallele Stapel** und **Parallele Aufgaben** bereit, sodass Sie Multithreadanwendungen leichter debuggen können.<br /><br /> Weitere Informationen über Debugunterstützung für die Concurrency Runtime finden Sie unter [Verwenden des Fensters "Aufgaben"](../Topic/Using%20the%20Tasks%20Window.md), [Verwenden des Fensters "Parallele Stapel"](../Topic/Using%20the%20Parallel%20Stacks%20Window.md) und [Exemplarische Vorgehensweise: Debuggen einer parallelen Anwendung](../Topic/Walkthrough:%20Debugging%20a%20Parallel%20Application.md).|  
  
## Wann es sich nicht empfiehlt, OpenMP zur Concurrency Runtime zu migrieren  
 In den folgenden Fällen ist es nicht sinnvoll, vorhandenen OpenMP\-Code zur Concurrency Runtime zu migrieren.  
  
|Fälle|Erklärung|  
|-----------|---------------|  
|Die Anwendung erfüllt bereits Ihre Anforderungen.|Wenn Sie mit der Anwendungsleistung und der aktuellen Debugunterstützung zufrieden sind, ist eine Migration nicht sinnvoll.|  
|Die parallelen Schleifentexte führen einen geringen Umfang an Arbeit aus.|Die Vorteile einer parallelen Ausführung des Schleifentexts überwiegen möglicherweise nicht den Mehraufwand für den Concurrency Runtime\-Taskplaner, insbesondere, wenn der Schleifentext relativ klein ist.|  
|Die Anwendung ist in C geschrieben.|Da die Concurrency Runtime viele C\+\+\-Funktionen verwendet, ist eine Migration möglicherweise nicht sinnvoll, wenn Sie keinen Code schreiben können, der es der C\-Anwendung ermöglicht, die Funktionen umfassend zu nutzen.|  
  
## Verwandte Themen  
 [Gewusst wie: Konvertieren einer parallel\-for\-Schleife in OpenMP zur Verwendung der Concurrency Runtime](../../parallel/concrt/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime.md)  
 Eine einfache Schleife, die OpenMP [Ähnlichkeiten](../../parallel/openmp/reference/parallel.md) und [für](../../parallel/openmp/reference/for-openmp.md)\-Direktive verwendet, veranschaulicht, wie sie konvertiert, um der Concurrency Runtime [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) Algorithmus zu verwenden.  
  
 [Gewusst wie: Konvertieren einer OpenMP\-Schleife mit Abbruch zur Verwendung der Concurrency Runtime](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md)  
 Veranschaulicht, wie eine OpenMP\-[parallel](../../parallel/openmp/reference/parallel.md) [for](../../parallel/openmp/reference/for-openmp.md)\-Schleife, die keine Iterationen erfordert, für die Verwendung des Concurrency Runtime\-Abbruchmechanismus konvertiert wird.  
  
 [Gewusst wie: Konvertieren einer OpenMP\-Schleife, in der die Ausnahmebehandlung verwendet wird, zur Verwendung der Concurrency Runtime](../../parallel/concrt/convert-an-openmp-loop-that uses-exception-handling.md)  
 Veranschaulicht, wie eine OpenMP\-[parallel](../../parallel/openmp/reference/parallel.md) [for](../../parallel/openmp/reference/for-openmp.md)\-Schleife, die Ausnahmebehandlung ausführt, für die Verwendung des Concurrency Runtime\-Ausnahmebehandlungsmechanismus konvertiert wird.  
  
 [Gewusst wie: Konvertieren einer OpenMP\-Schleife, in der eine reduction\-Variable verwendet wird, zur Verwendung der Concurrency Runtime](../../parallel/concrt/convert-an-openmp-loop-that-uses-a-reduction-variable.md)  
 Veranschaulicht, wie eine OpenMP\-[parallel](../../parallel/openmp/reference/parallel.md) [for](../../parallel/openmp/reference/for-openmp.md)\-Schleife, in der die [reduction](../../parallel/openmp/reference/reduction.md)\-Klausel verwendet wird, für die Verwendung der Concurrency Runtime konvertiert wird.  
  
## Siehe auch  
 [Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)   
 [OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Parallel Patterns Library \(PPL\)](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)