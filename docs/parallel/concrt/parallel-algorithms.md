---
title: Parallele Algorithmen
ms.date: 11/19/2018
helpviewer_keywords:
- parallel algorithms [Concurrency Runtime]
ms.assetid: 045dca7b-4d73-4558-a44c-383b88a28473
ms.openlocfilehash: c2d41ccdb8d70095f00cd18508fdff2b78392696
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2019
ms.locfileid: "69631549"
---
# <a name="parallel-algorithms"></a>Parallele Algorithmen

Die Parallel Patterns Library (PPL) stellt Algorithmen bereit, die gleichzeitig Arbeit an Datensammlungen ausführen. Diese Algorithmen ähneln den von der C++ Standard Bibliothek bereitgestellten Algorithmen.

Die parallelen Algorithmen bestehen aus vorhandenen Funktionen in der Concurrency Runtime. Beispielsweise verwendet der [parallelcurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) -Algorithmus ein [parallelcurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) -Objekt, um die parallelen Schleifen Iterationen auszuführen. Die `parallel_for` Algorithmen für den Algorithmus funktionieren auf optimale Weise, wenn die verfügbare Anzahl von computeressourcen verfügbar ist.

##  <a name="top"></a> Abschnitte

- [Der parallel_for-Algorithmus](#parallel_for)

- [Der parallel_for_each-Algorithmus](#parallel_for_each)

- [Der parallel_invoke-Algorithmus](#parallel_invoke)

- [Die Algorithmen parallel_transform und parallel_reduce](#parallel_transform_reduce)

    - [Der parallel_transform-Algorithmus](#parallel_transform)

    - [Der parallel_reduce-Algorithmus](#parallel_reduce)

    - [Anpassen von mit VSTU Paralleles Ausführen von Map und Reduce](#map_reduce_example)

- [Partitionierungs Arbeit](#partitions)

- [Parallele Sortierung](#parallel_sorting)

    - [Auswählen eines Sortieralgorithmus](#choose_sort)

##  <a name="parallel_for"></a>Der parallel_for-Algorithmus

Der [parallelcurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) -Algorithmus führt die gleiche Aufgabe wiederholt parallel aus. Jede dieser Aufgaben wird durch einen Iterations Wert parametrisiert. Dieser Algorithmus ist nützlich, wenn Sie über einen Schleifen Text verfügen, der keine Ressourcen zwischen Iterationen dieser Schleife gemeinsam verwendet.

Der `parallel_for` Algorithmus partitioniert Aufgaben auf optimale Weise für die parallele Ausführung. Er verwendet einen Arbeits Übernahme Algorithmus und Bereichs Diebstahl, um diese Partitionen auszugleichen, wenn Arbeits Auslastungen nicht ausgeglichen sind. Wenn eine Schleifen Iteration kooperativ blockiert wird, verteilt die Common Language Runtime den Bereich von Iterationen, der dem aktuellen Thread zugewiesen ist, auf andere Threads oder Prozessoren. Wenn ein Thread einen Bereich von Iterationen abschließt, verteilt die Laufzeit die Arbeit von anderen Threads an diesen Thread. Der `parallel_for` Algorithmus unterstützt auch die Unterstützung von unterstützten *Parallelität*. Wenn eine parallele Schleife eine andere parallele Schleife enthält, koordiniert die Laufzeit die Verarbeitung von Ressourcen zwischen den Schleifen Körpern auf effiziente Weise für die parallele Ausführung.

Der `parallel_for` Algorithmus verfügt über mehrere überladene Versionen. Die erste Version übernimmt einen Startwert, einen Endwert und eine Arbeitsfunktion (einen Lambda-Ausdruck, ein Funktions Objekt oder einen Funktionszeiger). Die zweite Version übernimmt einen Startwert, einen Endwert, einen Wert, mit dem ein Schritt ausgeführt werden soll, und eine Arbeitsfunktion. Die erste Version dieser Funktion verwendet 1 als Schrittwert. Die verbleibenden Versionen nehmen partiierer-Objekte an, mit denen Sie `parallel_for` angeben können, wie Bereiche zwischen Threads partitioniert werden sollen. Partitionierer werden im Abschnitt [Partitionierungs Arbeit](#partitions) in diesem Dokument ausführlicher erläutert.

Sie können viele `for` zu verwendende `parallel_for`Schleifen konvertieren. Der `parallel_for` Algorithmus unterscheidet sich jedoch wie `for` folgt von der-Anweisung:

- Der `parallel_for` Algorithmus`parallel_for` führt die Aufgaben nicht in einer vorab festgelegten Reihenfolge aus.

- Der `parallel_for` Algorithmus unterstützt keine willkürlichen Beendigungs Bedingungen. Der `parallel_for` Algorithmus wird beendet, wenn der aktuelle Wert der Iterations Variablen eins kleiner als `last`ist.

- Der `_Index_type` Typparameter muss ein ganzzahliger Typ sein. Dieser ganzzahlige Typ kann mit oder ohne Vorzeichen signiert werden.

- Die Schleifen Iterationen muss vorwärts sein. Der `parallel_for` Algorithmus löst eine Ausnahme vom Typ [Std:: Invalid_argument](../../standard-library/invalid-argument-class.md) aus, `_Step` wenn der-Parameter kleiner als 1 ist.

- Der Mechanismus für die Ausnahmebehandlung für `parallel_for` den Algorithmus unterscheidet sich von `for` dem einer-Schleife. Wenn mehrere Ausnahmen gleichzeitig in einem parallelen Schleifen Text auftreten, gibt die Laufzeit nur eine der Ausnahmen an den Thread weiter, der `parallel_for`aufgerufen hat. Wenn eine Schleifen Iterations Ausnahme eine Ausnahme auslöst, wird die gesamte Schleife von der Laufzeit nicht sofort beendet. Stattdessen wird die Schleife in den Zustand "abgebrochen" versetzt, und die Laufzeit verwirft alle Tasks, die noch nicht gestartet wurden. Weitere Informationen zur Ausnahmebehandlung und parallelen Algorithmen finden Sie unter [Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

Obwohl der `parallel_for` Algorithmus keine willkürlichen Beendigungs Bedingungen unterstützt, können Sie mit dem Abbruch alle Aufgaben beenden. Weitere Informationen zu Abbruch finden Sie unter [Abbruch in der ppl](cancellation-in-the-ppl.md).

> [!NOTE]
>  Die durch den Lastenausgleich und die Unterstützung von Features, wie z. b. einem Abbruch, erzielten Zeit Planungskosten können die Vorteile der parallelen Ausführung des Schleifen Texts nicht überwinden, insbesondere dann, wenn der Schleifen Text relativ klein ist. Sie können diesen mehr Aufwand minimieren, indem Sie einen Partitionierer in der parallelen Schleife verwenden. Weitere Informationen finden Sie unter [Partitionieren von Arbeiten](#partitions) weiter unten in diesem Dokument.

### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die grundlegende Struktur des `parallel_for` Algorithmus. In diesem Beispiel werden alle Werte im Bereich [1, 5] parallel in der Konsole gedruckt.

[!code-cpp[concrt-parallel-for-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_1.cpp)]

Dieses Beispiel erzeugt die folgende Beispielausgabe:

```Output
1 2 4 3 5
```

Da der `parallel_for` Algorithmus für jedes Element parallel agiert, ist die Reihenfolge, in der die Werte in der Konsole gedruckt werden, unterschiedlich.

Ein umfassendes Beispiel, in dem der `parallel_for` -Algorithmus verwendet [wird, finden Sie unter Gewusst wie: Schreiben einer parallel_for-](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)Schleife.

[[Nach oben](#top)]

##  <a name="parallel_for_each"></a>Der parallel_for_each-Algorithmus

Der [parallelcurrency::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) -Algorithmus führt Aufgaben für einen iterativen Container aus, z. b. C++ die, die von der Standard Bibliothek parallel bereitgestellt werden. Er verwendet die gleiche Partitionierungslogik wie der `parallel_for`-Algorithmus.

Der `parallel_for_each` Algorithmus ähnelt dem C++ Standard Bibliothek [Std:: for_each](../../standard-library/algorithm-functions.md#for_each) -Algorithmus, mit dem `parallel_for_each` Unterschied, dass der Algorithmus die Aufgaben gleichzeitig ausführt. Wie andere parallele Algorithmen `parallel_for_each` führt die Aufgaben nicht in einer bestimmten Reihenfolge aus.

Obwohl der `parallel_for_each` Algorithmus sowohl für Forward-Iteratoren als auch für Iteratoren mit zufälligem Zugriff geeignet ist, ist er mit zufälligen zugriffsiteratoren besser geeignet.

### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die grundlegende Struktur des `parallel_for_each` Algorithmus. In diesem Beispiel werden alle Werte in einem [Std:: Array](../../standard-library/array-class-stl.md) -Objekt parallel an die Konsole ausgegeben.

[!code-cpp[concrt-parallel-for-each-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_2.cpp)]

Dieses Beispiel erzeugt die folgende Beispielausgabe:

```Output
4 5 1 2 3
```

Da der `parallel_for_each` Algorithmus für jedes Element parallel agiert, ist die Reihenfolge, in der die Werte in der Konsole gedruckt werden, unterschiedlich.

Ein umfassendes Beispiel, in dem der `parallel_for_each` -Algorithmus verwendet [wird, finden Sie unter Gewusst wie: Schreiben einer parallel_for_each-](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)Schleife.

[[Nach oben](#top)]

##  <a name="parallel_invoke"></a>Der parallel_invoke-Algorithmus

Der [parallelcurrency::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) -Algorithmus führt parallel eine Reihe von Aufgaben aus. Sie wird erst zurückgegeben, wenn jede Aufgabe abgeschlossen ist. Dieser Algorithmus ist nützlich, wenn Sie mehrere unabhängige Aufgaben gleichzeitig ausführen möchten.

Der `parallel_invoke` Algorithmus verwendet als Parameter eine Reihe von Arbeitsfunktionen (Lambda-Funktionen, Funktions Objekte oder Funktionszeiger). Der `parallel_invoke` Algorithmus ist überladen, um zwischen zwei und zehn Parametern zu übernehmen. Jede Funktion, die Sie an `parallel_invoke` übergeben, muss NULL Parameter annehmen.

Wie andere parallele Algorithmen `parallel_invoke` führt die Aufgaben nicht in einer bestimmten Reihenfolge aus. Das Thema [Aufgaben Parallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md) erläutert, wie `parallel_invoke` sich der Algorithmus auf Aufgaben und Aufgaben Gruppen bezieht.

### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die grundlegende Struktur des `parallel_invoke` Algorithmus. In diesem Beispiel wird die `twice` -Funktion gleichzeitig für drei lokale Variablen aufgerufen, und das Ergebnis wird in der Konsole ausgegeben.

[!code-cpp[concrt-parallel-invoke-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_3.cpp)]

Dieses Beispiel erzeugt die folgende Ausgabe:

```Output
108 11.2 HelloHello
```

Umfassende Beispiele, in denen der `parallel_invoke` -Algorithmus verwendet [wird, finden Sie unter Gewusst wie: Verwenden Sie parallel_invoke, um eine parallele Sortier](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md) Routine [zu schreiben und Folgendes zu tun: Verwenden Sie parallel_invoke, um parallele](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)Vorgänge auszuführen.

[[Nach oben](#top)]

##  <a name="parallel_transform_reduce"></a>Die Algorithmen parallel_transform und parallel_reduce

Die Algorithmen "Parallelität [::p arallel_transform](reference/concurrency-namespace-functions.md#parallel_transform) " und "Parallelität [::p arallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce) " sind C++ parallele Versionen der Standard Bibliotheks Algorithmen " [Std:: Transform](../../standard-library/algorithm-functions.md#transform) " und " [Std:: akkumul"](../../standard-library/numeric-functions.md#accumulate). Die Concurrency Runtime Versionen Verhalten sich wie C++ die Standard Bibliotheksversionen, mit dem Unterschied, dass die Reihenfolge der Vorgänge nicht bestimmt wird, da Sie parallel ausgeführt werden. Verwenden Sie diese Algorithmen, wenn Sie mit einer Menge arbeiten, die groß genug ist, um Leistungs-und Skalierbarkeits Vorteile von der parallelen Verarbeitung zu erhalten.

> [!IMPORTANT]
>  Die `parallel_transform` Algorithmen `parallel_reduce` und unterstützen nur zufällige Zugriffe, bidirektionale und Forward-Iteratoren, da diese Iteratoren stabile Speicheradressen liefern. Außerdem müssen diese Iteratoren nicht-`const` l-Werte liefern.

###  <a name="parallel_transform"></a>Der parallel_transform-Algorithmus

Sie können den `parallel transform` -Algorithmus verwenden, um viele datenparallelisierungsvorgänge auszuführen. Sie haben unter anderem folgende Möglichkeiten:

- Passen Sie die Helligkeit eines Bilds an, und führen Sie andere Bild Verarbeitungsvorgänge aus.

- Addieren Sie das Punktprodukt zwischen zwei Vektoren, und führen Sie andere numerische Berechnungen für Vektoren durch.

- Ausführen der 3D-Ray-Ablauf Verfolgung, wobei jede Iterationen auf ein Pixel verweist, das gerendert werden muss.

Das folgende Beispiel zeigt die grundlegende Struktur, die verwendet wird, `parallel_transform` um den-Algorithmus aufzurufen. In diesem Beispiel werden die einzelnen Elemente eines Std::[Vector](../../standard-library/vector-class.md) -Objekts auf zwei Arten negiert. Die erste Methode verwendet einen Lambda-Ausdruck. Die zweite Methode verwendet " [Std:: Negate](../../standard-library/negate-struct.md)", das von " [Std:: Unary_function](../../standard-library/unary-function-struct.md)" abgeleitet wird.

[!code-cpp[concrt-basic-parallel-transform#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_4.cpp)]

> [!WARNING]
>  Dieses Beispiel veranschaulicht die grundlegende Verwendung `parallel_transform`von. Da die Arbeitsfunktion keine große Menge an Arbeit ausführt, wird in diesem Beispiel kein erheblicher Leistungszuwachs erwartet.

Der `parallel_transform` Algorithmus verfügt über zwei über Ladungen. Die erste Überladung nimmt einen Eingabebereich und eine unäre Funktion an. Bei der unären Funktion kann es sich um einen Lambda-Ausdruck handeln, der ein Argument, ein Funktions Objekt oder einen `unary_function`Typ annimmt, der von abgeleitet wird. Die zweite Überladung nimmt zwei Eingabe Bereiche und eine binäre Funktion auf. Bei der binären Funktion kann es sich um einen Lambda Ausdruck handeln, der zwei Argumente annimmt, ein Funktions Objekt oder einen Typ, der von [Std:: binary_function](../../standard-library/binary-function-struct.md)abgeleitet wird. Diese Unterschiede werden im folgenden Beispiel veranschaulicht.

[!code-cpp[concrt-parallel-transform-vectors#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_5.cpp)]

> [!IMPORTANT]
>  Der Iterator, den Sie für die Ausgabe von `parallel_transform` angeben, muss den eingabeiterator vollständig überlappen oder sich überhaupt nicht überlappen. Das Verhalten dieses Algorithmus ist nicht angegeben, wenn sich die Eingabe-und ausgabeiteratoren teilweise überlappen.

###  <a name="parallel_reduce"></a>Der parallel_reduce-Algorithmus

Der `parallel_reduce` Algorithmus ist nützlich, wenn Sie über eine Abfolge von Vorgängen verfügen, die der assoziativen Eigenschaft entsprechen. (Für diesen Algorithmus ist die kommutativ-Eigenschaft nicht erforderlich.) Im folgenden finden Sie einige der Vorgänge, die Sie mit `parallel_reduce`ausführen können:

- Multiplizieren von Sequenz von Matrizen, um eine Matrix zu entwickeln.

- Multiplizieren Sie einen Vektor mit einer Sequenz von Matrizen, um einen Vektor zu entwickeln.

- Berechnen der Länge einer Sequenz von Zeichen folgen.

- Kombinieren Sie eine Liste von Elementen, z. b. Zeichen folgen, in einem Element.

Im folgenden grundlegenden Beispiel wird gezeigt, wie `parallel_reduce` der-Algorithmus verwendet wird, um eine Sequenz von Zeichen folgen in einer Zeichenfolge zu kombinieren Wie bei den Beispielen für `parallel_transform`werden Leistungssteigerungen in diesem einfachen Beispiel nicht erwartet.

[!code-cpp[concrt-basic-parallel-reduce#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_6.cpp)]

In vielen Fällen können Sie sich `parallel_reduce` als Kurzform für die Verwendung `parallel_for_each` des Algorithmus zusammen mit der Klasse "parallelcurrency [:: combinable](../../parallel/concrt/reference/combinable-class.md) " vorstellen.

###  <a name="map_reduce_example"></a>Beispiel Paralleles Ausführen von Map und Reduce

Ein Zuordnungs Vorgang wendet eine Funktion auf jeden Wert in einer Sequenz an. Ein *Reduzierungs* Vorgang kombiniert die Elemente einer Sequenz zu einem Wert. Zum Ausführen von Zuordnungs-und Reduzierungs Vorgängen können Sie die C++ Standard Bibliothek " [Std:: Transform](../../standard-library/algorithm-functions.md#transform) " und " [Std:: akkumul"](../../standard-library/numeric-functions.md#accumulate) verwenden. Allerdings können Sie für viele Probleme den- `parallel_transform` Algorithmus verwenden, um den Zuordnungs Vorgang parallel auszuführen, und der `parallel_reduce` -Algorithmus führt den Reduzierungs Vorgang parallel aus.

Im folgenden Beispiel wird die Zeit verglichen, die benötigt wird, um die Summe von Primzahlen serialisiert und parallel zu berechnen. Die Map-Phase wandelt nicht-primwerte in 0 um, und die Reduzierungs Phase fasst die Werte zusammen.

[!code-cpp[concrt-parallel-map-reduce-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_7.cpp)]

Ein weiteres Beispiel, in dem eine Karte durchlaufen und der Vorgang gleich [zeitig reduziert wird, finden Sie unter Gewusst wie: Paralleles](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)Ausführen von Map-und Reduce-Vorgängen.

[[Nach oben](#top)]

##  <a name="partitions"></a>Partitionierungs Arbeit

Um einen Vorgang für eine Datenquelle zu parallelisieren, besteht ein wesentlicher Schritt darin, die Quelle in mehrere Abschnitte zu *Partitionieren* , auf die gleichzeitig durch mehrere Threads zugegriffen werden kann. Ein Partitionierer gibt an, wie ein paralleler Algorithmus Bereiche zwischen Threads Partitionieren soll. Wie bereits in diesem Dokument erläutert wurde, verwendet die ppl einen standardmäßigen Partitionierungs Mechanismus, der eine anfängliche Arbeitsauslastung erstellt und dann einen Arbeits Übernahme Algorithmus und Bereichs Diebstahl verwendet, um diese Partitionen auszugleichen, wenn Arbeits Auslastungen nicht ausgeglichen sind. Wenn z. b. eine Schleifen Iteration einen Bereich von Iterationen abschließt, verteilt die Runtime die Arbeit von anderen Threads an diesen Thread neu. In einigen Szenarien möchten Sie jedoch möglicherweise einen anderen Partitionierungs Mechanismus angeben, der besser für Ihr Problem geeignet ist.

Die `parallel_for`Algorithmen `parallel_for_each`, `_Partitioner`und `parallel_transform` bieten überladene Versionen, die einen zusätzlichen Parameter,, verwenden. Dieser Parameter definiert den Partitionierungstyp, der die Arbeit dividiert. Hier sind die Arten von partitionierern, die von der ppl definiert werden:

[concurrency::affinity_partitioner](../../parallel/concrt/reference/affinity-partitioner-class.md)<br/>
Dividiert den Arbeitsaufwand in eine festgelegte Anzahl von Bereichen (in der Regel die Anzahl der Arbeitsthreads, die für die Schleife verfügbar sind). Dieser Partitionierungstyp `static_partitioner`ähnelt, verbessert jedoch die Cache Affinität durch die Art und Weise, wie Bereiche zu Arbeitsthreads zugeordnet werden. Dieser Partitionierungstyp kann die Leistung verbessern, wenn eine Schleife mehrmals über das gleiche DataSet ausgeführt wird (z. b. eine Schleife innerhalb einer Schleife) und die Daten in den Cache passen. Dieser Partitionierer wird nicht vollständig an einem Abbruch teilnehmen. Außerdem verwendet er keine kooperative Blockierungs Semantik und kann daher nicht mit parallelen Schleifen verwendet werden, die eine vorwärts Abhängigkeit aufweisen.

[concurrency::auto_partitioner](../../parallel/concrt/reference/auto-partitioner-class.md)<br/>
Dividiert die Arbeit in eine anfängliche Anzahl von Bereichen (in der Regel die Anzahl der Arbeitsthreads, die für die Schleife verfügbar sind). Die Laufzeit verwendet diesen Typ standardmäßig, wenn Sie keinen überladenen parallelen Algorithmus aufrufen, der `_Partitioner` einen-Parameter annimmt. Jeder Bereich kann in Teilbereiche aufgeteilt werden und ermöglicht so den Lastenausgleich. Wenn ein Arbeitsbereich abgeschlossen ist, verteilt die Laufzeit Teilbereiche der Arbeit von anderen Threads an diesen Thread. Verwenden Sie diesen Partitionierer, wenn ihre Arbeitsauslastung nicht unter eine der anderen Kategorien fällt oder Sie vollständige Unterstützung für Abbruch oder kooperative Blockierung benötigen.

[concurrency::simple_partitioner](../../parallel/concrt/reference/simple-partitioner-class.md)<br/>
Dividiert die Arbeit in Bereiche, sodass jeder Bereich mindestens über die Anzahl der durch die angegebene Segmentgröße angegebenen Iterationen verfügt. Dieser Partitionierungstyp ist am Lastenausgleich beteiligt. die Laufzeit teilt die Bereiche jedoch nicht in Unterbereiche auf. Die Laufzeit überprüft für jeden Worker den Abbruch und führt einen Lastenausgleich durch, `_Chunk_size` nachdem Iterationen beendet wurden.

[concurrency::static_partitioner](../../parallel/concrt/reference/static-partitioner-class.md)<br/>
Dividiert den Arbeitsaufwand in eine festgelegte Anzahl von Bereichen (in der Regel die Anzahl der Arbeitsthreads, die für die Schleife verfügbar sind). Dieser Partitionierungstyp kann die Leistung verbessern, da er keinen Arbeits Diebstahl verwendet und daher weniger Aufwand erfordert. Verwenden Sie diesen Partitionierungstyp, wenn jede Iterationen einer parallelen Schleife ein festes und einheitliches Arbeitsaufwand durchführt und Sie keine Unterstützung für Abbruch oder vorwärts Blockierung benötigen.

> [!WARNING]
>  Die `parallel_for_each` Algorithmen `parallel_transform` und unterstützen nur Container, die zufällige zugriffsiteratoren (z. b. Std::[Vector](../../standard-library/vector-class.md)) für die statischen, einfachen und Affinitäts partiierer verwenden. Die Verwendung von Containern, die bidirektionale und Forward-Iteratoren verwenden, erzeugt einen Kompilierzeitfehler. Der Standard Partitionierer `auto_partitioner`,, unterstützt alle drei iteratortypen.

In der Regel werden diese Partitionierer auf die gleiche Weise verwendet, mit `affinity_partitioner`Ausnahme von. Die meisten partitionierertypen behalten den Zustand nicht bei und werden von der Laufzeit nicht geändert. Daher können Sie diese partiierer-Objekte an der-aufrufssite erstellen, wie im folgenden Beispiel gezeigt.

[!code-cpp[concrt-static-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_8.cpp)]

Sie müssen jedoch ein `affinity_partitioner` Objekt als nicht-`const`, l-Wert-Verweis übergeben, damit der Algorithmus den Zustand für zukünftige Schleifen speichern kann. Das folgende Beispiel zeigt eine grundlegende Anwendung, die denselben Vorgang für ein DataSet mehrmals parallel ausführt. Die Verwendung von `affinity_partitioner` kann die Leistung verbessern, da das Array wahrscheinlich in den Cache passt.

[!code-cpp[concrt-affinity-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_9.cpp)]

> [!CAUTION]
>  Gehen Sie vorsichtig vor, wenn Sie vorhandenen Code ändern, der von kooperativen Blockierungs `static_partitioner` Semantik zur Verwendung von oder `affinity_partitioner`abhängig ist. Diese Partitionierungstypen verwenden keinen Lastenausgleich oder Bereichs Diebstahl und können daher das Verhalten der Anwendung ändern.

Die beste Möglichkeit, um zu bestimmen, ob ein Partitionierer in einem bestimmten Szenario verwendet werden soll, ist das Experimentieren und Messen, wie lange die Ausführung von Vorgängen unter repräsentativen Lasten und Computerkonfigurationen dauert. Die statische Partitionierung könnte z.B. möglicherweise auf einem Mehrkerncomputer mit nur wenigen Kernen für erhebliche Beschleunigung sorgen, doch bei Computern mit relativ vielen Kernen zu Verlangsamungen führen.

[[Nach oben](#top)]

##  <a name="parallel_sorting"></a>Parallele Sortierung

Die ppl stellt drei Sortieralgorithmen bereit: Parallelität [::p arallel_sort](reference/concurrency-namespace-functions.md#parallel_sort), Parallelität [::p arallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort)und Parallelität [::p arallel_radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort). Diese Sortieralgorithmen sind nützlich, wenn Sie über ein Dataset verfügen, das von einer parallelen Sortierung profitieren kann. Das parallele Sortieren ist besonders nützlich, wenn Sie über ein großes Dataset verfügen oder wenn Sie einen rechenintensiven Vergleichs Vorgang verwenden, um Ihre Daten zu sortieren. Jeder dieser Algorithmen sortiert Elemente an Ort und Stelle.

Bei `parallel_sort` den `parallel_buffered_sort` Algorithmen und handelt es sich um Vergleichs basierte Algorithmen. Das heißt, dass Sie Elemente nach Wert vergleichen. Der `parallel_sort` Algorithmus hat keine zusätzlichen Arbeitsspeicher Anforderungen und eignet sich für die allgemeine Sortierung. Der `parallel_buffered_sort` Algorithmus kann eine bessere Leistung `parallel_sort`als erzielen, erfordert jedoch O (N)-Speicherplatz.

Der `parallel_radixsort` Algorithmus ist Hash basiert. Das heißt, es werden ganzzahlige Schlüssel zum Sortieren von Elementen verwendet. Mithilfe von Schlüsseln kann dieser Algorithmus das Ziel eines Elements direkt berechnen, anstatt Vergleiche zu verwenden. Ebenso `parallel_buffered_sort`benötigt dieser Algorithmus O (N)-Speicherplatz.

In der folgenden Tabelle sind die wichtigen Eigenschaften der drei parallelen Sortieralgorithmen zusammengefasst.

|Algorithmus|Beschreibung|Sortier Mechanismus|Sortier Stabilität|Arbeitsspeicher Anforderungen|Zeit Komplexität|Iteratorzugriff|
|---------------|-----------------|-----------------------|--------------------|-------------------------|---------------------|---------------------|
|`parallel_sort`|Allgemeine Vergleichs basierte Sortierung.|Vergleichs basiert (aufsteigend)|Lem|None|O ((n/p) log (n/p) + 2n ((P-1)/P))|Random|
|`parallel_buffered_sort`|Schnellere allgemeine Vergleichs basierte Sortierung, die O (N)-Speicherplatz erfordert.|Vergleichs basiert (aufsteigend)|Lem|Erfordert zusätzlichen O (N)-Speicherplatz|O ((n/P) log (n))|Random|
|`parallel_radixsort`|Schlüssel basierte ganzzahlige Sortierung, die O (N)-Speicherplatz erfordert.|Hash basiert|Stabil|Erfordert zusätzlichen O (N)-Speicherplatz|O (N/P)|Random|

In der folgenden Abbildung werden die wichtigen Eigenschaften der drei parallelen Sortierungs Algorithmen grafisch dargestellt.

![Vergleich der Sortieralgorithmen](../../parallel/concrt/media/concrt_parallel_sorting.png "Vergleich der Sortieralgorithmen")

Diese parallelen Sortieralgorithmen folgen den Regeln der Abbruch-und Ausnahmebehandlung. Weitere Informationen zur Abbruch-und Ausnahmebehandlung in der Concurrency Runtime finden Sie unter [Abbrechen paralleler Algorithmen](../../parallel/concrt/cancellation-in-the-ppl.md#algorithms) und [Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

> [!TIP]
>  Diese parallelen Sortieralgorithmen unterstützen Verschiebungs Semantik. Sie können einen Bewegungs Zuweisungs Operator definieren, um die effizientere Ausführung von Austausch Vorgängen zu ermöglichen. Weitere Informationen zur Verschiebungs Semantik und zum Verschiebungs Zuweisungs Operator finden Sie unter [rvalue reference declarator: & &](../../cpp/rvalue-reference-declarator-amp-amp.md)und [Move Constructors and Move Zuweisungs Operators (C++)](../../cpp/move-constructors-and-move-assignment-operators-cpp.md). Wenn Sie keinen Verschiebungs Zuweisungs Operator oder keine Swap-Funktion bereitstellen, verwenden die Sortierungs Algorithmen den Kopierkonstruktor.

Im folgenden grundlegenden Beispiel wird gezeigt, `parallel_sort` wie verwendet wird `vector` , `int` um eine von-Werten zu sortieren. Standardmäßig `parallel_sort` verwendet [Std:: less](../../standard-library/less-struct.md) zum Vergleichen von Werten.

[!code-cpp[concrt-basic-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_10.cpp)]

In diesem Beispiel wird gezeigt, wie eine benutzerdefinierte Vergleichsfunktion bereitgestellt wird. Er verwendet die [Std:: Complex:: Real](../../standard-library/complex-class.md#real) -Methode zum Sortieren von [Std:\<: Complex Double >](../../standard-library/complex-double.md) -Werten in aufsteigender Reihenfolge.

[!code-cpp[concrt-basic-parallel-sort#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_11.cpp)]

In diesem Beispiel wird gezeigt, wie eine Hash Funktion für `parallel_radixsort` den Algorithmus bereitgestellt wird. In diesem Beispiel werden 3D-Punkte sortiert. Die Punkte werden basierend auf ihrer Entfernung von einem Bezugspunkt sortiert.

[!code-cpp[concrt-parallel-sort-points#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_12.cpp)]

Zur Veranschaulichung wird in diesem Beispiel ein relativ kleines DataSet verwendet. Sie können die anfängliche Größe des Vektors erhöhen, um mit Leistungsverbesserungen für größere Datensätze zu experimentieren.

In diesem Beispiel wird ein Lambda-Ausdruck als Hash Funktion verwendet. Sie können auch eine der integrierten Implementierungen der Std::[Hash-Klasse](../../standard-library/hash-class.md) verwenden oder eine eigene Spezialisierung definieren. Sie können auch ein benutzerdefiniertes Hash Funktions Objekt verwenden, wie im folgenden Beispiel gezeigt:

[!code-cpp[concrt-parallel-sort-points#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_13.cpp)]

[!code-cpp[concrt-parallel-sort-points#3](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_14.cpp)]

Die Hash Funktion muss einen ganzzahligen Typ zurückgeben ("[Std:: is_integral:: Value](../../standard-library/is-integral-class.md) " muss " **true**" lauten). Dieser ganzzahlige Typ muss in den `size_t`Typ konvertierbar sein.

###  <a name="choose_sort"></a>Auswählen eines Sortieralgorithmus

In vielen Fällen `parallel_sort` bietet ein optimales Verhältnis von Geschwindigkeit und Speicherleistung. Wenn Sie jedoch die Größe Ihres Datasets erhöhen, wird die Anzahl der verfügbaren Prozessoren oder die Komplexität der Vergleichsfunktion `parallel_buffered_sort` oder `parallel_radixsort` eine bessere Leistung erzielt. Die beste Möglichkeit, um zu bestimmen, welcher Sortieralgorithmus in einem bestimmten Szenario verwendet werden soll, besteht darin, zu experimentieren und zu messen, wie lange es dauert, um typische Daten in repräsentativen Computerkonfigurationen zu sortieren. Beachten Sie bei der Auswahl einer Sortier Strategie die folgenden Richtlinien.

- Die Größe des Datasets. In diesem Dokument enthält ein *kleines* DataSet weniger als 1.000 Elemente, ein *Mittleres* DataSet enthält zwischen 10.000 und 100.000 Elemente, und ein *großes* DataSet enthält mehr als 100.000 Elemente.

- Der Arbeitsaufwand, den die Vergleichsfunktion oder Hash Funktion ausführt.

- Die Menge der verfügbaren Computerressourcen.

- Die Merkmale Ihres Datasets. Beispielsweise kann ein Algorithmus für Daten, die bereits fast sortiert sind, eine gute Leistung haben, aber nicht auch für Daten, die vollständig Unsortiert sind.

- Die Segmentgröße. Das optionale `_Chunk_size` -Argument gibt an, wann der Algorithmus von einer parallelen zu einer seriellem Sortier Implementierung wechselt, wenn die Gesamt Sortierung in kleinere Arbeitseinheiten unterteilt wird. Wenn Sie z. b. 512 angeben, wechselt der Algorithmus in die serielle Implementierung, wenn eine Arbeitseinheit 512 oder weniger Elemente enthält. Eine serielle Implementierung kann die Gesamtleistung verbessern, da dadurch der Aufwand für die parallele Datenverarbeitung entfällt.

Es lohnt sich nicht, ein kleines DataSet parallel zu sortieren, auch wenn Sie über eine große Anzahl verfügbarer computingressourcen verfügen oder die Vergleichsfunktion oder Hash Funktion eine relativ große Menge an Arbeit ausführt. Sie können die [Std:: Sort](../../standard-library/algorithm-functions.md#sort) -Funktion zum Sortieren kleiner Datasets verwenden. (`parallel_sort` und `parallel_buffered_sort` wird aufgerufen`sort` , wenn Sie eine Segmentgröße angeben, die `parallel_buffered_sort` größer ist als das DataSet. müsste jedoch O (N)-Speicherplatz belegen, was aufgrund von Sperr Konflikten oder einer Speicher Belegung zusätzliche Zeit in Anspruch nehmen kann.)

Wenn Sie Speicherplatz einsparen müssen oder für Ihre Speicherzuweisung Sperr Konflikte bestehen, verwenden `parallel_sort` Sie zum Sortieren eines mittelgroßen Datasets. `parallel_sort`erfordert keinen zusätzlichen Speicherplatz. die anderen Algorithmen erfordern O (N)-Speicherplatz.

Verwenden `parallel_buffered_sort` Sie, um mittelgroße Datasets zu sortieren, und, wenn Ihre Anwendung die zusätzliche O (N)-Speicherplatz Anforderung erfüllt. `parallel_buffered_sort`Dies kann besonders nützlich sein, wenn Sie über eine große Anzahl von computeressourcen oder eine teure Vergleichsfunktion oder Hash Funktion verfügen.

Verwenden `parallel_radixsort` Sie, um große Datasets zu sortieren, und, wenn Ihre Anwendung den zusätzlichen O (N)-Speicherplatz benötigt. `parallel_radixsort`Dies kann besonders nützlich sein, wenn der entsprechende Vergleichs Vorgang teurer ist oder wenn beide Vorgänge aufwendig sind.

> [!CAUTION]
>  Zum Implementieren einer guten Hash Funktion müssen Sie den Datasetbereich kennen und angeben, wie die einzelnen Elemente im DataSet in einen entsprechenden Wert ohne Vorzeichen transformiert werden. Da der Hash Vorgang bei Werten ohne Vorzeichen funktioniert, sollten Sie eine andere Sortier Strategie in Erwägung gezogen, wenn nicht signierte Hashwerte nicht erstellt werden können.

Im folgenden Beispiel wird die Leistung von `sort`, `parallel_sort`, `parallel_buffered_sort`und `parallel_radixsort` mit dem gleichen großen Satz zufälliger Daten verglichen.

[!code-cpp[concrt-choosing-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_15.cpp)]

In diesem Beispiel, bei dem davon ausgegangen wird, dass es zulässig ist, O (N)-Speicher `parallel_radixsort` Platz während der Sortierung zuzuordnen, wird in diesem Dataset für diese Computerkonfiguration die beste Leistung erzielt.

[[Nach oben](#top)]

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[Vorgehensweise: Schreiben einer parallel_for-Schleife](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)|Zeigt, wie der- `parallel_for` Algorithmus verwendet wird, um die Matrix Multiplikation auszuführen.|
|[Vorgehensweise: Schreiben einer parallel_for_each-Schleife](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)|Zeigt, wie der `parallel_for_each` -Algorithmus verwendet wird, um die Anzahl von Primzahlen in einem [Std:: Array](../../standard-library/array-class-stl.md) -Objekt parallel zu berechnen.|
|[Vorgehensweise: Verwenden von „parallel_invoke“ zum Schreiben einer Routine für paralleles Sortieren](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)|Erläutert, wie die Leistung des bitonischen Sortieralgorithmus mit dem `parallel_invoke`-Algorithmus verbessert werden.|
|[Vorgehensweise: Ausführen von parallelen Vorgängen mithilfe von „parallel_invoke“](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|Erläutert, wie die Leistung eines Programms mit dem `parallel_invoke`-Algorithmus verbessert werden kann, das mehrere Vorgänge in einer freigegebenen Datenquelle ausführt.|
|[Vorgehensweise: Paralleles Ausführen von Zuordnungs- und Reduzierungsvorgängen](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)|Zeigt, wie der- `parallel_transform` Algorithmus `parallel_reduce` und der-Algorithmus verwendet werden, um einen Map-und Reduce-Vorgang auszuführen, der die Vorkommen von Wörtern in Dateien zählt.|
|[Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Beschreibt die ppl, die ein Imperatives Programmiermodell bereitstellt, das die Skalierbarkeit und Benutzerfreundlichkeit für die Entwicklung gleichzeitiger Anwendungen fördert.|
|[Abbruch in der PPL](cancellation-in-the-ppl.md)|Erläutert die Rolle des Abbruchs in der ppl, das Abbrechen paralleler arbeiten und das ermitteln, wann eine Aufgaben Gruppe abgebrochen wird.|
|[Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|Erläutert die Rolle der Ausnahmebehandlung in der Concurrency Runtime.|

## <a name="reference"></a>Referenz

[parallel_for-Funktion](reference/concurrency-namespace-functions.md#parallel_for)

[Parallel_for_each-Funktion](reference/concurrency-namespace-functions.md#parallel_for_each)

[Parallel_invoke-Funktion](reference/concurrency-namespace-functions.md#parallel_invoke)

[affinity_partitioner-Klasse](../../parallel/concrt/reference/affinity-partitioner-class.md)

[auto_partitioner-Klasse](../../parallel/concrt/reference/auto-partitioner-class.md)

[simple_partitioner-Klasse](../../parallel/concrt/reference/simple-partitioner-class.md)

[static_partitioner-Klasse](../../parallel/concrt/reference/static-partitioner-class.md)

[parallel_sort-Funktion](reference/concurrency-namespace-functions.md#parallel_sort)

[parallel_buffered_sort-Funktion](reference/concurrency-namespace-functions.md#parallel_buffered_sort)

[parallel_radixsort-Funktion](reference/concurrency-namespace-functions.md#parallel_radixsort)
