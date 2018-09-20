---
title: Parallele Container und Objekte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parallel objects
- parallel containers
- concurrent containers
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb06cf0c4e3e5868a0dadeefb30c2e75158d4e32
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433379"
---
# <a name="parallel-containers-and-objects"></a>Parallele Container und Objekte

Die Parallel Patterns Library (PPL) enthält mehrere Container und Objekte, die threadsicheren Zugriff auf ihre Elemente bereitstellen.

Ein *gleichzeitigen Container* parallelitätssichere Zugriff auf die wichtigsten Vorgänge enthält. Die Funktionalität dieser Container ähnelt, die von der C++-Standardbibliothek bereitgestellt werden. Z. B. die [Concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) -Klasse ähnelt der [Std:: vector](../../standard-library/vector-class.md) Klasse, die `concurrent_vector` Klasse können Sie die Elemente parallel anfügen. Verwenden Sie parallele Container bei parallelen Code, der Lese- und Schreibzugriff auf den gleichen Container erforderlich sind.

Ein *gleichzeitige Objekt* zwischen Komponenten gleichzeitig freigegeben wird. Ein Prozess, der den Status der parallele Objekte parallel berechnet erzeugt das gleiche Ergebnis wie ein anderer Prozess, der den gleichen Zustand seriell berechnet. Die [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) Klasse ist ein Beispiel für einen parallelen Objekttyp. Die `combinable` Klasse können Sie die Berechnungen parallel ausführen, und kombinieren Sie diese Berechnungen in einem Endergebnis. Verwenden Sie parallele Objekte aus, wenn Sie einen Synchronisierungsmechanismus, z. B. einen Mutex, sonst, zum Synchronisieren des Zugriffs auf eine freigegebene Variable oder eine Ressource verwenden würden.

##  <a name="top"></a> Abschnitte

In diesem Thema wird beschrieben, die folgenden parallele Container und Objekte im Detail.

Parallele Container:

