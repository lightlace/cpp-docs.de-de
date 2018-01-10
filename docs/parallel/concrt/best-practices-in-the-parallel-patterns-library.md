---
title: "Bewährte Methoden in der Parallel Patterns Library | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Parallel Patterns Library, practices to avoid
- practices to avoid, Parallel Patterns Library
- best practices, Parallel Patterns Library
- Parallel Patterns Library, best practices
ms.assetid: e43e0304-4d54-4bd8-a3b3-b8673559a9d7
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 40629b25ebcc954ac19389fbc0abb3aef6e9374a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="best-practices-in-the-parallel-patterns-library"></a>Empfohlene Vorgehensweisen in der Parallel Patterns Library
Dieses Dokument beschreibt die optimale, effektive Nutzung der Parallel Patterns Library (PPL). Die PPL bietet allgemeine Container, Objekte und Algorithmen zum Ausführen von differenziertem Parallelismus.  
  
 Weitere Informationen zur PPL finden Sie unter [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md).  
  
##  <a name="top"></a> Abschnitte  
 Dieses Dokument enthält folgende Abschnitte:  
  
- [Kleine Schleifenkörper nicht parallelisieren](#small-loops)  
  
- [Parallelität auf der höchstmöglichen Ebene Ausdrücken](#highest)  
  
- [Parallel_invoke zum Lösen von Divide-and-Conquer-Problemen](#divide-and-conquer)  
  
- [Verwenden Sie Abbruch und Ausnahmebehandlung zum Verlassen einer Parallelschleife](#breaking-loops)  
  
- [Verstehen, wie Abbruch und Ausnahmebehandlung auf die Zerstörung auswirken](#object-destruction)  
  
- [In einer parallelen Schleife kein wiederholtes blockieren](#repeated-blocking)  
  
- [Führen Sie keine Blockierungsvorgänge beim Abbrechen paralleler Aufgaben](#blocking)  
  
- [Nicht auf freigegebene Daten in einer parallelen Schleife schreiben](#shared-writes)  
  
- [Vermeiden Sie False Sharing nach Möglichkeit](#false-sharing)  
  
- [Stellen Sie sicher, dass Variablen während der gesamten Lebensdauer einer Aufgabe gültig sind.](#lifetime)  
  
##  <a name="small-loops"></a>Kleine Schleifenkörper nicht parallelisieren  
 Die Parallelisierung von relativ kleinen Schleifenkörpern kann dazu führen, dass der entsprechende Planungsaufwand die Vorteile der parallelen Verarbeitung zunichte machen. Betrachten Sie das folgende Beispiel, das jedes Elementpaar in zwei Arrays hinzufügt.  
  
 [!code-cpp[concrt-small-loops#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_1.cpp)]  
  
 Die Arbeitsauslastung für jede Iteration der parallelen Schleife ist zu klein, um vom Aufwand für die parallele Verarbeitung zu profitieren. Sie können die Leistung dieser Schleife verbessern, indem Sie mehr Arbeit im Schleifenkörper oder durch das serielle Ausführen der Schleife erledigen.  
  
 [[Nach oben](#top)]  
  
##  <a name="highest"></a>Parallelität auf der höchstmöglichen Ebene Ausdrücken  
 Wenn Sie Code nur auf niedriger Ebene parallelisieren, können Sie ein Fork-Join-Konstrukt einführen, das nicht mit der steigenden Anzahl der Prozessoren skaliert. Ein *Fork-Join* -Konstrukt ist ein Konstrukt, in dem eine Aufgabe seine Arbeit in kleinere parallele Unteraufgaben unterteilt und dieser Unteraufgaben wartet. Jede Unteraufgabe kann sich selbst rekursiv auf weitere Unteraufgaben aufteilen.  
  
 Obwohl das Fork-Join-Modell zur Lösung verschiedener Probleme hilfreich sein kann, gibt es Situationen, in denen der Synchronisierungsaufwand die Skalierbarkeit verringern kann. Betrachten Sie beispielsweise den folgenden seriellen Code, der Bilddaten verarbeitet.  
  
 [!code-cpp[concrt-image-processing-filter#20](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_2.cpp)]  
  
 Da jede Schleifeniteration unabhängig ist, können Sie einen Großteil der Arbeit parallelisieren, wie im folgenden Beispiel gezeigt wird. Dieses Beispiel verwendet die [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) -Algorithmus zum parallelisieren der äußeren Schleife.  

  
 [!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_3.cpp)]  
  
 Das folgende Beispiel veranschaulicht ein Fork-Join-Konstrukt durch Aufrufen der `ProcessImage`-Funktion in einer Schleife. Jeder Aufruf von `ProcessImage` wird erst zurückgegeben, wenn jede Unteraufgabe abgeschlossen ist.  
  
 [!code-cpp[concrt-image-processing-filter#21](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_4.cpp)]  
  
 Wenn jede Iteration der parallelen Schleife fast keine Arbeit ausführt oder die Arbeit, die von der parallelen Schleife ausgeführt wird, unausgeglichenen ist, d. h. einige Schleifeniterationen dauern länger als andere, kann der Planungsaufwand, der erforderlich ist, um Arbeit häufig aufzuteilen und zu verknüpfen, die Vorteile für die parallele Ausführung überwiegen. Dieser Aufwand nimmt mit der Anzahl der Prozessoren zu.  
  
 Um den Planungsaufwand in diesem Beispiel zu reduzieren, können Sie äußere Schleifen parallelisieren, bevor Sie innere Schleifen parallelisieren, oder Sie verwenden ein anderes paralleles Konstrukt, z. B. Pipelines. Im folgende Beispiel ändert die `ProcessImages` Funktion verwendet die [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) -Algorithmus zum parallelisieren der äußeren Schleife.  

  
 [!code-cpp[concrt-image-processing-filter#22](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_5.cpp)]  
  
 Ein ähnliches Beispiel, die eine Pipeline verwendet, um bildverarbeitung parallel auszuführen, finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer Bildverarbeitungsnetzwerks](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="divide-and-conquer"></a>Parallel_invoke zum Lösen von Divide-and-Conquer-Problemen  

 Ein *Divide-and-conquer* -Problem ist eine Form des Fork-Join-Konstrukts, das Rekursion verwendet, um eine Aufgabe in Unteraufgaben zu unterteilen. Zusätzlich zu den [Concurrency:: task_group](reference/task-group-class.md) und [Concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) Klassen, können Sie auch die [Concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) -Algorithmus Divide-and-conquer-Probleme zu lösen. Die `parallel_invoke`-Algorithmus verfügt über eine kompaktere Syntax als Aufgabengruppenobjekte und ist nützlich, wenn Sie eine feste Anzahl paralleler Aufgaben haben.  
  
 Das folgende Beispiel veranschaulicht die Verwendung des `parallel_invoke`-Algorithmus zum Implementieren des bitonischen Sortieralgorithmus.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#12](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_6.cpp)]  
  
 Mit dem `parallel_invoke`-Algorithmus wird der Aufwand reduziert, indem die letzte einer Reihe von Aufgaben im aufrufenden Kontext ausgeführt wird.  
  
 Die vollständige Version dieses Beispiels, finden Sie unter [wie: Verwenden von Parallel_invoke auf parallele Sortierung Schreiben einer](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md). Weitere Informationen zu den `parallel_invoke` -Algorithmus finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="breaking-loops"></a>Verwenden Sie Abbruch und Ausnahmebehandlung zum Verlassen einer Parallelschleife  
 Die PPL bietet zwei Möglichkeiten, um parallele Arbeitsvorgänge abzubrechen, die von einer Aufgabengruppe oder einem parallelen Algorithmus ausgeführt werden. Eine Möglichkeit ist die Verwendung der Abbruchmechanismus, die von bereitgestellte der [Concurrency:: task_group](reference/task-group-class.md) und [Concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) Klassen. Eine andere Möglichkeit ist das Auslösen einer Ausnahme im Text einer Arbeitsfunktion einer Aufgabe. Der Abbruchmechanismus ist effizienter als die Ausnahmebehandlung beim Abbrechen einer parallelen Arbeitsstruktur. Ein *parallele Arbeitsstruktur* ist eine Gruppe verwandter Aufgabengruppen, die in der einige Aufgabengruppen andere Aufgabengruppen enthalten. Der Abbruchmechanismus bricht eine Aufgabengruppe und ihre untergeordneten Aufgabengruppen von oben nach unten ab. Bei der Ausnahmebehandlung wird dagegen die umgekehrte Reihenfolge verwendet (Bottom-Up-Ansatz), sodass jede untergeordnete Aufgabengruppe einzeln abgebrochen werden muss.  
  

 Wenn Sie direkt mit einem Aufgabengruppenobjekt arbeiten, verwenden Sie die [task_group](reference/task-group-class.md#cancel) oder [Concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) Methoden, um die Arbeit abzubrechen, die zu dieser Aufgabengruppe gehört. . Zum Abbrechen eines parallelen Algorithmus, z. B. `parallel_for`, erstellen Sie eine übergeordnete Aufgabengruppe brechen diese Aufgabengruppe ab. Betrachten Sie beispielsweise die folgende Funktion `parallel_find_any`, die parallel nach einem Wert in einem Array sucht.  


  
 [!code-cpp[concrt-parallel-array-search#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_7.cpp)]  
  
 Da parallele Algorithmen Aufgabengruppen verwenden, wenn eine der parallelen Iterationen die übergeordnete Aufgabengruppe abbricht, wird die gesamte Aufgabe abgebrochen. Die vollständige Version dieses Beispiels, finden Sie unter [wie: Verwenden eines Abbruchs zum Verlassen einer Parallel-Schleife](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md).  
  
 Obwohl die Ausnahmebehandlung eine weniger effiziente Möglichkeit zum Abbrechen paralleler Aufgaben als der Abbruch ist, gibt es Fälle, in denen Ausnahmebehandlung sinnvoll ist. Zum Beispiel führt die folgende Methode, `for_all`, rekursiv eine Arbeitsfunktion auf jedem Knoten einer `tree`-Struktur aus. In diesem Beispiel wird die `_children` -Datenmember ist eine [List](../../standard-library/list-class.md) enthält `tree` Objekte.  
  
 [!code-cpp[concrt-task-tree-search#6](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_8.cpp)]  
  
 Der Aufrufer der `tree::for_all`-Methode kann eine Ausnahme auslösen, wenn es nicht erforderlich ist, dass die Arbeitsfunktion für jedes Element der Struktur aufgerufen wird. Das folgende Beispiel zeigt die `search_for_value`-Funktion, die nach einem Wert im bereitgestellten `tree`-Objekt sucht. Die `search_for_value`-Funktion verwendet eine Arbeitsfunktion, die eine Ausnahme auslöst, wenn das aktuelle Element der Struktur mit dem bereitgestellten Wert übereinstimmt. Die `search_for_value`-Funktion verwendet einen `try-catch`-Block, um die Ausnahme zu erfassen und das Ergebnis in der Konsole auszugeben.  
  
 [!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_9.cpp)]  
  
 Die vollständige Version dieses Beispiels, finden Sie unter [Vorgehensweise: Verwenden der Ausnahmebehandlung zum Verlassen einer Parallel-Schleife](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md).  
  
 Weitere allgemeine Informationen zu Abbruch- und Ausnahmebehandlungsmechanismen, die von der PPL bereitgestellt werden, finden Sie unter [Abbruch in der PPL](cancellation-in-the-ppl.md) und [Exception Handling](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="object-destruction"></a>Verstehen, wie Abbruch und Ausnahmebehandlung auf die Zerstörung auswirken  
 Eine abgebrochene Aufgabe in einer Struktur paralleler Arbeitsaufgaben kann dazu führen, dass untergeordnete Aufgaben nicht ausgeführt werden. Dies kann Probleme verursachen, wenn eine der untergeordneten Aufgaben einen Vorgang ausführen soll, der für die Anwendung von Bedeutung ist, beispielsweise das Freigeben einer Ressource. Darüber hinaus kann ein Aufgabenabbruch eine Ausnahme über einen Objektdestruktor weitergeben und ein nicht definiertes Verhalten in der Anwendung verursachen.  
  
 Im folgenden Beispiel beschreibt die `Resource`-Klasse eine Ressource und die `Container`-Klasse einen Container, der Ressourcen enthält. Im ihrem Destruktor ruft die `Container`-Klasse die `cleanup`-Methode für zwei ihrer `Resource`-Member parallel auf und ruft dann die `cleanup`-Methode für den dritten `Resource`-Member auf.  
  
 [!code-cpp[concrt-parallel-resource-destruction#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_10.h)]  
  
 Obwohl dieses Muster selbst keine Probleme hat, sollten Sie den folgenden Code verwenden, der zwei Aufgaben parallel ausführt. Die erste Aufgabe erstellt ein `Container`-Objekt, und die zweite Aufgabe bricht die gesamte Aufgabe ab. Zur Veranschaulichung wird im Beispiel verwendet zwei [Concurrency:: Event](../../parallel/concrt/reference/event-class.md) Objekte, um sicherzustellen, dass der Abbruch, nachdem auftritt die `Container` Objekt erstellt wird und dass die `Container` -Objekt zerstört wird, nach dem Abbruch Vorgang auftritt.  
  
 [!code-cpp[concrt-parallel-resource-destruction#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_11.cpp)]  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```Output  
Container 1: Freeing resources...Exiting program...  
```  
  
 Dieses Codebeispiel enthält die folgenden Probleme, die dazu führen, dass es sich möglicherweise anders als erwartet verhält:  
  
-   Der Abbruch der übergeordneten Aufgabe bewirkt, dass die untergeordnete Aufgabe, die den Aufruf von [Concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke), ebenfalls abgebrochen wird. Aus diesem Grund werden diese beiden Ressourcen nicht freigegeben.  

  
-   Der Abbruch der übergeordneten Aufgabe bewirkt, dass die untergeordnete Aufgabe eine interne Ausnahme auslöst. Da der `Container`-Destruktor diese Ausnahme nicht behandelt, wird die Ausnahme aufwärts weitergegeben, und die dritte Ressource wird nicht freigegeben.  
  
-   Die Ausnahme, die von der untergeordneten Aufgabe ausgelöst wird, wird über den `Container`-Destruktor weitergegeben. Durch das Auslösen von einem Destruktor wird die Anwendung in einen nicht definierten Zustand versetzt.  
  
 Es wird empfohlen, keine wichtigen Vorgänge, z. B. das Freigeben von Ressourcen, in den Aufgaben auszuführen, sofern Sie nicht garantieren können, dass diese Aufgaben nicht abgebrochen werden. Außerdem wird empfohlen, keine Laufzeitfunktionen zu verwenden, die im Destruktor der Typen ausgelöst werden können.  
  
 [[Nach oben](#top)]  
  
##  <a name="repeated-blocking"></a>In einer parallelen Schleife kein wiederholtes blockieren  

 Eine parallele Schleife wie [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) oder [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) , richtet sich anfällt, durch das Blockieren von Vorgängen können dazu führen, dass die Laufzeit innerhalb einer kurzen Zeitspanne viele Threads erstellt.  

  
 Die Concurrency Runtime führt zusätzliche Arbeiten aus, wenn eine Aufgabe beendet oder kooperativ blockiert oder zurückgehalten wird. Wenn eine parallelen Schleifeniteration blockiert, kann die Laufzeit eine andere Iteration starten. Wenn keine Leerlaufthreads verfügbar sind, erstellt die Laufzeit einen neuen Thread.  
  
 Wenn der Text einer parallelen Schleife gelegentlich blockt, hilft dieser Mechanismus beim Maximieren des Gesamtaufgabendurchsatzes. Wenn viele Iterationen blockieren, kann die Laufzeit viele Threads erstellen, um die zusätzlichen Arbeitsvorgänge auszuführen. Dies kann zu Arbeitsspeichermangel oder unzureichender Nutzung von Hardwareressourcen führen.  
  
 Betrachten Sie das folgende Beispiel ruft die [Concurrency:: Send](reference/concurrency-namespace-functions.md#send) Funktion in jeder Iteration eine `parallel_for` Schleife. Da `send` kooperativ blockiert, erstellt die Laufzeit einen neuen Thread, um zusätzliche Arbeit bei jedem Aufruf von `send` auszuführen.  
  
 [!code-cpp[concrt-repeated-blocking#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_12.cpp)]  
  
 Wir empfehlen, den Code neu zu gestalten, um dieses Muster zu vermeiden. In diesem Beispiel können Sie die Erstellung zusätzlicher Threads vermeiden, indem Sie `send` in einen seriellen `for`-Schleife aufrufen.  
  
 [[Nach oben](#top)]  
  
##  <a name="blocking"></a>Führen Sie keine Blockierungsvorgänge beim Abbrechen paralleler Aufgaben  

 Wenn möglich, nicht führen blockierenden Vorgänge vor dem Aufrufen der [task_group](reference/task-group-class.md#cancel) oder [Concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) Methode zum Abbrechen paralleler Aufgaben.  


  
 Wenn eine Aufgabe einen kooperativen Blockierungsvorgang ausführt, kann die Laufzeit andere Aufgaben ausführen, während die erste Aufgabe auf Daten wartet. Die Laufzeit plant die wartende Aufgabe neu, wenn die Blockierung aufgehoben wird. Die Laufzeit plant in der Regel Aufgaben neu, die vor kurzem entsperrt wurden, bevor sie Aufgaben, die vor längerer Zeit entsperrt wurden, neu plant. Aus diesem Grund könnte die Laufzeit unnötige Arbeit während des blockierenden Vorgangs planen, was zu Leistungseinbußen führt. Wenn Sie also einen Blockierungsvorgang ausführen, bevor Sie parallele Arbeitsvorgänge abbrechen, kann der blockierende Vorgang den Aufruf von `cancel` verzögern. Dies führt dazu, dass andere Aufgaben unnötige Arbeit ausführen.  
  
 Das folgende Beispiel definiert die `parallel_find_answer`-Funktion, die ein Element des bereitgestellten Arrays sucht, das der angegebenen Prädikatfunktion entspricht. Wenn die Prädikatfunktion `true` zurückgibt, erstellt die parallele Arbeitsfunktion ein `Answer`-Objekt und bricht die gesamte Aufgabe ab.  
  
 [!code-cpp[concrt-blocking-cancel#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_13.cpp)]  
  


 Der `new`-Operator führt eine Heapzuordnung aus, die blockieren könnte. Die Runtime führt andere arbeiten, nur wenn die Aufgabe einen kooperativen blockierenden Aufruf, wie z. B. einen Aufruf von [Concurrency::critical_section::lock](reference/critical-section-class.md#lock).  


  
 Das folgende Beispiel zeigt, wie Sie unnötige Arbeiten verhindern und damit die Leistung verbessern. In diesem Beispiel wird die Aufgabengruppe abgebrochen, bevor sie den Speicher für das `Answer`-Objekt zuweist.  
  
 [!code-cpp[concrt-blocking-cancel#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_14.cpp)]  
  
 [[Nach oben](#top)]  
  
##  <a name="shared-writes"></a>Nicht auf freigegebene Daten in einer parallelen Schleife schreiben  
 Die Concurrency Runtime bietet verschiedene Datenstrukturen, z. B. [Concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md), die gleichzeitigen Zugriff auf freigegebene Daten synchronisieren. Diese Datenstrukturen sind in vielen Fällen hilfreich, wenn z. B. mehrere Aufgaben nur selten gemeinsamen Zugriff auf eine Ressource erfordern.  
  
 Betrachten Sie das folgende Beispiel, das verwendet die [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) Algorithmus und eine `critical_section` Objekt berechnet die Anzahl von Primzahlen in einem [Std:: Array](../../standard-library/array-class-stl.md) Objekt. Dieses Beispiel skaliert nicht, da jeder Thread warten muss, um auf die freigegebene Variable `prime_sum` zuzugreifen.  

  
 [!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_15.cpp)]  
  
 Dieses Beispiel kann auch zu Leistungseinbußen führen, da der häufige Sperrvorgang die Schleife effektiv serialisiert. Wenn darüber hinaus ein Concurrency Runtime-Objekt einen Blockierungsvorgang ausführt, erstellt der Planer möglicherweise einen zusätzlichen Thread, um andere Aufgaben auszuführen, während der erste Thread auf Daten wartet. Wenn die Laufzeit viele Threads erstellt, da viele Aufgaben auf freigegebene Daten warten, kann die Anwendungsleistung abnehmen oder die Anwendung in einen Ressourcenmangelzustand versetzt werden.  
  
 Die PPL definiert die [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) -Klasse, die Sie gemeinsam verwendete Zustände und bietet Zugriff auf freigegebene Ressourcen in einer Weise sperrenfreie beseitigen kann. Die `combinable`-Klasse stellt lokalen Threadspeicher bereit, mit dem Sie differenzierte Berechnungen ausführen und dann diese Berechnungen in einem Endergebnis zusammenführen können. Stellen Sie sich ein `combinable`-Objekt wie eine Reduktionsvariable vor.  
  
 Im folgenden Beispiel wird das vorherige mithilfe eines `combinable`-Objekts anstelle eines `critical_section`-Objekts zum Berechnen der Summe geändert. Dieses Beispiel skaliert, da jeder Thread eine eigene lokale Kopie der Summe enthält. Dieses Beispiel verwendet die [Combine](reference/combinable-class.md#combine) Methode, um die lokalen Berechnungen zum Endergebnis zusammenzuführen.  

  
 [!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_16.cpp)]  
  
 Die vollständige Version dieses Beispiels, finden Sie unter [wie: Verbessern der Leistung mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md). Weitere Informationen zu den `combinable` Klasse, finden Sie unter [parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="false-sharing"></a>Vermeiden Sie False Sharing nach Möglichkeit  
 *False sharing* tritt auf, wenn mehrere gleichzeitige Aufgaben, die auf separaten Prozessoren ausgeführt werden, die auf Variablen, die befinden auf derselben Cachezeile schreiben. Wenn eine Aufgabe in eine der Variablen schreibt, wird die Cachezeile für beide Variablen ungültig. Jeder Prozessor muss die Cachezeile jedes Mal neu laden, wenn die Cachezeile ungültig ist. Daher kann False Sharing zu Leistungseinbußen in der Anwendung führen.  
  
 Das folgende grundlegende Beispiel zwei gleichzeitige Aufgaben, die jeweils eine gemeinsame Zählervariable erhöhen.  
  
 [!code-cpp[concrt-false-sharing#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_17.cpp)]  
  
 Um die gemeinsame Nutzung von Daten zwischen den beiden Aufgaben zu vermeiden, können Sie das Beispiel so ändern, dass zwei Zählervariablen verwendet werden. In diesem Beispiel wird der endgültige Zählerwert berechnet, nachdem die Aufgaben beendet wurden. Dieses Beispiel veranschaulicht jedoch False Sharing, da sich die Variablen `count1` und `count2` wahrscheinlich in derselben Cachezeile befinden.  
  
 [!code-cpp[concrt-false-sharing#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_18.cpp)]  
  
 Eine Möglichkeit zur Eliminierung von False Sharing besteht darin, sicherzustellen, dass sich die Zählervariablen in unterschiedlichen Cachezeilen befinden. Das folgende Beispiel richtet die Variablen `count1` und `count2` auf 64-Byte-Grenzen aus.  
  
 [!code-cpp[concrt-false-sharing#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_19.cpp)]  
  
 In diesem Beispiel wird davon ausgegangen, dass die Größe des Arbeitsspeichercaches höchstens 64 Byte beträgt.  
  
 Wir empfehlen die Verwendung der [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) Klasse, wenn Sie Daten für Aufgaben freigeben müssen. Die `combinable`-Klasse erstellt lokale Threadvariablen derart, dass False Sharing weniger wahrscheinlich ist. Weitere Informationen zu den `combinable` Klasse, finden Sie unter [parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="lifetime"></a>Stellen Sie sicher, dass Variablen während der gesamten Lebensdauer einer Aufgabe gültig sind.  
 Wenn Sie einer Aufgabengruppe oder einem parallelen Algorithmus einen Lambdaausdruck bereitstellen, gibt die Erfassungsklausel an, ob der Text des Lambdaausdrucks auf Variablen im einschließenden Bereich als Wert oder als Verweis zugreift. Wenn Sie Variablen als Verweis an einen Lambdaausdruck übergeben, müssen Sie sicherstellen, dass die Lebensdauer dieser Variablen bis zum Beenden der Aufgabe erhalten bleibt.  
  
 Betrachten Sie das folgende Beispiel, in dem die `object`-Klasse und die `perform_action`-Funktion definiert werden. Die `perform_action`-Funktion erstellt eine `object`-Variable und führt eine Aktion für diese Variable asynchron durch. Da die Aufgabe nicht unbedingt vor der Rückgabe der `perform_action`-Funktion beendet wird, stürzt das Programm ab oder zeigt nicht definiertes Verhalten, wenn die `object`-Variable beim Ausführen der Aufgabe gelöscht wird.  
  
 [!code-cpp[concrt-lambda-lifetime#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_20.cpp)]  
  
 Je nach den Anforderungen Ihrer Anwendung können Sie eine der folgenden Methoden verwenden, um zu garantieren, dass Variablen während der Lebensdauer der einzelnen Aufgaben gültig bleiben.  
  
 Das folgende Beispiel übergibt die `object`-Variable als Wert an die Aufgabe. Aus diesem Grund funktioniert die Aufgabe mit der eigenen Kopie der Variablen.  
  
 [!code-cpp[concrt-lambda-lifetime#2](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_21.cpp)]  
  
 Da die `object`-Variable als Wert übergeben wird, werden alle Zustandsänderungen, die für diese Variablen auftreten, nicht in der ursprünglichen Kopie angezeigt.  
  
 Im folgenden Beispiel wird die [Concurrency:: task_group::](reference/task-group-class.md#wait) Methode, um sicherzustellen, dass die Aufgabe abgeschlossen, bevor ist die `perform_action` -Funktion zurückgegeben wird.  


  
 [!code-cpp[concrt-lambda-lifetime#3](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_22.cpp)]  
  
 Da die Aufgabe jetzt abgeschlossen ist, bevor die Funktion beendet wird, verhält sich die `perform_action`-Funktion nicht mehr asynchron.  
  
 Das folgende Beispiel ändert die `perform_action`-Funktion für die Übergabe eines Verweises an die `object`-Variable. Der Aufrufer muss sicherstellen, dass die Lebensdauer der `object`-Variable gültig ist, bis die Aufgabe abgeschlossen ist.  
  
 [!code-cpp[concrt-lambda-lifetime#4](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-parallel-patterns-library_23.cpp)]  
  
 Sie können auch einen Zeiger zur Steuerung der Lebensdauer eines Objekts verwenden, das Sie an eine Aufgabengruppe oder einen parallelen Algorithmus übergeben.  
  
 Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions (Lambdaausdrücke)](../../cpp/lambda-expressions-in-cpp.md).  
  
 [[Nach oben](#top)]  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency Runtime bewährte Methoden](../../parallel/concrt/concurrency-runtime-best-practices.md)   
 [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)   
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [Abbruch in der PPL](cancellation-in-the-ppl.md)   
 [Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Exemplarische Vorgehensweise: Erstellen einer Bildverarbeitungsnetzwerks](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)   
 [Vorgehensweise: Verwenden von Parallel_invoke auf parallele Sortierung Schreiben einer](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)   
 [Vorgehensweise: Verwenden eines Abbruchs zum Verlassen einer Parallel-Schleife](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)   
 [Vorgehensweise: Verbessern der Leistung mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)   
 [Empfohlene Vorgehensweisen in der Asynchronous Agents Library](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)   
 [Allgemein bewährte Methoden in der Concurrency Runtime](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)

