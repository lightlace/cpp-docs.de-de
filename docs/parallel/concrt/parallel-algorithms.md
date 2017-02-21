---
title: "Parallele Algorithmen | Microsoft Docs"
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
  - "Parallele Algorithmen [Concurrency Runtime]"
ms.assetid: 045dca7b-4d73-4558-a44c-383b88a28473
caps.latest.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 36
---
# Parallele Algorithmen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Parallel Patterns Library (PPL) stellt die Algorithmen, die Auflistungen von Daten gleichzeitig verarbeiten. Diese Algorithmen ähneln denen von der Standardvorlagenbibliothek (STL).  
  
 Die parallelen Algorithmen bestehen aus vorhandenen Funktionen in der Concurrency Runtime. Z. B. die [Concurrency:: parallel_for](../Topic/parallel_for%20Function.md) -Algorithmus verwendet eine [Concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) Objekt die parallelen Schleifeniterationen ausführen. Die `parallel_for` Algorithmus verteilt die Arbeit auf Grundlage der verfügbaren Computerressourcen auf optimale Weise.  
  
##  <a name="a-nametopa-sections"></a><a name="top"></a> Abschnitte  
  
- [Der Parallel_for-Algorithmus](#parallel_for)  
  
- [Der Parallel_for_each-Algorithmus](#parallel_for_each)  
  
- [Der Parallel_invoke-Algorithmus](#parallel_invoke)  
  
- [Die Parallel_transform- und Parallel_reduce-Algorithmen](#parallel_transform_reduce)  
  
    - [Der Parallel_transform-Algorithmus](#parallel_transform)  
  
    - [Der Parallel_reduce-Algorithmus](#parallel_reduce)  
  
    - [Beispiel: Ausführen der Zuordnung und parallel zu reduzieren](#map_reduce_example)  
  
- [Partitionieren der Arbeit](#partitions)  
  
- [Parallele Sortierung](#parallel_sorting)  
  
    - [Auswählen eines Sortieralgorithmus](#choose_sort)  
  
##  <a name="a-nameparallelfora-the-parallelfor-algorithm"></a><a name="parallel_for"></a> Der Parallel_for-Algorithmus  
 Die [Concurrency:: parallel_for](../Topic/parallel_for%20Function.md) Algorithmus führt die gleiche Aufgabe wiederholt Parallel aus. Jede dieser Aufgaben wird mit einem Iterationswert parametrisiert. Dieser Algorithmus ist nützlich, wenn Sie eine Schleife verfügen, die keine Ressourcen zwischen Iterationen dieser Schleife gemeinsam nutzt.  
  
 Die `parallel_for` -Algorithmus verteilt die Aufgaben auf optimale Weise für die parallele Ausführung. Er verwendet einen Arbeitsübernahme-Algorithmus und ein Bereich stehlen, um diese Partitionen zu verteilen, wenn Arbeitslasten nicht ausgeglichen sind. Wenn eine Schleifeniteration kooperativ blockiert wird, verteilt die Laufzeit den Bereich der Iterationen, der die der aktuelle Thread eine andere Threads oder Prozessoren zugewiesen ist. Wenn ein Thread einen Bereich von Iterationen abgeschlossen ist, verteilt die Common Language Runtime auf ähnliche Weise Arbeit von anderen Threads zu diesem Thread. Die `parallel_for` -Algorithmus unterstützt auch *geschachtelten Parallelität*. Wenn eine parallele Schleife eine andere parallele Schleife enthält, koordiniert die Common Language Runtime Verarbeitungsressourcen zwischen der Schleifenkörper in eine effiziente Möglichkeit für die parallele Ausführung.  
  
 Die `parallel_for` Algorithmus verfügt über mehrere überladene Versionen. Die erste Version verwendet einen Anfangswert, einen Endwert und eine Arbeitsfunktion (ein Lambda-Ausdruck, Funktionsobjekt oder Funktionszeiger). Die zweite Version verwendet einen Anfangswert, einen Endwert, einen Wert mit dem Schritt, und eine Arbeitsfunktion. Die erste Version dieser Funktion verwendet 1 als Schrittwert. Die übrigen Versionen nehmen Partitionierer-Objekte, die können Sie angeben, wie `parallel_for` Bereiche zwischen Threads sollten partitioniert werden. Partitionierer werden ausführlich im Abschnitt erläutert [Partitionierung Arbeit](#partitions) in diesem Dokument.  
  
 Sie können viele konvertieren `for` Schleifen verwenden `parallel_for`. Allerdings die `parallel_for` Algorithmus unterscheidet sich von der `for` Anweisung auf folgende Weise:  
  
-   Die `parallel_for` Algorithmus `parallel_for` die Aufgaben nicht in einer vordefinierten Reihenfolge ausgeführt.  
  
-   Die `parallel_for` Algorithmus beliebige beenden-Bedingung nicht unterstützt. Die `parallel_for` Algorithmus wird beendet, wenn der aktuelle Wert der Iterationsvariablen eine ist kleiner als `last`.  
  
-   Die `_Index_type` Typparameter muss einen ganzzahligen Typ sein. Dieser ganzzahlige Typ kann mit oder ohne Vorzeichen.  
  
-   Die Schleifeniteration muss vorwärts gerichtet sein. Die `parallel_for` -Algorithmus löst eine Ausnahme vom Typ [Std:: invalid_argument](../../standard-library/invalid-argument-class.md) Falls der `_Step` Parameter ist kleiner als 1.  
  
-   Der Mechanismus für die Ausnahmebehandlung für die `parallel_for` Algorithmus unterscheidet sich von einem `for` Schleife. Wenn mehrere Ausnahmen gleichzeitig in einem parallelen Schleifentext auftreten, die Common Language Runtime gibt nur eine der Ausnahmen an den Thread, der aufgerufen `parallel_for`. Darüber hinaus, wenn eine Schleifeniteration eine Ausnahme auslöst, wird die Common Language Runtime nicht sofort die gesamte Schleife beendet. Stattdessen wird die Schleife in den abgebrochenen Zustand platziert und verwirft die Runtime alle Aufgaben, die noch nicht gestartet wurden. Weitere Informationen zur Behandlung von Ausnahmen und parallele Algorithmen finden Sie unter [Exception Handling](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 Obwohl die `parallel_for` Algorithmus beliebige beenden-Bedingung nicht unterstützt, können Sie alle Aufgaben beendet Abbruch. Weitere Informationen über das Abbrechen finden Sie unter [Abbruch](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation_in_the_ppl).  
  
> [!NOTE]
>  Die Planung Kosten, dass die Ergebnisse aus den Lastenausgleich und die Unterstützung für Features, z. B. Abbruch nicht die Vorteile der Text der Schleife parallel ausgeführten überwinden können, ist besonders bei Schleifentext relativ klein. Sie können diesen zusätzlichen Aufwand minimieren, indem Sie einen Partitionierer in der parallelen Schleife. Weitere Informationen finden Sie unter [Partitionierung Arbeit](#partitions) Weiter unten in diesem Dokument.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die grundlegende Struktur der `parallel_for` Algorithmus. Diesem Beispiel wird jeder Wert im Bereich [1, 5] parallel auf der Konsole aus.  
  
 [!CODE [concrt-parallel-for-structure#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-for-structure#1)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe:  
  
```Output  
1 2 4 3 5  
```  
  
 Da die `parallel_for` Algorithmus für jedes Element parallel fungiert, variiert die Reihenfolge, in der die Werte werden auf der Konsole ausgegeben.  
  
 Für ein vollständiges Beispiel, verwendet der `parallel_for` -Algorithmus finden Sie unter [Gewusst wie: Schreiben einer Parallel_for-Schleife](../../parallel/concrt/how-to-write-a-parallel-for-loop.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="a-nameparallelforeacha-the-parallelforeach-algorithm"></a><a name="parallel_for_each"></a> Der Parallel_for_each-Algorithmus  
 Die [Concurrency:: parallel_for_each](../Topic/parallel_for_each%20Function.md) Algorithmus führt Aufgaben für einen iterativen Container, z. B. über die STL parallel. Er verwendet die gleiche Partitionierungslogik wie der `parallel_for`-Algorithmus.  
  
 Die `parallel_for_each` -Algorithmus die STL ähnelt [Std:: for_each](../Topic/for_each.md) Algorithmus, außer dass die `parallel_for_each` -Algorithmus die Aufgaben gleichzeitig ausführt. Wie andere parallele Algorithmen, `parallel_for_each` die Aufgaben nicht in einer bestimmten Reihenfolge ausgeführt.  
  
 Obwohl die `parallel_for_each` Algorithmus funktioniert sowohl in forward-Iteratoren random-Access-Iteratoren, bietet eine bessere Leistung mit wahlfreiem Zugriffsiteratoren.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die grundlegende Struktur der `parallel_for_each` Algorithmus. In diesem Beispiel wird in der Konsole jeden Wert in einem [Std:: Array](../../standard-library/array-class-stl.md) -Objekt parallel.  
  
 [!CODE [concrt-parallel-for-each-structure#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-for-each-structure#1)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe:  
  
```Output  
4 5 1 2 3  
```  
  
 Da die `parallel_for_each` Algorithmus für jedes Element parallel fungiert, variiert die Reihenfolge, in der die Werte werden auf der Konsole ausgegeben.  
  
 Für ein vollständiges Beispiel, verwendet der `parallel_for_each` -Algorithmus finden Sie unter [Gewusst wie: Schreiben einer Parallel_for_each-Schleife](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="a-nameparallelinvokea-the-parallelinvoke-algorithm"></a><a name="parallel_invoke"></a> Der Parallel_invoke-Algorithmus  
 Die [Concurrency:: parallel_invoke](../Topic/parallel_invoke%20Function.md) Algorithmus führt eine Reihe von Aufgaben Parallel aus. Es gibt keine zurück, bis jeder Aufgabe abgeschlossen ist. Dieser Algorithmus ist nützlich, wenn Sie mehrere unabhängige Aufgaben verfügen, die zur gleichen Zeit ausgeführt werden soll.  
  
 Die `parallel_invoke` Algorithmus verwendet als Parameter eine Reihe von Arbeitsfunktionen (Lambda-Funktionen, Funktionsobjekte oder Funktionszeiger). Die `parallel_invoke` Algorithmus wird überladen, um zwischen zwei und zehn Parameter in Anspruch nehmen. Jede Funktion, die Sie übergeben `parallel_invoke` muss 0 (null) Parameter akzeptieren.  
  
 Wie andere parallele Algorithmen, `parallel_invoke` die Aufgaben nicht in einer bestimmten Reihenfolge ausgeführt. Das Thema [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md) wird erläutert, wie die `parallel_invoke` Algorithmus bezieht sich auf Aufgaben und Aufgabengruppen.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die grundlegende Struktur der `parallel_invoke` Algorithmus. Dieses Beispiel ruft gleichzeitig die `twice` Funktion auf drei lokale Variablen und das Ergebnis an die Konsole ausgegeben.  
  
 [!CODE [concrt-parallel-invoke-structure#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-invoke-structure#1)]  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```Output  
108 11.2 HelloHello  
```  
  
 Vollständige Beispiele für die Verwendung der `parallel_invoke` -Algorithmus, finden Sie unter [wie: Verwenden von Parallel_invoke um parallele Sortierung Schreiben einer](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md) und [wie: Parallel_invoke zum Ausführen von parallelen Vorgängen](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="a-nameparalleltransformreducea-the-paralleltransform-and-parallelreduce-algorithms"></a><a name="parallel_transform_reduce"></a> Die Parallel_transform- und Parallel_reduce-Algorithmen  
 Die [parallel_transform](../Topic/parallel_transform%20Function.md) und [concurrency::parallel_reduce](../Topic/parallel_reduce%20Function.md) -Algorithmen sind parallele Versionen einer STL-Algorithmen [std::transform](../Topic/transform.md) und [Std:: Accumulate](../Topic/accumulate.md), bzw.. Die Concurrency Runtime-Versionen verhalten sich wie die STL-Versionen, mit der Ausnahme, dass die Reihenfolge der Operation nicht ermittelt werden kann, da sie parallel ausgeführt. Verwenden Sie diese Algorithmen, bei der Arbeit mit einem Satz, der groß genug ist, Leistung und Skalierbarkeit Vorteile parallel verarbeitet werden.  
  
> [!IMPORTANT]
>  Die `parallel_transform` und `parallel_reduce` Algorithmen nur random-Access, bidirektionale und Weiterleiten Iteratoren unterstützt, da diese Iteratoren stabil Speicheradressen erzeugen. Auch diese Iteratoren erzeugen müssen nicht`const` l-Werte.  
  
###  <a name="a-nameparalleltransforma-the-paralleltransform-algorithm"></a><a name="parallel_transform"></a> Der Parallel_transform-Algorithmus  
 Sie können die `parallel transform` Algorithmus viele Parallelisierung Datenvorgänge ausführt. Sie haben unter anderem folgende Möglichkeiten:  
  
-   Passen Sie die Helligkeit eines Bildes an, und führen Sie andere Verarbeitungsvorgänge Bild.  
  
-   Die Summe oder nutzen Sie das Skalarprodukt zwischen beiden Vektoren, und führen Sie andere numerischen Berechnungen für Vektoren.  
  
-   Führen Sie die 3D-Szene Chow Verfolgung, wobei jede Iteration ein Pixel bezeichnet, die gerendert werden muss.  
  
 Im folgende Beispiel wird die grundlegende Struktur, die verwendet wird, zum Aufrufen der `parallel_transform` Algorithmus. In diesem Beispiel negiert jedes Element eine std::[Vektor](vector%20Class.md) Objekt auf zwei Arten. Die erste Methode verwendet einen Lambda-Ausdruck. Die zweite Möglichkeit verwendet [std::negate](../../standard-library/negate-struct.md), die sich daraus ableitet [std::unary_function](../../standard-library/unary-function-struct.md).  
  
 [!CODE [concrt-basic-parallel-transform#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-parallel-transform#1)]  
  
> [!WARNING]
>  Dieses Beispiel veranschaulicht die grundlegende Verwendung von `parallel_transform`. Da die Arbeitsfunktion nicht viel Arbeit durchgeführt wird, wird eine wesentliche Verbesserung der Leistung in diesem Beispiel nicht erwartet.  
  
 Die `parallel_transform` Algorithmus verfügt über zwei Überladungen. Die erste Überladung nimmt einen Eingabewert und eine unäre Funktion. Die unäre-Funktion kann ein Lambda-Ausdruck, der ein Argument, ein Funktionsobjekt oder ein Typ, der abgeleitet wird `unary_function`. Die zweite Überladung nimmt zwei Eingabebereiche und eine binäre Funktion. Der binäre Funktion kann ein Lambda-Ausdruck, die akzeptiert zwei Argumente, ein Funktionsobjekt oder ein Typ, der abgeleitet werden [std::binary_function](../../standard-library/binary-function-struct.md). Das folgende Beispiel veranschaulicht diese Unterschiede.  
  
 [!CODE [concrt-parallel-transform-vectors#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-transform-vectors#2)]  
  
> [!IMPORTANT]
>  Der Iterator, der für die Ausgabe des angegebenen `parallel_transform` muss vollständig Eingabeiterators überschneiden oder sich nicht überschneiden. Das Verhalten dieses Algorithmus ist nicht angegeben, wenn die Eingabe- und Iteratoren teilweise überlappen.  
  
###  <a name="a-nameparallelreducea-the-parallelreduce-algorithm"></a><a name="parallel_reduce"></a> Der Parallel_reduce-Algorithmus  
 Die `parallel_reduce` Algorithmus ist nützlich, bei einer Abfolge von Vorgängen, die die assoziative-Eigenschaft zu erfüllen. (Dieser Algorithmus erfordert keine Eigenschaft kommutativ.) Hier sind einige Vorgänge, die Sie ausführen können `parallel_reduce`:  
  
-   Multiplizieren Sie Sequenzen von Matrizen bis hin zu eine Matrix zu erzeugen.  
  
-   Multipliziert einen Vektor einer Folge von Matrizen bis hin zu einen Vektor zu erzeugen.  
  
-   Berechnen Sie die Länge einer Sequenz von Zeichenfolgen.  
  
-   Kombinieren Sie eine Liste von Elementen, z. B. Zeichenfolgen, in ein Element.  
  
 Im folgende grundlegende Beispiel wird gezeigt, wie die `parallel_reduce` Algorithmus, um eine Sequenz von Zeichenfolgen zu einer einzigen Zeichenfolge zu kombinieren. Wie bei den Beispielen für `parallel_transform`, Leistungssteigerungen in diesem einfachen Beispiel werden nicht wie erwartet.  
  
 [!CODE [concrt-basic-parallel-reduce#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-parallel-reduce#1)]  
  
 In vielen Fällen können Sie sich vorstellen `parallel_reduce` als Kurzform für die Verwendung der `parallel_for_each` Algorithmus zusammen mit den [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) Klasse.  
  
###  <a name="a-namemapreduceexamplea-example-performing-map-and-reduce-in-parallel"></a><a name="map_reduce_example"></a> Beispiel: Ausführen der Zuordnung und parallel zu reduzieren  
 Ein *Karte* -Vorgang gilt eine Funktion für jeden Wert in einer Sequenz. Ein *reduzieren* Vorgang kombiniert die Elemente einer Sequenz in einen Wert. Sie können die Standardvorlagenbibliothek (STL) [std::transform](../Topic/transform.md)[Std:: Accumulate](../Topic/accumulate.md) Klassen zum Ausführen von Zuordnungs- und Vorgänge zu reduzieren. Für viele Probleme, Sie können jedoch die `parallel_transform` Algorithmus, um den Zuordnungsvorgang parallel ausführen und die `parallel_reduce` Algorithmus den Reduce-Vorgang parallel auszuführen.  
  
 Im folgenden Beispiel wird die Zeit, die die Summe von Primzahlen seriell sowie parallel berechnet. Map-Phase transformiert nicht Primzahlen Werte zwischen 0 und der Reduce-Phase Summen, die Werte zu.  
  
 [!CODE [concrt-parallel-map-reduce-sum-of-primes#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-map-reduce-sum-of-primes#1)]  
  
 Ein anderes Beispiel führt eine Karte und reduce-Vorgang parallel, finden Sie unter [Gewusst wie: Ausführen-Zuordnung und Reduzierung Vorgänge parallel](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="a-namepartitionsa-partitioning-work"></a><a name="partitions"></a> Partitionieren der Arbeit  
 Um einen Vorgang in einer Datenquelle zu parallelisieren, ist ein wichtiger Schritt *Partition* der Quelle in mehrere Abschnitte, die von mehreren Threads gleichzeitig zugegriffen werden kann. Ein Partitionierer gibt an, wie paralleler Algorithmen Bereiche zwischen Threads partitionieren sollten. Wie zuvor in diesem Dokument erläutert wird, ist der Standardwert der PPL Partitionierung Mechanismus, der eine anfänglichen Arbeitslast erstellt und verwendet dann einen Arbeitsübernahme-Algorithmus und ein Bereich stehlen, um diese Partitionen zu verteilen, wenn diese nicht ausgeglichen sind. Wenn eine Schleifeniteration einen Bereich von Iterationen abgeschlossen ist, verteilt die Common Language Runtime z. B. Arbeit von anderen Threads zu diesem Thread. Jedoch möglicherweise für einige Szenarien einen anderen Mechanismus zur Partitionierung angeben möchten, der für das Problem besser eignet.  
  
 Die `parallel_for`, `parallel_for_each`, und `parallel_transform` Algorithmen bieten überladene Versionen, die einen zusätzlichen Parameter, `_Partitioner`. Dieser Parameter definiert den Partitionierer, der Arbeit unterteilt. Hier werden die Arten der Partitionierer, die die PPL definiert:  
  
 [Concurrency::affinity_partitioner](../../parallel/concrt/reference/affinity-partitioner-class.md)  
 Teilt arbeiten in einer festen Anzahl von Bereichen (in der Regel die Anzahl der Arbeitsthreads, die für die Arbeit in der Schleife verfügbar sind). Dieser Typ Partitionierer ähnelt `static_partitioner`, jedoch wird, verbessert die Art und Weise, wie Bereiche Arbeitsthreads zugeordnet. Dieser Typ Partitionierer kann die Leistung verbessern, wenn eine Schleife über dieselben Daten mehrmals (z. B. eine Schleife in einer Schleife) ausgeführt wird und die Daten in den Cache passen. Diese Partitionierer verwendet nicht vollständig in Abbruch. Es auch einen kooperativen blockierenden Semantik nicht verwendet und daher nicht verwendet werden, mit parallelen Schleifen, die forward abhängig sind.  
  
 [Concurrency::auto_partitioner](../../parallel/concrt/reference/auto-partitioner-class.md)  
 Teilt arbeiten in eine ursprüngliche Anzahl von Bereichen (in der Regel die Anzahl der Arbeitsthreads, die für die Arbeit in der Schleife verfügbar sind). Die Common Language Runtime verwendet dieses Typs standardmäßig, wenn Sie einen überladene parallelen Algorithmus nicht aufrufen, die akzeptiert ein `_Partitioner` Parameter. Jeder Bereich kann in Teilbereiche aufgeteilt werden, und somit aktiviert den Lastenausgleich erfolgen. Wenn Sie ein Bereich von Arbeit abgeschlossen ist, verteilt die Common Language Runtime Teilbereiche Arbeit von anderen Threads zu diesem Thread. Verwenden Sie diese Partitionierer, wenn Ihre Arbeitslast nicht unter einem der anderen Kategorien fällt oder wenn Sie die vollständige Unterstützung für Abbruch oder Kooperative Blockierung benötigen.  
  
 [Concurrency::simple_partitioner](../../parallel/concrt/reference/simple-partitioner-class.md)  
 Teilt funktionieren in Bereiche, damit jeder Bereich mindestens die Anzahl von Iterationen enthält, die von der angegebenen Segmentgröße angegeben werden. Dieser Typ Partitionierer beteiligt Lastenausgleich; Allerdings ist die Common Language Runtime nicht Bereiche in untergeordnete Bereiche unterteilen. Für jeden Arbeitsthread die Common Language Runtime nach einem Abbruchvorgang gesucht und führt einen Lastenausgleich nach `_Chunk_size` Iterationen abgeschlossen.  
  
 [Concurrency::static_partitioner](../../parallel/concrt/reference/static-partitioner-class.md)  
 Teilt arbeiten in einer festen Anzahl von Bereichen (in der Regel die Anzahl der Arbeitsthreads, die für die Arbeit in der Schleife verfügbar sind). Dieser Typ Partitionierer kann die Leistung verbessern, da es kein Arbeitsübernahme- und daher weniger Aufwand hat. Verwenden Sie diese Partitionierer-Typ, wenn jede Iteration einer parallelen Schleife einen festen und einheitlichen Arbeitsaufwand führt und Sie nicht weiterleiten Kooperative Blockierung oder abbruchunterstützung erforderlich ist.  
  
> [!WARNING]
>  Die `parallel_for_each` und `parallel_transform` Algorithmen unterstützen nur Container, die random-Access-Iteratoren (z. B. std::[Vektor](vector%20Class.md)) für die statischen und einfache Affinität Partitionierer. Die Verwendung von Containern, die bidirektionalen und forward-Iteratoren verwenden erzeugt einen Fehler während der Kompilierung. Dem Standardpartitionierer `auto_partitioner`, alle drei dieser Iterator-Typen unterstützt.  
  
 Für diese Partitionierer werden normalerweise verwendet auf die gleiche Weise, mit Ausnahme von `affinity_partitioner`. Die meisten Partitionierer-Typen den Zustand nicht beibehalten und nicht von der Laufzeit geändert werden. Daher können Sie diese Objekte Partitionierer an der Aufrufsite erstellen, wie im folgenden Beispiel gezeigt.  
  
 [!CODE [concrt-static-partitioner#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-static-partitioner#1)]  
  
 Allerdings müssen Sie übergeben ein `affinity_partitioner` Objekt als nicht`const`, l-Wert verweisen, sodass der Algorithmus den Zustand für zukünftige Schleifen Wiederverwendung speichern kann. Das folgende Beispiel zeigt eine einfache Anwendung, die denselben Vorgang in einem DataSet parallel mehrmals ausgeführt. Die Verwendung von `affinity_partitioner` kann die Leistung verbessern, da das Array wahrscheinlich in den Cache passen.  
  
 [!CODE [concrt-affinity-partitioner#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-affinity-partitioner#1)]  
  
> [!CAUTION]
>  Vorsichtig, wenn Sie vorhandenen Code, der auf einen kooperativen blockierenden Semantik ändern verwenden basiert `static_partitioner` oder `affinity_partitioner`. Diese Typen Partitionierer verwenden Sie den Lastenausgleich oder Bereich zu stehlen und aus diesem Grund können das Verhalten der Anwendung ändern.  
  
 Die beste Möglichkeit zum Ermitteln, ob einen Partitionierer in einem gegebenen Szenario ist experimentieren und messen, wie lange dauert die Vorgänge bei repräsentativer Auslastung und Computerkonfigurationen abgeschlossen. Z. B. statische Partitionierung, kann erhebliche Beschleunigung auf einem Multi-Core-Computer, der nur wenige Kernen bereitstellen, aber es kann zu einer Verlangsamung auf Computern mit relativ viele Kerne führen.  
  
 [[Nach oben](#top)]  
  
##  <a name="a-nameparallelsortinga-parallel-sorting"></a><a name="parallel_sorting"></a> Parallele Sortierung  
 Die PPL bietet drei Sortieralgorithmen: [Concurrency:: parallel_sort](../Topic/parallel_sort%20Function.md), [Concurrency:: parallel_buffered_sort](../Topic/parallel_buffered_sort%20Function.md), und [Concurrency:: parallel_radixsort](../Topic/parallel_radixsort%20Function.md). Diese Sortieralgorithmen sind nützlich, bei einem Dataset, die parallel zu sortierenden profitieren können. Insbesondere eignet sich parallel sortieren, wenn Sie ein großes Dataset haben oder wenn Sie eine sehr hohe Vergleichsvorgang um Ihre Daten zu sortieren. Jeder dieser Algorithmen sortiert die Elemente an.  
  
 Die `parallel_sort` und `parallel_buffered_sort` sind Algorithmen sowohl vergleichsbasierte. D. h. Vergleichen sie Elemente nach Wert. Die `parallel_sort` Algorithmus verfügt über keine zusätzlichen Speicherbedarf und eignet sich für allgemeine sortieren. Die `parallel_buffered_sort` kann es sich um eine Ausführung des Algorithmus besser als `parallel_sort`, O(N) Speicherplatz erfordert jedoch.  
  
 Die `parallel_radixsort` Algorithmus Hash-basiert. Das heißt, verwendet es Ganzzahlschlüssel Elemente sortieren. Mithilfe von Schlüsseln kann dieser Algorithmus direkt berechnen, das Ziel eines Elements statt Vergleiche zu verwenden. Wie `parallel_buffered_sort`, dieser Algorithmus erfordert O(N) Speicherplatz.  
  
 In der folgenden Tabelle werden die wichtigen Eigenschaften der drei parallele Sortieralgorithmen zusammengefasst.  
  
|Algorithmus|Beschreibung|Sortieren von Mechanismus|Sort-Stabilität|Speicherbedarf|Zeit.|Iteratorzugriff|  
|---------------|-----------------|-----------------------|--------------------|-------------------------|---------------------|---------------------|  
|`parallel_sort`|Allgemeine vergleichsbasierte sortieren.|Vergleichsbasierte (aufsteigend)|Instabile|Keine|O((N/P)Log(N/P) + 2N((P-1)/P))|Random|  
|`parallel_buffered_sort`|Schneller allgemeine vergleichsbasierte sortieren, die O(N) Platz erforderlich ist.|Vergleichsbasierte (aufsteigend)|Instabile|Erfordert zusätzlichen O(N) Speicherplatz|O((N/P)Log(N))|Random|  
|`parallel_radixsort`|Ganze Zahl schlüsselbasierten sortieren, die O(N) Platz erforderlich ist.|Hash-basierte|Stable|Erfordert zusätzlichen O(N) Speicherplatz|O(N/P)|Random|  
  
 Die folgende Abbildung zeigt die wichtigen Eigenschaften der drei parallele Sortieralgorithmen mehr grafisch an.  
  
 ![Vergleich der Sortieralgorithmen](../../parallel/concrt/media/concrt_parallel_sorting.png "concrt_parallel_sorting")  
  
 Diese parallel Sortieralgorithmen Regeln den des Abbruchs und der Ausnahmebehandlung. Weitere Informationen zum Abbruch und Ausnahmebehandlung in der Concurrency Runtime finden Sie unter [Abbrechen von parallelen Algorithmen](../../parallel/concrt/cancellation-in-the-ppl.md#algorithms) und [Exception Handling](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
> [!TIP]
>  Diese parallel Sortieralgorithmen unterstützen Verschiebesemantik. Sie können einen bewegungszuweisungsoperator zum Aktivieren von Austauschvorgängen effizienter erfolgen definieren. Weitere Informationen zu Verschiebungssemantik und der bewegungszuweisungsoperator, finden Sie unter [Rvalue-Verweisdeklarator: & &](../../cpp/rvalue-reference-declarator-amp-amp.md), und [Konstruktoren verschieben und verschieben Zuweisung Operatoren (C++)](../../cpp/move-constructors-and-move-assignment-operators-cpp.md). Die Sortieralgorithmen verwenden, wenn Sie einen bewegungszuweisungsoperator oder Swap-Funktion nicht bereitstellen, den Kopierkonstruktor.  
  
 Im folgende grundlegende Beispiel wird gezeigt, wie `parallel_sort` zum Sortieren einer `vector` von `int` Werte. In der Standardeinstellung `parallel_sort` verwendet [Std:: less](../../standard-library/less-struct.md) zum Vergleichen von Werten.  
  
 [!CODE [concrt-basic-parallel-sort#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-parallel-sort#1)]  
  
 Dieses Beispiel zeigt, wie Sie eine benutzerdefinierte Vergleichsfunktion bereitstellen. Er verwendet die [Std::complex::real](../Topic/complex::real.md) Methode zum Sortieren [std::complex \< double>](../../standard-library/complex-class.md) Werte in aufsteigender Reihenfolge.  
  
 [!CODE [concrt-basic-parallel-sort#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-basic-parallel-sort#2)]  
  
 Dieses Beispiel zeigt, wie Sie eine Hashfunktion, die `parallel_radixsort` Algorithmus. In diesem Beispiel sortiert 3D-Punkten. Die Punkte werden basierend auf ihrer Entfernung Bezugspunkt sortiert.  
  
 [!CODE [concrt-parallel-sort-points#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-sort-points#1)]  
  
 Zur Veranschaulichung verwendet dieses Beispiel einen relativ kleinen Satz von Daten. Sie können die ursprüngliche Größe des Vektors Leistungssteigerungen über größere Datenmengen experimentieren erhöhen.  
  
 Dieses Beispiel verwendet einen Lambda-Ausdruck als Hashfunktion. Sie können auch eine integrierte Implementierung von der std::[hash-Klasse](hash%20Class.md) oder eigene Spezialisierung definieren. Sie können auch eine benutzerdefinierte Funktion Hashobjekt verwenden, wie im folgenden Beispiel gezeigt:  
  
 [!CODE [concrt-parallel-sort-points#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-sort-points#2)]  
  
 [!CODE [concrt-parallel-sort-points#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-sort-points#3)]  
  
 Die Hash-Funktion muss einen ganzzahligen Typ zurückgeben ([Std::is_integral::value](../../standard-library/is-integral-class.md) muss `true`). Dieser ganzzahlige Typ muss in den Typ `size_t`.  
  
###  <a name="a-namechoosesorta-choosing-a-sorting-algorithm"></a><a name="choose_sort"></a> Auswählen eines Sortieralgorithmus  
 In vielen Fällen `parallel_sort` bietet das optimale Gleichgewicht zwischen Geschwindigkeit und Leistung. Allerdings als Sie erhöhen die Größe des Datasets, die Anzahl der Prozessoren verfügbar sind oder die Komplexität der Compare-Funktion `parallel_buffered_sort` oder `parallel_radixsort` bieten eine bessere Leistung. Die beste Methode zum Ermitteln von der Sortieralgorithmus in einem gegebenen Szenario zu verwenden ist experimentieren und messen, wie lange es dauert, um repräsentativen Computerkonfigurationen typisch für die Daten zu sortieren. Bedenken Sie die folgenden Richtlinien beim Auswählen einer Strategie für die Sortierung.  
  
-   Die Größe des Datasets. In diesem Dokument eine *kleine* Dataset weniger als 1.000 Elemente enthält, eine *Mittel* Dataset zwischen 10.000 und 100.000 Elementen enthält und ein *große* Dataset enthält mehr als 100.000 Elemente.  
  
-   Der Arbeitsaufwand, der die Compare-Funktion oder einen Hash-Funktion ausführt.  
  
-   Die Menge der verfügbaren Computerressourcen.  
  
-   Die Merkmale des Datasets. Ein Algorithmus kann z. B. ausführen, gut für Daten, die bereits fast sortiert ist, aber nicht so gut für Daten, die nicht vollständig sortiert sind.  
  
-   Die Segmentgröße. Das optionale `_Chunk_size` Argument gibt an, wenn der Algorithmus aus einer parallelen auf eine serielle Sortierung Implementierung wechselt, wie es die gesamte Sortierung in kleinere Arbeitseinheiten unterteilt. Z. B. Wenn Sie 512 bereitstellen, wechselt der Algorithmus in serielle Implementierung eine Arbeitseinheit 512 oder weniger Elemente enthält. Eine serielle Implementierung verbessert allgemeine Leistung, da es nicht mehr den Aufwand, der zum Verarbeiten von Daten parallel erforderlich ist.  
  
 Es ist möglicherweise nicht sinnvoll sein, einen kleinen Dataset parallel zu sortieren, auch wenn Sie über eine große Anzahl von verfügbaren Computerressourcen oder die Compare-Funktion oder einen Hash-Funktion eine relativ große Menge an Arbeit führt. Sie können [Std:: Sort](../Topic/sort.md) Funktion, um kleine Datasets zu sortieren. (`parallel_sort` und `parallel_buffered_sort` Aufrufen `sort` bei der Angabe einer Größe, die größer ist als das Dataset; allerdings `parallel_buffered_sort` müssten O(N) Speicherplatz zuzuordnen, die zusätzliche Zeit aufgrund von Konflikten oder Arbeitsspeicher sperrenzuordnung dauern.)  
  
 Wenn müssen Sie Speicherplatz sparen oder Ihre Speicherbelegungsfunktion unterliegt Sperrenkonflikte, `parallel_sort` Dataset mittlerer Größe zu sortieren. `parallel_sort` erfordert keinen zusätzlichen Speicherplatz. die andere Algorithmen O(N) Speicherplatz benötigt wird.  
  
 Verwendung `parallel_buffered_sort` zum Sortieren von Datasets mittlerer Größe und wenn Ihre Anwendung die zusätzliche O(N) Speicherplatz erfüllt. `parallel_buffered_sort` kann besonders hilfreich sein, wenn Sie eine große Anzahl von Ressourcen oder eine teure Compare-Funktion oder Hash-Funktion haben.  
  
 Verwendung `parallel_radixsort` Sortieren großer Datasets und wenn Ihre Anwendung die zusätzliche O(N) Speicherplatz erfüllt. `parallel_radixsort` kann besonders hilfreich sein, wenn der entsprechende Vergleichsvorgang teurer ist, oder wenn beide Vorgänge teuer sind.  
  
> [!CAUTION]
>  Implementieren einer guten Hashfunktion müssen Sie wissen, der Dataset-Bereich und Transformation von jedem Element im Dataset in einen entsprechenden Wert ohne Vorzeichen. Da die Hash-Operation auf Werte ohne Vorzeichen verwendet werden kann, sollten Sie eine andere Sortierung Strategie, wenn nicht signierte Hashwerte erzeugt werden können.  
  
 Im folgende Beispiel wird die Leistung von `sort`, `parallel_sort`, `parallel_buffered_sort`, und `parallel_radixsort` mit dem gleichen großen Satz von zufälligen Daten.  
  
 [!CODE [concrt-choosing-parallel-sort#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-choosing-parallel-sort#1)]  
  
 In diesem Beispiel, wobei davon ausgegangen wird, dass es akzeptabel O(N) Speicherplatz während der Sortierung zugeordnet ist, `parallel_radixsort` führt die am besten für dieses Dataset auf diesem Computerkonfiguration.  
  
 [[Nach oben](#top)]  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Gewusst wie: Schreiben einer Parallel_for-Schleife](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)|Veranschaulicht, wie die `parallel_for` Algorithmus Matrixmultiplikation.|  
|[Gewusst wie: Schreiben einer Parallel_for_each-Schleife](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)|Veranschaulicht, wie die `parallel_for_each` Algorithmus zum Berechnen der Anzahl von Primzahlen in einem [Std:: Array](../../standard-library/array-class-stl.md) -Objekt parallel.|  
|[Gewusst wie: Verwenden von Parallel_invoke um parallele Sortierung Schreiben einer](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)|Erläutert, wie die Leistung des bitonischen Sortieralgorithmus mit dem `parallel_invoke`-Algorithmus verbessert werden.|  
|[Gewusst wie: Verwenden von Parallel_invoke zum Ausführen von parallelen Vorgängen](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|Erläutert, wie die Leistung eines Programms mit dem `parallel_invoke`-Algorithmus verbessert werden kann, das mehrere Vorgänge in einer freigegebenen Datenquelle ausführt.|  
|[Gewusst wie: Ausführen von Zuordnungs- und Reduzierungsoperationen Parallel](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)|Veranschaulicht, wie die `parallel_transform` und `parallel_reduce` Algorithmen führen Sie eine Karte und reduce-Vorgang, der zählt die Vorkommen der Wörter in Dateien.|  
|[Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Beschreibt die PPL, die ein obligatorisches Programmiermodell bereitstellt, das Skalierbarkeit und einfache Handhabung beim Entwickeln gleichzeitige Anwendungen fördert.|  
|[Abbruch](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation_in_the_ppl)|Erläutert die Rolle des Abbruchs in der PPL, wie zum Abbrechen paralleler Aufgaben und bestimmen, wann eine Aufgabengruppe abgebrochen wird.|  
|[Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|Erläutert die Rolle der Ausnahmebehandlung in der Concurrency Runtime.|  
  
## <a name="reference"></a>Verweis  
 [Parallel_for-Funktion](../Topic/parallel_for%20Function.md)  
  
 [Parallel_for_each-Funktion](../Topic/parallel_for_each%20Function.md)  
  
 [Parallel_invoke-Funktion](../Topic/parallel_invoke%20Function.md)  
  
 [Affinity_partitioner-Klasse](../../parallel/concrt/reference/affinity-partitioner-class.md)  
  
 [Auto_partitioner-Klasse](../../parallel/concrt/reference/auto-partitioner-class.md)  
  
 [Simple_partitioner-Klasse](../../parallel/concrt/reference/simple-partitioner-class.md)  
  
 [Static_partitioner-Klasse](../../parallel/concrt/reference/static-partitioner-class.md)  
  
 [Parallel_sort-Funktion](../Topic/parallel_sort%20Function.md)  
  
 [Parallel_buffered_sort-Funktion](../Topic/parallel_buffered_sort%20Function.md)  
  
 [Parallel_radixsort-Funktion](../Topic/parallel_radixsort%20Function.md)