- [concurrent_vector-Klasse](#ctor)

   - [Concurrent_vector-Unterschiede zwischen "oder" Vektor](#ctor)

   - [Parallelitätssicheren Vorgängen](#ctor)

   - [Ausnahmebehandlung](#ctor)

- [concurrent_queue-Klasse](#queue)

   - [Unterschiede zwischen Concurrent_queue und Warteschlange](#queue-differences)

   - [Parallelitätssicheren Vorgängen](#queue-safety)

   - [Unterstützung für iteratordebugging](#queue-iterators)

- [concurrent_unordered_map-Klasse](#unordered_map)

   - [Concurrent_unordered_map-Unterschiede zwischen und unordered_map-Element](#map-differences)

   - [Parallelitätssicheren Vorgängen](#map-safety)

- [concurrent_unordered_multimap-Klasse](#unordered_multimap)

- [concurrent_unordered_set-Klasse](#unordered_set)

- [concurrent_unordered_multiset-Klasse](#unordered_multiset)

Parallele Objekte:

- [combinable-Klasse](#combinable)

   - [Methoden und Funktionen](#combinable-features)

   - [Beispiele](#combinable-examples)

##  <a name="vector"></a> Concurrent_vector-Klasse

Die [Concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) -Klasse ist eine Sequenzcontainerklasse, die, ebenso wie, die [Std:: vector](../../standard-library/vector-class.md) Klasse, können Sie den Zugriff auf die Elemente nach dem Zufallsprinzip. Die `concurrent_vector` Klasse aktiviert parallelitätssichere Anfügen und Zugreifen auf Elemente Vorgänge. Fügen Sie Vorgänge nicht ungültig, vorhandenen Zeiger oder Iteratoren. Iterator sind Zugriff und Durchlauf auch nebenläufigkeitssicher.

###  <a name="vector-differences"></a> Concurrent_vector-Unterschiede zwischen "oder" Vektor

Die `concurrent_vector` -Klasse gleicht der `vector` Klasse. Die Komplexität der anfügen, Elementzugriff und Iteratorzugriff sind für eine `concurrent_vector` Objekt entsprechen denen für eine `vector` Objekt. Die folgenden Punkte veranschaulichen, wo `concurrent_vector` unterscheidet sich von `vector`:

- Anfügen, Elementzugriff, Iteratorzugriff und Iteratordurchläufe sind auf eine `concurrent_vector` Objekt sind nebenläufigkeitssicher.

- Sie können Elemente hinzufügen, nur bis zum Ende einer `concurrent_vector` Objekt. Die `concurrent_vector` -Klasse keinen der `insert` Methode.

- Ein `concurrent_vector` Objekt verwendet keine [move-Semantik](../../cpp/rvalue-reference-declarator-amp-amp.md) Wenn Sie an diesen angefügt.

- Die `concurrent_vector` -Klasse keinen der `erase` oder `pop_back` Methoden. Wie bei `vector`, verwenden die [löschen](reference/concurrent-vector-class.md#clear) -Methode entfernt alle Elemente aus einer `concurrent_vector` Objekt.

- Die `concurrent_vector` Klasse speichert keine seiner Elemente nacheinander im Arbeitsspeicher. Aus diesem Grund können keine der `concurrent_vector` Klasse in der Hinsicht, dass Sie ein Array verwenden können. Beispielsweise für eine Variable namens `v` des Typs `concurrent_vector`, den Ausdruck `&v[0]+2` nicht definiertem Verhalten führt.

- Die `concurrent_vector` -Klasse definiert die [Grow_by](reference/concurrent-vector-class.md#grow_by) und [Grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least) Methoden. Diese Methoden ähneln die [Ändern der Größe](reference/concurrent-vector-class.md#resize) -Methode, außer dass sie parallelitätssichere sind.

- Ein `concurrent_vector` -Objekts werden nicht die Elemente verschoben, wenn Sie an diesen angefügt oder ändern Sie die Größe. Dadurch können vorhandene Zeiger und Iteratoren, die während der gleichzeitigen Vorgänge gültig bleibt.

- Die Laufzeit definiert keine spezielle Version des `concurrent_vector` für Typ `bool`.

###  <a name="vector-safety"></a> Parallelitätssicheren Vorgängen

Alle Methoden, die Anfügen an oder zum Erhöhen der Größe einer `concurrent_vector` Objekt, oder der Zugriff auf ein Element in eine `concurrent_vector` Objekt, das parallelitätssicher. Die Ausnahme von dieser Regel wird die `resize` Methode.

Die folgende Tabelle zeigt die allgemeine `concurrent_vector` Methoden und Operatoren, die Parallelität sicher sind.

||||
|-|-|-|

|[am](reference/concurrent-vector-class.md#at)|[End](reference/concurrent-vector-class.md#end)|[Operator&#91;&#93;](reference/concurrent-vector-class.md#operator_at)||[ Begin](reference/concurrent-vector-class.md#begin)|[Front](reference/concurrent-vector-class.md#front)|[Push_back](reference/concurrent-vector-class.md#push_back)||[ wieder](reference/concurrent-vector-class.md#back)|[Grow_by](reference/concurrent-vector-class.md#grow_by)|[Rbegin](reference/concurrent-vector-class.md#rbegin)||[ Kapazität](reference/concurrent-vector-class.md#capacity)|[Grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)|[rend](reference/concurrent-vector-class.md#rend)||[ leere](reference/concurrent-vector-class.md#empty)|[Max_size](reference/concurrent-vector-class.md#max_size)|[Größe](reference/concurrent-vector-class.md#size)|

Vorgänge, die die Laufzeit für die Kompatibilität mit der C++-Standardbibliothek, z. B. bereitstellt `reserve`, sind nicht nebenläufigkeitssicher. Die folgende Tabelle zeigt die allgemeinen Methoden und Operatoren, die nicht parallelitätssicher sind.

|||
|-|-|

|[Weisen Sie](reference/concurrent-vector-class.md#assign)|[reservieren](reference/concurrent-vector-class.md#reserve)||[ Deaktivieren Sie](reference/concurrent-vector-class.md#clear)|[Größe](reference/concurrent-vector-class.md#resize)||[ Operator =](reference/concurrent-vector-class.md#operator_eq)|[Shrink_to_fit](reference/concurrent-vector-class.md#shrink_to_fit)|

Vorgänge, die den Wert von vorhandenen Elementen zu ändern, sind nicht nebenläufigkeitssicher. Verwenden Sie z. B. ein Synchronisierungsobjekt, das eine [Reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) Objekt, das Synchronisieren gleichzeitiger Lese- und Schreibvorgänge mit dem gleichen Data-Element. Weitere Informationen zu Synchronisierungsobjekte, finden Sie unter [Synchronisierungsdatenstrukturen](../../parallel/concrt/synchronization-data-structures.md).

Beim Konvertieren von vorhandenen Codes, der verwendet `vector` verwenden `concurrent_vector`, gleichzeitige Vorgängen können dazu führen, dass das Verhalten Ihrer Anwendung ändern. Betrachten Sie beispielsweise das folgende Programm, der gleichzeitig zwei Aufgaben durchführt eine `concurrent_vector` Objekt. Der erste Task fügt zusätzliche Elemente an ein `concurrent_vector` Objekt. Der zweite Task berechnet die Summe aller Elemente im selben Objekt.

[!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]

Obwohl die `end` Methode ist nebenläufigkeitssicher, ein gleichzeitiger Aufruf der [Push_back](reference/concurrent-vector-class.md#push_back) Methode bewirkt, dass den Wert, der von zurückgegeben wird `end` ändern. Die Anzahl der Elemente, die der Iterator durchläuft ist unbestimmt. Daher kann dieses Programm ein anderes Ergebnis jedes Mal erzeugen, die Sie ausgeführt werden.

###  <a name="vector-exceptions"></a> Ausnahmebehandlung

Wenn ein Vorgang Wachstum oder Zuweisung der Status der eine Ausnahme auslöst, die `concurrent_vector` Objekt ungültig wird. Das Verhalten einer `concurrent_vector` -Objekt, das in einem ungültigen Zustand befindet, ist nicht definiert, sofern nicht anders angegeben. Allerdings frei der Destruktor immer den Speicher, den das Objekt belegt, selbst wenn das Objekt in einem ungültigen Zustand.

Der Datentyp, der die Elemente des Vektors, `T`, muss die folgenden Anforderungen erfüllen. Andernfalls das Verhalten der `concurrent_vector` Klasse ist nicht definiert.

- Der Destruktor dürfen keine auslösen.

- Wenn der Standard- oder Kopierkonstruktors auslöst, der Destruktor darf nicht deklariert werden mithilfe der `virtual` -Schlüsselwort, und er müssen ordnungsgemäß mit 0 (null) initialisierten Arbeitsspeicher funktionieren.

[[Nach oben](#top)]

##  <a name="queue"></a> Concurrent_queue-Klasse

Die [Concurrency:: concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) Klasse, wie die [Std:: Queue](../../standard-library/queue-class.md) Klasse, können Sie den Zugriff auf ihre Front- und back-Elemente. Die `concurrent_queue` Klasse aktiviert parallelitätssichere in die Warteschlange eingereiht und dequeue-Vorgänge. Die `concurrent_queue` Klasse bietet auch Unterstützung für iteratordebugging, die nicht parallelitätssicher ist.

###  <a name="queue-differences"></a> Unterschiede zwischen Concurrent_queue und Warteschlange

Die `concurrent_queue` -Klasse gleicht der `queue` Klasse. Die folgenden Punkte veranschaulichen, wo `concurrent_queue` unterscheidet sich von `queue`:

- In die Warteschlange eingereiht und dequeue-Vorgänge auf einer `concurrent_queue` Objekt sind nebenläufigkeitssicher.

- Die `concurrent_queue` -Klasse bietet Unterstützung für iteratordebugging, die nicht parallelitätssicher ist.

- Die `concurrent_queue` -Klasse keinen der `front` oder `pop` Methoden. Die `concurrent_queue` Klasse ersetzt diese Methoden durch die Definition der [Try_pop](reference/concurrent-queue-class.md#try_pop) Methode.

- Die `concurrent_queue` -Klasse keinen der `back` Methode. Aus diesem Grund können nicht Sie am Ende der Warteschlange verweisen.

- Die `concurrent_queue` -Klasse stellt die [Unsafe_size](reference/concurrent-queue-class.md#unsafe_size) -Methode anstelle der `size` Methode. Die `unsafe_size` Methode ist nicht nebenläufigkeitssicher.

###  <a name="queue-safety"></a> Parallelitätssicheren Vorgängen

Alle Methoden für enqueue- oder dequeue-Vorgänge ein `concurrent_queue` Objekt sind nebenläufigkeitssicher.

Die folgende Tabelle zeigt die allgemeine `concurrent_queue` Methoden und Operatoren, die Parallelität sicher sind.

|||
|-|-|
|[empty](reference/concurrent-queue-class.md#empty)|[push](reference/concurrent-queue-class.md#push)|
|[get_allocator](reference/concurrent-queue-class.md#get_allocator)|[try_pop](reference/concurrent-queue-class.md#try_pop)|

Obwohl die `empty` Methode ist nebenläufigkeitssicher, ein gleichzeitiger Vorgang kann dazu führen, dass die Warteschlange vergrößert oder verkleinert werden, bevor Sie die `empty` Methodenrückgabe.

Die folgende Tabelle zeigt die allgemeinen Methoden und Operatoren, die nicht parallelitätssicher sind.

|||
|-|-|
|[clear](reference/concurrent-queue-class.md#clear)|[unsafe_end](reference/concurrent-queue-class.md#unsafe_end)|
|[unsafe_begin](reference/concurrent-queue-class.md#unsafe_begin)|[unsafe_size](reference/concurrent-queue-class.md#unsafe_size)|

###  <a name="queue-iterators"></a> Unterstützung für iteratordebugging

Die `concurrent_queue` enthält Iteratoren, die nicht nebenläufigkeitssicher. Es wird empfohlen, dass Sie diese Iteratoren verwenden für das Debuggen vorgesehen.

Ein `concurrent_queue` Iterator durchläuft die Elemente nur vorwärts. Die folgende Tabelle zeigt den Operatoren, dass jeder Iterator unterstützt.

|Operator|Beschreibung|
|--------------|-----------------|
|`operator++`|Wechselt zum nächsten Element in der Warteschlange. Dieser Operator wird überladen, um sowohl Präinkrement- und Postinkrement-Semantik bereitzustellen.|
|`operator*`|Ruft einen Verweis auf das aktuelle Element ab.|
|`operator->`|Ruft einen Zeiger auf das aktuelle Element ab.|

[[Nach oben](#top)]

##  <a name="unordered_map"></a> Concurrent_unordered_map-Klasse

Die [Concurrency:: concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) -Klasse ist ein assoziativer Container-Klasse, die genau wie die [Std:: unordered_map](../../standard-library/unordered-map-class.md) Klasse, das eine Elementsequenz variabler Länge Sequenz von Elementen des Typs steuert[Std:: Pair\<const Key, Ty >](../../standard-library/pair-structure.md). Stellen Sie sich eine nicht geordnete Zuordnung als ein Wörterbuch, das Sie das Suchen nach Werten nach Schlüssel oder ein Schlüssel-Wert-Paar hinzu hinzufügen können. Diese Klasse ist hilfreich, wenn Sie über mehrere Threads oder Tasks, die gleichzeitig Zugriff auf einen gemeinsamen Container, in diese einfügen oder aktualisieren verfügen.

Das folgende Beispiel zeigt die grundlegende Struktur für die Verwendung von `concurrent_unordered_map`. In diesem Beispiel fügt die Zeichen im Bereich ["a", "i"]. Da die Reihenfolge der Vorgänge nicht festgelegt ist, ist der endgültige Wert für jeden Schlüssel auch unbestimmt. Allerdings ist es sicher ist, Einfügevorgänge parallel auszuführen.

[!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]

Ein Beispiel für die Verwendung `concurrent_unordered_map` um eine Zuordnungs- und Betrieb parallel zu reduzieren, finden Sie unter [Vorgehensweise: auszuführen Map und Vorgänge zu reduzieren, parallel](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).

###  <a name="map-differences"></a> Concurrent_unordered_map-Unterschiede zwischen und unordered_map-Element

Die `concurrent_unordered_map` -Klasse gleicht der `unordered_map` Klasse. Die folgenden Punkte veranschaulichen, wo `concurrent_unordered_map` unterscheidet sich von `unordered_map`:

- Die `erase`, `bucket`, `bucket_count`, und `bucket_size` Methoden werden mit dem Namen `unsafe_erase`, `unsafe_bucket`, `unsafe_bucket_count`, und `unsafe_bucket_size`bzw. Die `unsafe_` Benennungskonvention gibt an, dass diese Methoden nicht nebenläufigkeitssicher. Weitere Informationen zu parallelitätssicherheit, finden Sie unter [parallelitätssicheren Vorgängen](#map-safety).

- INSERT-Vorgänge werden keine vorhandenen Zeiger oder Iteratoren ungültig werden, und ändern sie die Reihenfolge der Elemente, die in der Zuordnung bereits vorhanden. Einfügen und Traversieren Vorgänge gleichzeitig auftreten können.

- `concurrent_unordered_map` unterstützt das Weiterleiten von Iteration nur.

- Einfügen von nicht für ungültig erklären oder aktualisieren Sie die Iteratoren, die von zurückgegeben werden `equal_range`. Einfügen, kann bis zum Ende des Bereichs ungleichen Elemente anfügen. Die Begin-Iterator verweist auf ein Element gleich.

Um zu verhindern, dass keine Methode der Deadlock `concurrent_unordered_map` sperrt, wenn er die Speicherbelegungsfunktion, Hashfunktionen oder anderen benutzerdefinierten Code aufruft. Darüber hinaus müssen Sie sicherstellen, dass die Hash-Funktion immer gleich Schlüssel auf den gleichen Wert ausgewertet. Die beste Hashfunktionen verteilen Sie Schlüssel gleichmäßig auf den Speicherplatz der Hash-Code.

###  <a name="map-safety"></a> Parallelitätssicheren Vorgängen

Die `concurrent_unordered_map` Klasse aktiviert parallelitätssichere einfügen und Elementzugriff Vorgänge. INSERT-Vorgänge werden keine vorhandenen Zeiger oder Iteratoren ungültig werden. Iterator sind Zugriff und Durchlauf auch nebenläufigkeitssicher. Die folgende Tabelle zeigt die häufigsten verwendeten `concurrent_unordered_map` Methoden und Operatoren, die Parallelität sicher sind.

|||||
|-|-|-|-|
|[at](reference/concurrent-unordered-map-class.md#at)|`count`|`find`|[key_eq](reference/concurrent-unordered-map-class.md#key_eq)|
|`begin`|`empty`|`get_allocator`|`max_size`|
|`cbegin`|`end`|`hash_function`|[operator&#91;&#93;](reference/concurrent-unordered-map-class.md#operator_at)|
|`cend`|`equal_range`|[insert](reference/concurrent-unordered-map-class.md#insert)|`size`|

Obwohl die `count` Methode sicher von gleichzeitig ausgeführten Threads aufgerufen werden kann, verschiedene Threads können unterschiedliche Ergebnisse erhalten, wenn es sich bei gleichzeitig ein neuer Wert in den Container eingefügt wird.

Die folgende Tabelle zeigt die häufig verwendeten Methoden und Operatoren, die nicht parallelitätssicher sind.

||||
|-|-|-|
|`clear`|`max_load_factor`|`rehash`|
|`load_factor`|[operator=](reference/concurrent-unordered-map-class.md#operator_eq)

Neben diesen Methoden können eine beliebige Methode beginnt mit `unsafe_` ist auch nicht nebenläufigkeitssicher.

[[Nach oben](#top)]

##  <a name="unordered_multimap"></a> Concurrent_unordered_multimap-Klasse

Die [concurrency::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) -Klasse gleicht der `concurrent_unordered_map` Klasse mit dem Unterschied, dass für mehrere Werte den gleichen Schlüssel zuordnen können. Es unterscheidet sich auch von `concurrent_unordered_map` auf folgende Weise:

- Die [concurrent_unordered_multimap:: Insert](reference/concurrent-unordered-multimap-class.md#insert) Methode gibt einen Iterator anstelle von `std::pair<iterator, bool>`.

- Die `concurrent_unordered_multimap` -Klasse keinen `operator[]` noch die `at` Methode.

Das folgende Beispiel zeigt die grundlegende Struktur für die Verwendung von `concurrent_unordered_multimap`. In diesem Beispiel fügt die Zeichen im Bereich ["a", "i"]. `concurrent_unordered_multimap` können einen Schlüssel, um mehrere Werte zu erhalten.

[!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]

[[Nach oben](#top)]

##  <a name="unordered_set"></a> Concurrent_unordered_set-Klasse

Die [concurrency::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) -Klasse gleicht der `concurrent_unordered_map` Klasse mit dem Unterschied, dass er Werte anstelle von Schlüssel-Wert-Paare verwaltet. Die `concurrent_unordered_set` -Klasse keinen `operator[]` noch die `at` Methode.

Das folgende Beispiel zeigt die grundlegende Struktur für die Verwendung von `concurrent_unordered_set`. In diesem Beispiel fügt Zeichenwerten enthalten, die im Bereich ["a", "i"]. Es ist sicher Einfügevorgänge parallel ausführen.

[!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]

[[Nach oben](#top)]

##  <a name="unordered_multiset"></a> Concurrent_unordered_multiset-Klasse

Die [concurrency::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) -Klasse gleicht der `concurrent_unordered_set` Klasse mit dem Unterschied, dass es doppelte Werte ermöglicht. Es unterscheidet sich auch von `concurrent_unordered_set` auf folgende Weise:

- Die [concurrent_unordered_multiset:: Insert](reference/concurrent-unordered-multiset-class.md#insert) Methode gibt einen Iterator anstelle von `std::pair<iterator, bool>`.

- Die `concurrent_unordered_multiset` -Klasse keinen `operator[]` noch die `at` Methode.

Das folgende Beispiel zeigt die grundlegende Struktur für die Verwendung von `concurrent_unordered_multiset`. In diesem Beispiel fügt Zeichenwerten enthalten, die im Bereich ["a", "i"]. `concurrent_unordered_multiset` ermöglicht einen Wert, der mehrfach vorkommen.

[!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]

[[Nach oben](#top)]

##  <a name="combinable"></a> combinable-Klasse

Die [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) -Klasse stellt wiederverwendbare, Thread-lokalen Speicher, in dem Sie differenzierte Berechnungen ausführen, und klicken Sie dann in einem Endergebnis zusammenführen kann. Stellen Sie sich ein `combinable`-Objekt wie eine Reduktionsvariable vor.

Die `combinable` Klasse ist nützlich, wenn Sie eine Ressource verfügen, die von mehreren Threads oder Aufgaben gemeinsam genutzt wird. Die `combinable` Klasse können Sie die freigegebenen Zustand vermeiden können, durch die Bereitstellung von Zugriff auf freigegebene Ressourcen in einer Weise sperrfrei. Aus diesem Grund: Diese Klasse stellt eine Alternative zur Verwendung eines Synchronisierungsmechanismus, z. B. einen Mutex, zum Synchronisieren des Zugriffs auf freigegebene Daten aus mehreren Threads.

###  <a name="combinable-features"></a> Methoden und Funktionen

Die folgende Tabelle zeigt einige der wichtigen Methoden von der `combinable` Klasse. Weitere Informationen zu allen dem `combinable` -Klassenmethoden, finden Sie unter [combinable-Klasse](../../parallel/concrt/reference/combinable-class.md).

|Methode|Beschreibung|
|------------|-----------------|
|[local](reference/combinable-class.md#local)|Ruft einen Verweis auf die lokale Variable, die den Kontext des aktuellen Threads zugeordnet ist.|
|[clear](reference/combinable-class.md#clear)|Entfernt alle Thread-lokalen Variablen aus der `combinable` Objekt.|
|[combine](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|Verwendet die Funktion bereitgestellten kombinieren, um einen endgültigen Wert aus der Gruppe alle Thread-lokalen Berechnungen zu generieren.|

Die `combinable` Klasse ist eine Vorlagenklasse, die auf das endgültige Ergebnis des zusammengeführten parametrisiert wird. Wenn Sie den Standard-Konstruktor aufrufen der `T` Vorlagentyp-Parameter müssen einen Standardkonstruktor und einen Kopierkonstruktor. Wenn die `T` Vorlagenparametertyp verfügt nicht über einen Standardkonstruktor, rufen Sie die überladene Version des Konstruktors, die eine Initialisierungsfunktion als Parameter akzeptiert.

Sie können zusätzliche Daten in speichern eine `combinable` Objekt aufzurufen, nachdem Sie die [kombinieren](reference/combinable-class.md#combine) oder [Combine_each](reference/combinable-class.md#combine_each) Methoden. Sie können auch aufrufen, die `combine` und `combine_each` Methoden mehrmals. Wenn kein lokaler Wert in eine `combinable` Objekts ändert, die `combine` und `combine_each` Methoden liefern das gleiche Ergebnis jedes Mal, die sie aufgerufen werden.

###  <a name="combinable-examples"></a> Beispiele

Beispiele zur Verwendung der `combinable` Klasse, finden Sie unter den folgenden Themen:

- [Vorgehensweise: Verbessern der Leistung mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)

- [Vorgehensweise: Kombinieren von Gruppen mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)

[[Nach oben](#top)]

## <a name="related-topics"></a>Verwandte Themen

[Vorgehensweise: Erhöhen der Effizienz mithilfe von parallelen Containern](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br/>
Zeigt, wie Sie mithilfe von parallelen Containern effizient zu speichern und Abrufen von Daten parallel.

[Vorgehensweise: Verbessern der Leistung mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br/>
Zeigt, wie die `combinable` Klasse, um die freigegebenen Zustand vermeiden können, und so die Leistung zu verbessern.

[Vorgehensweise: Kombinieren von Gruppen mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)<br/>
Zeigt, wie eine `combine` Funktion, um die Thread-lokale Daten zusammenzuführen.

[Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
Beschreibt die PPL, die ein obligatorisches Programmiermodell bereitstellt, das Skalierbarkeit und einfache Handhabung beim Entwickeln gleichzeitige Anwendungen fördert.

## <a name="reference"></a>Referenz

[concurrent_vector-Klasse](../../parallel/concrt/reference/concurrent-vector-class.md)

[concurrent_queue-Klasse](../../parallel/concrt/reference/concurrent-queue-class.md)

[concurrent_unordered_map-Klasse](../../parallel/concrt/reference/concurrent-unordered-map-class.md)

[concurrent_unordered_multimap-Klasse](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)

[concurrent_unordered_set-Klasse](../../parallel/concrt/reference/concurrent-unordered-set-class.md)

[concurrent_unordered_multiset-Klasse](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)

[combinable-Klasse](../../parallel/concrt/reference/combinable-class.md)
