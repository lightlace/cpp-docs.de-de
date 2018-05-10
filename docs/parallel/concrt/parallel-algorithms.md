---
title: Parallele Algorithmen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parallel algorithms [Concurrency Runtime]
ms.assetid: 045dca7b-4d73-4558-a44c-383b88a28473
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 365acd15c61b52631fc75018ab4c3a017d3eed8f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="parallel-algorithms"></a>Parallele Algorithmen
Die Parallel Patterns Library (PPL) stellt die Algorithmen, die gleichzeitig Arbeit mit Auflistungen von Daten verwenden. Diese Algorithmen entsprechen den in der C++-Standardbibliothek.  
  

 Parallelen Algorithmen bestehen aus vorhandenen Funktionen in der Concurrency Runtime. Z. B. die [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) -Algorithmus verwendet eine [Concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) Objekt, das die parallelen Schleifeniterationen ausführen. Die `parallel_for` Algorithmus Partitionen auf Grundlage der verfügbaren Computerressourcen optimale Weise funktionieren.  

  
##  <a name="top"></a> Abschnitte  
  
- [Der Parallel_for-Algorithmus](#parallel_for)  
  
- [Der Parallel_for_each-Algorithmus](#parallel_for_each)  
  
- [Der Parallel_invoke-Algorithmus](#parallel_invoke)  
  
- [Die Parallel_transform- und Parallel_reduce-Algorithmen](#parallel_transform_reduce)  
  
    - [Der Parallel_transform-Algorithmus](#parallel_transform)  
  
    - [Der Parallel_reduce-Algorithmus](#parallel_reduce)  
  
    - [Beispiel: Der Zuordnung und Reduzierung parallel ausführen](#map_reduce_example)  
  
- [Partitionieren der Arbeit](#partitions)  
  
- [Parallele Sortierung](#parallel_sorting)  
  
    - [Auswählen eines Sortieralgorithmus](#choose_sort)  
  
##  <a name="parallel_for"></a> Der Parallel_for-Algorithmus  

 Die [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) führt der Algorithmus wiederholt die gleiche Aufgabe parallel aus. Jede dieser Aufgaben wird durch eine Iterationswert parametrisiert. Dieser Algorithmus ist nützlich, wenn ein Schleifenkörper vorliegen, die Ressourcen von Iterationen der Schleife nicht gemeinsam verwendet wird.  
  
 Die `parallel_for` Algorithmus partitioniert Aufgaben eine optimale, für die parallele Ausführung. Er verwendet einen Arbeitsübernahme-Algorithmus und Bereich, um diese Partitionen zu verteilen, wenn arbeitsauslastungen nicht ausgeglichen sind zu stehlen. Wenn eine Schleifeniteration kooperativ blockiert, verteilt die Laufzeit des Bereichs von Iterationen, die für den aktuellen Thread auf andere Threads oder Prozessoren zugewiesen wird. Wenn ein Thread einen Bereich von Iterationen abgeschlossen ist, wird die Common Language Runtime auf ähnliche Weise Arbeit von anderen Threads in diesem Thread. Die `parallel_for` Algorithmus unterstützt auch *geschachtelt Parallelität*. Wenn eine parallele Schleife eine andere parallele Schleife enthält, koordiniert die Common Language Runtime Verarbeitungsressourcen zwischen der Schleifenkörper auf effiziente Weise für die parallele Ausführung.  
  
 Die `parallel_for` Algorithmus verfügt über mehrere überladene Versionen. Die erste Version akzeptiert einen Startwert und einen Endwert eine Arbeitsfunktion (Lambda-Ausdruck, Funktionsobjekt oder Funktionszeiger). Die zweite Version akzeptiert einen Startwert, einen Endwert, einen Wert mit dem Schritt, und eine Arbeitsfunktion. Die erste Version dieser Funktion verwendet 1 als Step-Wert. Die verbleibenden Versionen dauern Partitionierer-Objekte, die Ihnen die Angabe ermöglichen wie `parallel_for` Bereiche zwischen Threads sollte partitionieren. Partitionierer werden ausführlich im Abschnitt [Partitionierung Arbeit](#partitions) in diesem Dokument.  
  
 Sie können viele konvertieren `for` Schleifen mit `parallel_for`. Allerdings die `parallel_for` Algorithmus unterscheidet sich von der `for` Anweisung auf folgende Weise:  
  
-   Die `parallel_for` Algorithmus `parallel_for` die Aufgaben in einer vordefinierten Reihenfolge wird nicht ausgeführt.  
  
-   Die `parallel_for` Algorithmus beliebige Beendigung Bedingungen nicht unterstützt. Die `parallel_for` Algorithmus wird beendet, wenn der aktuelle Wert der Iterationsvariablen eines ist kleiner als `last`.  
  
-   Die `_Index_type` Typparameter muss ein ganzzahliger Typ sein. Dieser ganzzahlige Typ kann mit oder ohne Vorzeichen.  
  
-   Die Iteration der Schleife muss vorwärts gerichtet sein. Die `parallel_for` Algorithmus löst eine Ausnahme vom Typ [Std:: invalid_argument](../../standard-library/invalid-argument-class.md) Wenn die `_Step` Parameter ist kleiner als 1.  
  
-   Der Mechanismus für die Ausnahmebehandlung für die `parallel_for` Algorithmus unterscheidet sich von einer `for` Schleife. Wenn mehrere Ausnahmen gleichzeitig in einer parallelen Schleife auftreten, die Common Language Runtime gibt nur eine der Ausnahmen an den Thread, der aufgerufen `parallel_for`. Darüber hinaus, wenn eine Schleifeniteration eine Ausnahme auslöst, wird die Common Language Runtime nicht sofort die gesamte Schleife beendet. Stattdessen wird die Schleife befindet sich im Status "abgebrochen", und verwirft die Runtime alle Aufgaben, die noch nicht gestartet wurden. Weitere Informationen zur Behandlung von Ausnahmen und parallele Algorithmen finden Sie unter [Exception Handling](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 Obwohl die `parallel_for` Algorithmus beliebige Beendigung Bedingungen nicht unterstützt, können Sie Abbruch um aller Aufgaben zu beenden. Weitere Informationen über Abbrüche finden Sie unter [Abbruch in der PPL](cancellation-in-the-ppl.md).  
  
> [!NOTE]
>  Die Planung Kosten, dass die Ergebnisse von Lastenausgleich und Unterstützung für Funktionen, z. B. Abbruch nicht die Vorteile der Ausführung der Schleife parallel umgehen können, sind insbesondere beim Schleifenkörper sehr gering. Sie können diesen zusätzlichen Aufwand minimieren, mithilfe eines Partitionierers in der parallelen Schleife. Weitere Informationen finden Sie unter [Partitionierung Arbeit](#partitions) weiter unten in diesem Dokument.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die grundlegende Struktur der `parallel_for` Algorithmus. In diesem Beispiel gibt jeden Wert im Bereich [1, 5] parallel an der Konsole aus.  
  
 [!code-cpp[concrt-parallel-for-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_1.cpp)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe:  
  
```Output  
1 2 4 3 5  
```  
  
 Da die `parallel_for` Algorithmus für jedes Element in parallelen fungiert, variiert die Reihenfolge, in dem die Werte werden in der Konsole ausgegeben.  
  
 Für ein vollständiges Beispiel, verwendet der `parallel_for` -Algorithmus finden Sie unter [wie: Schreiben einer Parallel_for-Schleife](../../parallel/concrt/how-to-write-a-parallel-for-loop.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="parallel_for_each"></a> Der Parallel_for_each-Algorithmus  

 Die [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) Algorithmus führt Aufgaben für einen iterativen Container, z. B. die von der C++-Standardbibliothek parallel bereitgestellt. Er verwendet die gleiche Partitionierungslogik wie der `parallel_for`-Algorithmus.  
  
 Die `parallel_for_each` -Algorithmus ähnelt der C++-Standardbibliothek [Std:: for_each](../../standard-library/algorithm-functions.md#for_each) -Algorithmus, außer dass die `parallel_for_each` -Algorithmus die Aufgaben gleichzeitig ausführt. Wie andere parallele Algorithmen `parallel_for_each` die Aufgaben in einer bestimmten Reihenfolge wird nicht ausgeführt.  
  
 Obwohl die `parallel_for_each` Algorithmus funktioniert auf die forward-Iteratoren und random-Access-Iteratoren, bietet eine bessere Leistung mit wahlfreiem Zugriffsiteratoren.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die grundlegende Struktur der `parallel_for_each` Algorithmus. In diesem Beispiel druckt in die Konsole jedes Werts in einer [Std:: Array](../../standard-library/array-class-stl.md) -Objekt parallel.  
  
 [!code-cpp[concrt-parallel-for-each-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_2.cpp)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe:  
  
```Output  
4 5 1 2 3  
```  
  
 Da die `parallel_for_each` Algorithmus für jedes Element in parallelen fungiert, variiert die Reihenfolge, in dem die Werte werden in der Konsole ausgegeben.  
  
 Für ein vollständiges Beispiel, verwendet der `parallel_for_each` -Algorithmus finden Sie unter [wie: Schreiben einer Parallel_for_each-Schleife](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="parallel_invoke"></a> Der Parallel_invoke-Algorithmus  

 Die [Concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) Algorithmus führt eine Reihe von Aufgaben gleichzeitig aus. Es gibt keinen zurück, bis jede Aufgabe abgeschlossen ist. Dieser Algorithmus ist hilfreich, wenn Sie mehrere unabhängige Aufgaben verfügen, die zur gleichen Zeit ausgeführt werden soll.  
  
 Die `parallel_invoke` Algorithmus erfordert als Parameter eine Reihe von Arbeitsfunktionen (Lambda-Funktionen, Funktionsobjekte und Funktionszeiger). Die `parallel_invoke` Algorithmus ist überladen, sodass Sie zwischen zwei und zehn Parameter übernehmen. Jede Funktion, die Sie zum übergeben `parallel_invoke` muss 0 (null) Parameter annehmen.  
  
 Wie andere parallele Algorithmen `parallel_invoke` die Aufgaben in einer bestimmten Reihenfolge wird nicht ausgeführt. Das Thema [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md) wird erläutert, wie die `parallel_invoke` Algorithmus bezieht sich auf Aufgaben und Aufgabengruppen.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die grundlegende Struktur der `parallel_invoke` Algorithmus. Dieses Beispiel gleichzeitig Ruft die `twice` Funktion auf drei lokale Variablen und das Ergebnis an die Konsole ausgegeben.  
  
 [!code-cpp[concrt-parallel-invoke-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_3.cpp)]  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```Output  
108 11.2 HelloHello  
```  
  
 Ausführliche Beispiele für die Verwendung der `parallel_invoke` -Algorithmus finden Sie unter [Vorgehensweise: mithilfe von Parallel_invoke zum parallelen sortieren Schreiben einer](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md) und [wie: Parallel_invoke zum Ausführen von parallelen Vorgängen](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="parallel_transform_reduce"></a> Die Parallel_transform- und Parallel_reduce-Algorithmen  

 Die [Concurrency:: parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform) und [Concurrency:: parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce) Algorithmen sind die parallelen Versionen der C++-Standardbibliothek Algorithmen [reduzierungsvorgänge](../../standard-library/algorithm-functions.md#transform)und [Std:: Accumulate](../../standard-library/numeric-functions.md#accumulate)zugeordnet. Die Concurrency Runtime-Versionen verhalten sich wie die C++-Standardbibliothek Versionen mit dem Unterschied, dass die Reihenfolge der Vorgang nicht bestimmt wird, daran, dass sie parallel ausgeführt. Verwenden Sie diese Algorithmen, wenn Sie mit einem Satz, die groß genug ist arbeiten, um Leistungs- und Skalierbarkeitsvorteile bieten abzurufen, von der parallelen Verarbeitung ist.  
  
> [!IMPORTANT]
>  Die `parallel_transform` und `parallel_reduce` Algorithmen unterstützen nur random-Access, bidirektionale und forward-Iteratoren, da diese Iteratoren stabil Speicheradressen erzeugen. Darüber hinaus diese Iteratoren erzeugen müssen nicht-`const` l-Werte.  
  
###  <a name="parallel_transform"></a> Der Parallel_transform-Algorithmus  
 Sie können die `parallel transform` Algorithmus, viele Data Parallelisierung Vorgänge auszuführen. Sie haben unter anderem folgende Möglichkeiten:  
  
-   Die Helligkeit eines Bilds und andere Vorgänge Image Verarbeitung.  
  
-   Die Summe oder nehmen Sie das Skalarprodukt zwischen beiden Vektoren aus, und andere numerische Berechnungen für Vektoren.  
  
-   Führen Sie 3D Strahl-Ablaufverfolgung zu, wobei jeder Iteration ein Pixel bezeichnet, die gerendert werden muss.  
  
 Im folgende Beispiel wird die grundlegende Struktur ab, das Aufrufen der `parallel_transform` Algorithmus. In diesem Beispiel negiert jedes Element eine std::[Vektor](../../standard-library/vector-class.md) Objekt auf zwei Arten. Die erste Methode verwendet einen Lambda-Ausdruck. Die zweite Methode verwendet [std::negate](../../standard-library/negate-struct.md), die sich daraus ableitet [std::unary_function](../../standard-library/unary-function-struct.md).  
  
 [!code-cpp[concrt-basic-parallel-transform#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_4.cpp)]  
  
> [!WARNING]
>  Dieses Beispiel veranschaulicht die grundlegende Verwendung von `parallel_transform`. Da die Arbeitsfunktion keine beträchtliche Menge an Arbeit ausführt, wird die Leistung beträchtlich zunehmen in diesem Beispiel nicht erwartet.  
  
 Die `parallel_transform` Algorithmus verfügt über zwei Überladungen. Die erste Überladung akzeptiert eine Eingabebereich und eine unäre Funktion. Unäre Funktion kann es sich um einen Lambda-Ausdruck, der akzeptiert ein Argument, ein Funktionsobjekt oder ein Typ, der von abgeleitet ist `unary_function`. Die zweite Überladung nimmt zwei Eingabebereiche und einer binären Funktion an. Binäre Funktion kann es sich um einen Lambda-Ausdruck, der akzeptiert zwei Argumente, ein Funktionsobjekt oder ein Typ, der von abgeleitet ist [std::binary_function](../../standard-library/binary-function-struct.md). Das folgende Beispiel zeigt diese Unterschiede.  
  
 [!code-cpp[concrt-parallel-transform-vectors#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_5.cpp)]  
  
> [!IMPORTANT]
>  Der Iterator, der für die Ausgabe der angegebenen `parallel_transform` müssen vollständig überlappen der input-Iterator, oder sich nicht überschneiden. Das Verhalten dieses Algorithmus ist nicht angegeben, wenn die Eingabe- und Iteratoren teilweise überschneiden.  
  
###  <a name="parallel_reduce"></a> Der Parallel_reduce-Algorithmus  
 Die `parallel_reduce` Algorithmus ist nützlich, bei einer Sequenz von Vorgängen, die die assoziative-Eigenschaft entsprechen. (Dieser Algorithmus ist nicht kommutativ Eigenschaft erforderlich.) Im folgenden sind einige der Vorgänge, die Sie auch `parallel_reduce`:  
  
-   Multiplizieren Sie Sequenzen von Matrizen bis hin zu eine Matrix zu erzeugen.  
  
-   Multipliziert einen Vektor einer Folge von Matrizen bis hin zu einen Vektor zu erzeugen.  
  
-   Die Länge einer Sequenz von Zeichenfolgen zu berechnen.  
  
-   Kombinieren Sie eine Liste der Elemente, z. B. Zeichenfolgen, in ein Element.  
  
 Im folgende grundlegende Beispiel wird gezeigt, wie die `parallel_reduce` Algorithmus, um eine Sequenz von Zeichenfolgen zu einer Zeichenfolge zu kombinieren. Wie bei den Beispielen für `parallel_transform`, Leistungssteigerungen sind in diesem grundlegenden Beispiel für nicht erwartet.  
  
 [!code-cpp[concrt-basic-parallel-reduce#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_6.cpp)]  
  
 In vielen Fällen können Sie der Meinung von `parallel_reduce` als Kurzform für die Verwendung der `parallel_for_each` Algorithmus zusammen mit den [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) Klasse.  
  
###  <a name="map_reduce_example"></a> Beispiel: Der Zuordnung und Reduzierung parallel ausführen  

 Ein *Zuordnung* wendet eine Funktion auf jeden Wert in einer Sequenz. Ein *reduzieren* kombiniert die Elemente einer Sequenz zu einem einzelnen Wert. Sie können die C++-Standardbibliothek [reduzierungsvorgänge](../../standard-library/algorithm-functions.md#transform) und [Std:: Accumulate](../../standard-library/numeric-functions.md#accumulate) Funktionen zum Ausführen von Zuordnungs- und Operationen verringern. Für viele Probleme, Sie können jedoch die `parallel_transform` -Algorithmus parallel den Zuordnungsvorgang ausgeführt und die `parallel_reduce` Algorithmus den Reduzierungsvorgang parallel ausführen.  

  
 Im folgenden Beispiel wird die Zeit, die die Summe von Primzahlen seriell sowie parallel berechnet. Die Phase Zuordnung transformiert nicht-Primzahlen Werte zwischen 0 und der Reduce Phase Summen, die Werte zu.  
  
 [!code-cpp[concrt-parallel-map-reduce-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_7.cpp)]  
  
 Ein anderes Beispiel führt eine Zuordnung und Reduzierung Vorgang parallel, finden Sie unter [wie: Zuordnung ausführen und Vorgänge zu reduzieren, parallel](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="partitions"></a> Partitionieren der Arbeit  
 Um einen Vorgang für eine Datenquelle zu parallelisieren, ist ein wichtiger Schritt zum *Partition* der Quelle in mehrere Abschnitte, die gleichzeitig durch mehrere Threads zugegriffen werden kann. Ein Partitionierer gibt an, wie ein paralleler Algorithmus Bereiche zwischen Threads partitionieren sollten. Wie zuvor in diesem Dokument erläutert wird, verwendet die PPL eine Partitionierung Mechanismus, der eine anfängliche Arbeitslast erstellt und verwendet dann einen Arbeitsübernahme-Algorithmus und Bereich, um diese Partitionen zu verteilen, wenn arbeitsauslastungen nicht ausgeglichen sind zu stehlen. Wenn eine Schleifeniteration einen Bereich von Iterationen abgeschlossen ist, wird die Common Language Runtime z. B. Arbeit von anderen Threads in diesem Thread. Möglicherweise möchten Sie jedoch für einige Szenarien ein anderen Mechanismus für die Partitionierungs angeben, das eine bessere Leistung für Ihr Problem geeignet ist.  
  
 Die `parallel_for`, `parallel_for_each`, und `parallel_transform` Algorithmen bieten überladene Versionen, die einen zusätzlichen Parameter annehmen `_Partitioner`. Dieser Parameter definiert, den Partitionierer-Typ, der Arbeit dividiert wird. Hier sind die Arten von Partitionierer, die die PPL definiert:  
  
 [Concurrency::affinity_partitioner](../../parallel/concrt/reference/affinity-partitioner-class.md)  
 Dividiert funktionieren in einer festen Anzahl von Bereichen (normalerweise die Anzahl der Arbeitsthreads, die für die Arbeit in der Schleife verfügbar sind). Dieser Typ Partitionierer ähnelt `static_partitioner`, jedoch wird die verbessert der Möglichkeit, Bereiche Arbeitsthreads zugeordnet. Dieser Typ Partitionierer kann die Leistung verbessern, wenn eine Schleife über das gleiche Dataset mehrere Male (z. B. eine Schleife in einer Schleife) ausgeführt wird und die Daten in den Cache passen. Diese Partitionierer nicht vollständig an Abbruch teilnehmen. Es auch nicht kooperativen blockierenden Semantik verwendet und kann daher nicht verwendet werden, mit parallelen Schleifen, die eine forward-Abhängigkeit aufweisen.  
  
 [Concurrency::auto_partitioner](../../parallel/concrt/reference/auto-partitioner-class.md)  
 Dividiert funktionieren in eine anfängliche Anzahl von Bereichen (normalerweise die Anzahl der Arbeitsthreads, die für die Arbeit in der Schleife verfügbar sind). Die Laufzeit dieses Typs wird standardmäßig verwendet, wenn Sie einen überladenen parallelen Algorithmus nicht aufrufen, die akzeptiert eine `_Partitioner` Parameter. Jeder Bereich kann in Teilbereiche aufgeteilt werden, und dadurch ermöglicht Lastenausgleich erfolgen. Wenn Sie ein Bereich von Arbeit abgeschlossen ist, werden die Common Language Runtime Teilbereiche von Arbeit von anderen Threads in diesem Thread neu verteilt. Verwenden Sie diese Partitionierer, wenn Ihre arbeitsauslastung nicht unter einem der anderen Kategorien liegt, oder Sie benötigen eine vollständige Unterstützung für die Abbruch- noch die Kooperative Blockierung.  
  
 [Concurrency::simple_partitioner](../../parallel/concrt/reference/simple-partitioner-class.md)  
 Dividiert funktionieren in Bereiche, damit jeder Bereich mindestens die Anzahl von Iterationen enthält, die von der Segmentgröße angegebene angegeben werden. Dieser Typ Partitionierer ist Teil des Lastenausgleichs; Allerdings ist die Common Language Runtime nicht Bereiche in untergeordnete Bereiche unterteilen. Für jeden Arbeitsthread die Common Language Runtime nach einem Abbruchvorgang gesucht und führt den Lastenausgleich nach `_Chunk_size` Iterationen abgeschlossen.  
  
 [Concurrency::static_partitioner](../../parallel/concrt/reference/static-partitioner-class.md)  
 Dividiert funktionieren in einer festen Anzahl von Bereichen (normalerweise die Anzahl der Arbeitsthreads, die für die Arbeit in der Schleife verfügbar sind). Dieser Typ Partitionierer kann die Leistung verbessern, da es keine Arbeitsübernahme verwendet- und daher weniger Aufwand hat. Verwenden Sie diesen Partitionierer-Typ, wenn jeder Iteration einer parallelen Schleife eine feste und gleichartige Menge an Arbeit führt und abbruchunterstützung erforderlich ist oder nicht Kooperative Blockierung weiterleiten.  
  
> [!WARNING]
>  Die `parallel_for_each` und `parallel_transform` Algorithmen unterstützen nur Container, die random-Access-Iteratoren verwenden (z. B. std::[Vektor](../../standard-library/vector-class.md)) für die Partitionierer static-, einfache und Affinität. Die Verwendung von Containern, die bidirektionale und forward-Iteratoren verwenden erzeugt einen Fehler während der Kompilierung. Dem Standardpartitionierer `auto_partitioner`, alle drei dieser Iterator-Typen unterstützt.  
  
 Normalerweise diese Partitionierer werden verwendet, auf die gleiche Weise, mit Ausnahme von `affinity_partitioner`. Die meisten Typen von Partitionierer Zustand nicht beibehalten und werden von der Laufzeit nicht geändert. Aus diesem Grund können Sie diese Objekte Partitionierer an der Aufrufsite erstellen, wie im folgenden Beispiel gezeigt.  
  
 [!code-cpp[concrt-static-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_8.cpp)]  
  
 Allerdings müssen Sie übergeben ein `affinity_partitioner` Objekt als nicht`const`, l-Wert verweisen, sodass der Algorithmus Status für zukünftige Schleifen Wiederverwendung gespeichert werden kann. Das folgende Beispiel zeigt eine einfache Anwendung, die denselben Vorgang in ein Dataset parallel mehrmals ausgeführt. Die Verwendung von `affinity_partitioner` kann die Leistung verbessern, da das Array wahrscheinlich in den Cache passen.  
  
 [!code-cpp[concrt-affinity-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_9.cpp)]  
  
> [!CAUTION]
>  Gehen Sie vorsichtig vor, wenn Sie vorhandenen Code, die Kooperative Blockierung Semantik ändern verwenden benötigt `static_partitioner` oder `affinity_partitioner`. Diese Typen Partitionierer verwenden Sie nicht den Lastenausgleich oder Bereich zu stehlen und aus diesem Grund können das Verhalten der Anwendung geändert werden.  
  
 Die beste Möglichkeit, die bestimmt, ob einen Partitionierer in bestimmten Szenarien verwendet, werden von experimentieren und messen, wie lange dauert es unter repräsentative Lade- und Computerkonfigurationen Abschluss von Vorgängen ab. Die statische Partitionierung könnte z.B. möglicherweise auf einem Mehrkerncomputer mit nur wenigen Kernen für erhebliche Beschleunigung sorgen, doch bei Computern mit relativ vielen Kernen zu Verlangsamungen führen.  
  
 [[Nach oben](#top)]  
  
##  <a name="parallel_sorting"></a> Parallele Sortierung  

 Die PPL bietet drei Sortieralgorithmen: [Concurrency:: parallel_sort](reference/concurrency-namespace-functions.md#parallel_sort), [Concurrency:: parallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort), und [Concurrency:: parallel_radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort). Diese Sortieralgorithmen sind nützlich, wenn Sie ein Dataset verfügen, die zu sortierenden parallel profitieren können. Parallele Sortierung ist insbesondere nützlich, bei ein großen Dataset haben oder wenn Sie einem rechenintensiv ist Vergleichsvorgang verwenden, um Ihre Daten zu sortieren. Jede der folgenden Algorithmen sortiert Elemente vorhanden.  

  
 Die `parallel_sort` und `parallel_buffered_sort` Algorithmen sind beide Algorithmen vergleichsbasierte. D. h. Vergleichen sie Elemente nach Wert. Die `parallel_sort` Algorithmus verfügt über keine zusätzlichen arbeitsspeicheranforderungen und eignet sich für allgemeine sortieren. Die `parallel_buffered_sort` ausführen Algorithmus kann besser `parallel_sort`, jedoch O(N) Speicherplatz erforderlich.  
  
 Die `parallel_radixsort` -Algorithmus ist hashbasierten. D. h. verwendet ganzzahligen Schlüssel, um Elemente zu sortieren. Mithilfe eines Schlüssels, kann dieser Algorithmus direkt das Ziel eines Elements statt Vergleiche berechnen. Wie `parallel_buffered_sort`, dieser Algorithmus ist O(N) Speicherplatz erforderlich.  
  
 In der folgenden Tabelle werden die wichtigen Eigenschaften der drei parallele Sortieralgorithmen zusammengefasst.  
  
|Algorithmus|Beschreibung|Sortieren von Mechanismus|Sortieren einer stabilen|Speicheranforderungen|Zeitkomplexität|Iteratorzugriff|  
|---------------|-----------------|-----------------------|--------------------|-------------------------|---------------------|---------------------|  
|`parallel_sort`|Allgemeine vergleichsbasierte sortieren.|Vergleichsbasierte (aufsteigend)|Instabil|Keiner|O((N/P)Log(N/P) + 2N((P-1)/P))|Random|  
|`parallel_buffered_sort`|Schneller allgemeine vergleichsbasierte sortieren, die O(N) Speicherplatz benötigt.|Vergleichsbasierte (aufsteigend)|Instabil|Erfordert zusätzlichen O(N) Speicherplatz|O((N/P)Log(N))|Random|  
|`parallel_radixsort`|Ganze Zahl Schlüsselbasierte sortieren, die O(N) Speicherplatz benötigt.|Hashbasierten|Stable|Erfordert zusätzlichen O(N) Speicherplatz|O(N/P)|Random|  
  
 Die folgende Abbildung zeigt die wichtigen Eigenschaften der drei parallele Sortieralgorithmen mehr grafisch an.  
  
 ![Vergleich der Sortieralgorithmen](../../parallel/concrt/media/concrt_parallel_sorting.png "Concrt_parallel_sorting")  
  
 Diese parallele Sortieralgorithmen folgen die Regeln der Abbruch und Ausnahmebehandlung. Weitere Informationen zum Abbruch und Ausnahmebehandlung in der Concurrency Runtime finden Sie unter [Abbrechen von parallelen Algorithmen](../../parallel/concrt/cancellation-in-the-ppl.md#algorithms) und [Exception Handling](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
> [!TIP]
>  Diese parallele Sortieralgorithmen unterstützen Move-Semantik. Sie können einen bewegungszuweisungsoperator zum Aktivieren von Swap Vorgänge effizienter auftreten definieren. Weitere Informationen zu Move-Semantik und der bewegungszuweisungsoperator, finden Sie unter [Rvalue-Verweisdeklarator: & &](../../cpp/rvalue-reference-declarator-amp-amp.md), und [Bewegungskonstruktoren und Bewegungszuweisungsoperatoren (C++)](../../cpp/move-constructors-and-move-assignment-operators-cpp.md). Wenn Sie einen bewegungszuweisungsoperator oder Swap-Funktion nicht bereitstellen, verwenden die Sortieralgorithmen den Kopierkonstruktor.  
  
 Im folgende grundlegende Beispiel wird gezeigt, wie `parallel_sort` zum Sortieren einer `vector` von `int` Werte. Standardmäßig `parallel_sort` verwendet [Std:: less](../../standard-library/less-struct.md) zum Vergleichen von Werten.  
  
 [!code-cpp[concrt-basic-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_10.cpp)]  
  
 In diesem Beispiel wird gezeigt, wie Sie eine benutzerdefinierte Vergleichsfunktion bereitstellen. Er verwendet die [Std::complex::real](../../standard-library/complex-class.md#real) Methode zum Sortieren [Std:: Complex\<doppelte >](../../standard-library/complex-double.md) Werte in aufsteigender Reihenfolge.  
  
 [!code-cpp[concrt-basic-parallel-sort#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_11.cpp)]  
  
 In diesem Beispiel wird gezeigt, wie eine Hash-Funktion zum Bereitstellen der `parallel_radixsort` Algorithmus. In diesem Beispiel wird 3D Punkte sortiert. Die Punkte werden basierend auf deren Abstand von Bezugspunkt sortiert.  
  
 [!code-cpp[concrt-parallel-sort-points#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_12.cpp)]  
  
 Dieses Beispiel verwendet zur Veranschaulichung wird ein relativ kleines Dataset. Sie können die anfängliche Größe des Vektors leistungsverbesserungen über größere Datenmengen experimentieren erhöhen.  
  
 Dieses Beispiel verwendet einen Lambda-Ausdruck als der Hashfunktion. Sie können auch eine der integrierten Implementierungen von dem std::[hash-Klasse](../../standard-library/hash-class.md) oder eigene Spezialisierung definieren. Sie können auch eine benutzerdefinierte hashfunktionsobjekt verwenden, wie im folgenden Beispiel gezeigt:  
  
 [!code-cpp[concrt-parallel-sort-points#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_13.cpp)]  
  
 [!code-cpp[concrt-parallel-sort-points#3](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_14.cpp)]  
  
 Die Hash-Funktion muss einen ganzzahligen Typ zurückgeben ([Std::is_integral::value](../../standard-library/is-integral-class.md) muss `true`). Diese ganzzahlige Typ muss in den Typ `size_t`.  
  
###  <a name="choose_sort"></a> Auswählen eines Sortieralgorithmus  
 In vielen Fällen `parallel_sort` die optimale Ausgewogenheit zwischen Geschwindigkeit und Leistung bietet. Allerdings als Sie erhöhen die Größe des Datasets, die Anzahl der verfügbaren Prozessoren oder die Komplexität der Compare-Funktion `parallel_buffered_sort` oder `parallel_radixsort` bieten eine bessere Leistung. Die beste Möglichkeit, um zu bestimmen, welche Sortieralgorithmus zur Verwendung in einem gegebenen Szenario besteht darin experimentieren und messen, wie lange es dauert, typische Daten unter repräsentativen Computerkonfigurationen sortiert. Bedenken Sie die folgenden Richtlinien bei der Auswahl einer Strategie für die Sortierung.  
  
-   Die Größe des Datasets. In diesem Dokument ein *kleine* Dataset weniger als 1.000 Elemente enthält, eine *Mittel* Dataset zwischen 10.000 und 100.000 Elemente enthält und eine *große* Dataset enthält mehr als 100.000 Elemente.  
  
-   Der Arbeitsaufwand, der den Compare-Funktion oder der Hash-Funktion ausführt.  
  
-   Die Größe des verfügbaren Computerressourcen.  
  
-   Die Merkmale des Datasets. Beispielsweise kann ein Algorithmus ausführen, gut für Daten, die bereits nahezu sortiert ist, jedoch nicht auch für Daten, die nicht vollständig sortiert sind.  
  
-   Die Segmentgröße. Das optionale `_Chunk_size` Argument gibt an, wenn der Algorithmus aus einer parallelen Struktur zu einer seriellen sortieren Implementierung wechselt, wie es die gesamte Sortierung in kleinere Arbeitseinheiten unterteilt. Z. B. wenn 512 bereitgestellt wird, schaltet der Algorithmus zum seriellen Implementierung, wenn eine Arbeitseinheit 512 oder weniger Elemente enthält. Eine serielle Implementierung kann die gesamtleistung verbessern, da es nicht mehr den Aufwand ist, der zum Verarbeiten von Daten parallel erforderlich ist.  
  
 Es ist möglicherweise nicht sinnvoll, um ein kleines Dataset parallel zu sortieren, auch wenn eine große Anzahl von verfügbaren Computerressourcen stehen Ihnen oder Ihrem Compare-Funktion oder ein Hash-Funktion eine relativ große Menge an Arbeit führt. Sie können [Std:: Sort](../../standard-library/algorithm-functions.md#sort) Funktion, um kleine Datasets zu sortieren. (`parallel_sort` und `parallel_buffered_sort` Aufrufen `sort` bei der Angabe einer Blockgröße, die größer ist als das Dataset; allerdings `parallel_buffered_sort` müsste O(N) Speicherplatz zuzuordnen, die zusätzliche Zeit aufgrund von Konflikten oder Arbeitsspeicher sperrenzuordnung einige Zeit dauern können.)  
  
 Verwenden, müssen Sie Speicherplatz sparen, oder Ihre Speicherbelegungsfunktion unterliegt den Konflikt bei Sperre, `parallel_sort` um ein Dataset mit mittlerer Größe zu sortieren. `parallel_sort` ist kein zusätzlichen Speicherplatz erforderlich; die andere Algorithmen O(N) Speicherplatz benötigt wird.  
  
 Verwendung `parallel_buffered_sort` sortieren mittelgroße Datasets und wenn Ihre Anwendung die zusätzliche O(N) speicherplatzanforderungen erfüllt. `parallel_buffered_sort` kann besonders hilfreich sein, wenn eine große Anzahl von Verarbeitungsressourcen oder eine teure Compare-Funktion oder eine Hashfunktion vorliegt.  
  
 Verwendung `parallel_radixsort` sortieren großer Datasets erstellt werden und wenn Ihre Anwendung die zusätzliche O(N) speicherplatzanforderungen erfüllt. `parallel_radixsort` kann besonders hilfreich sein, wenn der entsprechende Vergleichsvorgang teurer ist, oder wenn beide Vorgänge teuer sind.  
  
> [!CAUTION]
>  Implementiert eine gute Hashfunktion müssen Sie wissen, den Dataset-Bereich und wie jedes Element in das Dataset in einen entsprechenden Wert ohne Vorzeichen transformiert wird. Daran, dass die Hash-Operation für Werte ohne Vorzeichen funktioniert, erwägen Sie eine andere Sortierung Strategie, wenn nicht signierte Hashwerte können nicht erstellt werden.  
  
 Im folgenden Beispiel wird die Leistung von `sort`, `parallel_sort`, `parallel_buffered_sort`, und `parallel_radixsort` für dieselbe große Menge zufälliger Daten.  
  
 [!code-cpp[concrt-choosing-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_15.cpp)]  
  
 In diesem Beispiel, in dem wird davon ausgegangen, dass es akzeptabel O(N) Speicherplatz während der Sortierung zugeordnet ist, `parallel_radixsort` am besten geeignet für dieses Dataset für diese Konfiguration führt.  
  
 [[Nach oben](#top)]  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Vorgehensweise: Schreiben einer parallel_for-Schleife](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)|Zeigt, wie die `parallel_for` Algorithmus zum Durchführen der Matrixmultiplikation.|  
|[Vorgehensweise: Schreiben einer parallel_for_each-Schleife](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)|Zeigt, wie die `parallel_for_each` Algorithmus berechnet die Anzahl von Primzahlen in einem [Std:: Array](../../standard-library/array-class-stl.md) -Objekt parallel.|  
|[Vorgehensweise: Verwenden von parallel_invoke zum Schreiben einer Runtime für paralleles Sortieren](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)|Erläutert, wie die Leistung des bitonischen Sortieralgorithmus mit dem `parallel_invoke`-Algorithmus verbessert werden.|  
|[Vorgehensweise: Ausführen von parallelen Vorgängen mithilfe von parallel_invoke](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|Erläutert, wie die Leistung eines Programms mit dem `parallel_invoke`-Algorithmus verbessert werden kann, das mehrere Vorgänge in einer freigegebenen Datenquelle ausführt.|  
|[Vorgehensweise: Paralleles Ausführen von Zuordnungs- und Reduzierungsoperationen](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)|Zeigt, wie die `parallel_transform` und `parallel_reduce` Algorithmen zur führen Sie einer Zuordnung und zur Reduzierung der Vorgang, mit denen die Vorkommen von Wörtern in Dateien ermittelt.|  
|[Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Beschreibt die PPL vor, die ein obligatorisches Programmiermodell bereitstellt, das Skalierbarkeit und Einfachheit der Verwendung beim Entwickeln gleichzeitige Anwendungen fördert.|  
|[Abbruch in der PPL](cancellation-in-the-ppl.md)|Erläutert die Rolle des Abbruchs in der PPL, wie zum Abbrechen paralleler Aufgaben sowie zum bestimmen, wann eine Aufgabengruppe abgebrochen wird.|  
|[Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|Erläutert die Rolle der Ausnahmebehandlung in der Concurrency Runtime.|  
  
## <a name="reference"></a>Referenz  

 [Parallel_for-Funktion](reference/concurrency-namespace-functions.md#parallel_for)
  
 [Parallel_for_each-Funktion](reference/concurrency-namespace-functions.md#parallel_for_each)  
  
 [Parallel_invoke-Funktion](reference/concurrency-namespace-functions.md#parallel_invoke)  

  
 [affinity_partitioner-Klasse](../../parallel/concrt/reference/affinity-partitioner-class.md)  
  
 [auto_partitioner-Klasse](../../parallel/concrt/reference/auto-partitioner-class.md)  
  
 [simple_partitioner-Klasse](../../parallel/concrt/reference/simple-partitioner-class.md)  
  
 [static_partitioner-Klasse](../../parallel/concrt/reference/static-partitioner-class.md)  
  

 [Parallel_sort-Funktion](reference/concurrency-namespace-functions.md#parallel_sort)  
  
 [Parallel_buffered_sort-Funktion](reference/concurrency-namespace-functions.md#parallel_buffered_sort)  
  
 [Parallel_radixsort-Funktion](reference/concurrency-namespace-functions.md#parallel_radixsort)


