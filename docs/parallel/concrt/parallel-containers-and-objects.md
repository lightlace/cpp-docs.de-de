---
title: Parallele Container und Objekte | Microsoft Docs
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
ms.openlocfilehash: 168705c5d7497a0bcbede505760d49cdb63a3762
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="parallel-containers-and-objects"></a>Parallele Container und Objekte
Die Parallel Patterns Library (PPL) enthält mehrere Container und Objekte, die threadsicheren Zugriff auf ihre Elemente bieten.  
  
 Ein *gleichzeitigen Container* parallelitätssicher ist der Zugang zu den wichtigsten Vorgänge. Die Funktionalität dieser Container ähnelt, die von der C++-Standardbibliothek bereitgestellt werden. Z. B. die [Concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) -Klasse ähnelt der [Std:: vector](../../standard-library/vector-class.md) Klasse, außer dass die `concurrent_vector` -Klasse können Sie Elemente gleichzeitig angefügt werden soll. Verwenden Sie parallele Container bei parallelen Code, der Lese- und Schreibzugriff auf den gleichen Container erfordert.  
  
 Ein *gleichzeitige Objekt* für Komponenten gleichzeitig freigegeben wird. Ein Prozess, der den Status eines Objekts gleichzeitige parallel berechnet erzeugt das gleiche Ergebnis wie ein anderer Prozess, der den gleichen Status seriell berechnet. Die [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) Klasse ist ein Beispiel für einen parallelen Objekttyp. Die `combinable` -Klasse können Sie Berechnungen parallel ausführen, und klicken Sie dann diese Berechnungen in einem Endergebnis kombinieren. Verwenden Sie parallele Objekte aus, wenn Sie andernfalls einen Synchronisierungsmechanismus, z. B. einen Mutex, zum Synchronisieren des Zugriffs auf eine freigegebene Variable oder eine Ressource verwenden würden.  
  
##  <a name="top"></a> Abschnitte  
 Dieses Thema beschreibt die folgenden parallele Container und Objekte im Detail beschrieben.  
  
 Parallele Container:  
  
-   [concurrent_vector-Klasse](#ctor)  
  
    -   [Unterschiede zwischen Concurrent_vector und Vektorgrafiken](#ctor)  
  
    -   [Parallelitätssicheren Vorgängen](#ctor)  
  
    -   [Ausnahmesicherheit](#ctor)  
  
-   [concurrent_queue-Klasse](#queue)  
  
    -   [Unterschiede zwischen Concurrent_queue und queue](#queue-differences)  
  
    -   [Parallelitätssicheren Vorgängen](#queue-safety)  
  
    -   [Unterstützung für iteratordebugging](#queue-iterators)  
  
-   [concurrent_unordered_map-Klasse](#unordered_map)  
  
    -   [Unterschiede zwischen Concurrent_unordered_map und "unordered_map"](#map-differences)  
  
    -   [Parallelitätssicheren Vorgängen](#map-safety)  
  
-   [concurrent_unordered_multimap-Klasse](#unordered_multimap)  
  
-   [concurrent_unordered_set-Klasse](#unordered_set)  
  
-   [concurrent_unordered_multiset-Klasse](#unordered_multiset)  
  
 Parallele Objekte:  
  
-   [combinable-Klasse](#combinable)  
  
    -   [Methoden und Funktionen](#combinable-features)  
  
    -   [Beispiele](#combinable-examples)  
  
##  <a name="vector"></a> Concurrent_vector-Klasse  
 Die [Concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) -Klasse ist eine Sequenzcontainerklasse, die ebenso wie die [Std:: vector](../../standard-library/vector-class.md) Klasse, können Sie nach dem Zufallsprinzip seine Elemente zugreifen. Die `concurrent_vector` Klasse aktiviert parallelitätssichere Anfügen und Zugreifen auf Elemente Vorgänge. Anfügen Vorgänge keine vorhandenen Zeiger oder Iteratoren ungültig werden. Iterator-Zugriff und Durchlauf-Vorgänge sind auch parallelitätssicher ist.  
  
###  <a name="vector-differences"></a> Unterschiede zwischen Concurrent_vector und Vektorgrafiken  
 Die `concurrent_vector` -Klasse gleicht der `vector` Klasse. Die Komplexität der anfügen, Elementzugriff und Iteratorzugriff sind für eine `concurrent_vector` Objekt sind die gleichen wie für eine `vector` Objekt. Die folgenden Punkte veranschaulichen, wo `concurrent_vector` unterscheidet sich von `vector`:  
  
-   Anfügen, Elementzugriff, Iteratorzugriff und Iteratordurchläufe sind auf eine `concurrent_vector` Objekt sind parallelitätssicher ist.  
  
-   Sie können Elemente hinzufügen, nur bis zum Ende einer `concurrent_vector` Objekt. Die `concurrent_vector` Klasse bietet keine die `insert` Methode.  
  
-   Ein `concurrent_vector` Objekt verwendet keine [Verschiebesemantik](../../cpp/rvalue-reference-declarator-amp-amp.md) Wenn Sie an diese anfügen.  
  

-   Die `concurrent_vector` Klasse bietet keine die `erase` oder `pop_back` Methoden. Wie bei `vector`, verwenden Sie die [deaktivieren](reference/concurrent-vector-class.md#clear) -Methode entfernt alle Elemente aus einer `concurrent_vector` Objekt.  
  
-   Die `concurrent_vector` Klasse speichern seiner Elemente nicht zusammenhängend im Arbeitsspeicher. Aus diesem Grund können keine der `concurrent_vector` Klasse in den Verfahren, die Sie ein Array verwenden können. Z. B. für eine Variable namens `v` des Typs `concurrent_vector`, den Ausdruck `&v[0]+2` erzeugt nicht definiertem Verhalten.  
  
-   Die `concurrent_vector` Klasse definiert die [Grow_by](reference/concurrent-vector-class.md#grow_by) und [Grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least) Methoden. Diese Methoden ähneln den [Größe](reference/concurrent-vector-class.md#resize) -Methode, außer dass sie nebenläufigkeitssicher sind.  
  
-   Ein `concurrent_vector` Objekt zu seiner Elemente nicht verschieben, wenn Sie angefügt werden soll, oder ihre Größe. Dadurch werden vorhandene Zeiger und Iteratoren bei gleichzeitigen Vorgängen gültig bleibt.  
  
-   Die Common Language Runtime definiert keine spezielle Version des `concurrent_vector` für Typ `bool`.  
  
###  <a name="vector-safety"></a> Parallelitätssicheren Vorgängen  
 Alle Methoden, die angefügt werden soll oder Vergrößern einer `concurrent_vector` -Objekts oder Zugriff auf ein Element in eine `concurrent_vector` -Objekt sind parallelitätssicher ist. Die Ausnahme von dieser Regel wird die `resize` Methode.  
  
 Die folgende Tabelle zeigt die allgemeine `concurrent_vector` Methoden und Operatoren, die parallelitätssicher ist.  
  
||||  
|-|-|-|  

|[am](reference/concurrent-vector-class.md#at)|[End](reference/concurrent-vector-class.md#end)|[Operator&#91;&#93;](reference/concurrent-vector-class.md#operator_at)|  
|[Begin](reference/concurrent-vector-class.md#begin)|[Vorderseite](reference/concurrent-vector-class.md#front)|[Push_back](reference/concurrent-vector-class.md#push_back)|  
|[wieder](reference/concurrent-vector-class.md#back)|[Grow_by](reference/concurrent-vector-class.md#grow_by)|[Rbegin](reference/concurrent-vector-class.md#rbegin)|  
|[Kapazität](reference/concurrent-vector-class.md#capacity)|[Grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)|[rend](reference/concurrent-vector-class.md#rend)|  
|[leere](reference/concurrent-vector-class.md#empty)|[Max_size](reference/concurrent-vector-class.md#max_size)|[Größe](reference/concurrent-vector-class.md#size)|  

  
 Vorgänge, die die Laufzeit für Kompatibilität mit der C++-Standardbibliothek, z. B. enthält `reserve`, sind nicht parallelitätssicher ist. Die folgende Tabelle zeigt die allgemeine Methoden und Operatoren, die nicht parallelitätssicher ist.  
  
|||  
|-|-|  

|[Weisen Sie](reference/concurrent-vector-class.md#assign)|[reservieren](reference/concurrent-vector-class.md#reserve)|  
|[Deaktivieren Sie](reference/concurrent-vector-class.md#clear)|[Größe](reference/concurrent-vector-class.md#resize)|  
|[Operator =](reference/concurrent-vector-class.md#operator_eq)|[Shrink_to_fit](reference/concurrent-vector-class.md#shrink_to_fit)|  
  
 Vorgänge, die den Wert von vorhandenen Elementen ändern, sind nicht parallelitätssicher ist. Verwenden Sie z. B. ein Synchronisierungsobjekt, das eine [Reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) Objekt zum Synchronisieren des gleichzeitigen Lese- und Schreibvorgänge mit der gleichen Data-Element. Weitere Informationen zu Synchronisierungsobjekte, finden Sie unter [Strukturen für Synchronisierungsdaten](../../parallel/concrt/synchronization-data-structures.md).  
  
 Beim Konvertieren von vorhandenen Codes, der verwendet `vector` verwenden `concurrent_vector`, gleichzeitige Vorgänge können dazu führen, dass das Verhalten der Anwendung ändern. Betrachten Sie beispielsweise das folgende Programm, der zwei Aufgaben gleichzeitig auf führt eine `concurrent_vector` Objekt. Der erste Task fügt zusätzliche Elemente ein `concurrent_vector` Objekt. Die zweite Aufgabe berechnet die Summe aller Elemente im selben Objekt.  
  
 [!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]  
  

 Obwohl die `end` Methode ist nebenläufigkeitssicher, ein gleichzeitiger Aufruf der [Push_back](reference/concurrent-vector-class.md#push_back) Methode bewirkt, dass den Wert, der von zurückgegeben wird `end` ändern. Die Anzahl der Elemente, die der Iterator durchläuft ist unbestimmt. Daher kann dieses Programm ein anderes Ergebnis jedes Mal ergeben, die sie ausführen.  
  
###  <a name="vector-exceptions"></a> Ausnahmesicherheit  
 Wenn ein Vorgang Wachstum oder Zuweisung, eine Ausnahme, den Status des auslöst der `concurrent_vector` Objekt ungültig wird. Das Verhalten einer `concurrent_vector` Objekt, das in einem ungültigen Zustand ist nicht definiert, sofern nicht anders angegeben. Allerdings der Destruktor immer gibt den Arbeitsspeicher frei, den das Objekt belegt wird, selbst wenn das Objekt in einem ungültigen Zustand.  
  
 Der Datentyp, der die Vektorelemente `T`, muss die folgenden Anforderungen erfüllen. Andernfalls das Verhalten der `concurrent_vector` Klasse ist nicht definiert.  
  
-   Der Destruktor darf keine auslösen.  
  
-   Wenn der Standard- oder Kopierkonstruktor auslöst, der Destruktor muss nicht deklariert werden mithilfe der `virtual` -Schlüsselwort, und er müssen ordnungsgemäß mit 0 (null) initialisierten Speicher.  
  
 [[Nach oben](#top)]  
  
##  <a name="queue"></a> Concurrent_queue-Klasse  
 Die [Concurrency:: concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) Klasse, ebenso wie die [Std:: Queue](../../standard-library/queue-class.md) Klasse, können Sie den Zugriff auf ihre Front- und back-Elemente. Die `concurrent_queue` -Klasse aktiviert parallelitätssichere enqueue- und dequeue-Vorgänge. Die `concurrent_queue` Klasse bietet auch Unterstützung für iteratordebugging, die nicht parallelitätssicher ist.  
  
###  <a name="queue-differences"></a> Unterschiede zwischen Concurrent_queue und queue  
 Die `concurrent_queue` -Klasse gleicht der `queue` Klasse. Die folgenden Punkte veranschaulichen, wo `concurrent_queue` unterscheidet sich von `queue`:  
  
-   In die Warteschlange einreihen und dequeue-Vorgänge auf einer `concurrent_queue` Objekt sind parallelitätssicher ist.  
  
-   Die `concurrent_queue` Klasse bietet Unterstützung für iteratordebugging, die nicht parallelitätssicher ist.  
  

-   Die `concurrent_queue` Klasse bietet keine die `front` oder `pop` Methoden. Die `concurrent_queue` Klasse ersetzt diese Methoden durch die Definition der [Try_pop](reference/concurrent-queue-class.md#try_pop) Methode.  
  
-   Die `concurrent_queue` Klasse bietet keine die `back` Methode. Sie können nicht aus diesem Grund am Ende der Warteschlange verweisen.  
  
-   Die `concurrent_queue` -Klasse stellt die [Unsafe_size](reference/concurrent-queue-class.md#unsafe_size) -Methode anstelle der `size` Methode. Die `unsafe_size` Methode ist nicht nebenläufigkeitssicher.  

  
###  <a name="queue-safety"></a> Parallelitätssicheren Vorgängen  
 Alle Methoden für enqueue- oder dequeue-Vorgänge ein `concurrent_queue` Objekt sind parallelitätssicher ist.  
  
 Die folgende Tabelle zeigt die allgemeine `concurrent_queue` Methoden und Operatoren, die parallelitätssicher ist.  
  
|||  
|-|-|  
|[empty](reference/concurrent-queue-class.md#empty)|[push](reference/concurrent-queue-class.md#push)|  
|[get_allocator](reference/concurrent-queue-class.md#get_allocator)|[try_pop](reference/concurrent-queue-class.md#try_pop)|  


  
 Obwohl die `empty` Methode ist nebenläufigkeitssicher, ein gleichzeitiger Vorgang kann dazu führen, dass die Warteschlange vergrößert oder verkleinert werden, bevor die `empty` -Methode zurückkehrt.  
  
 Die folgende Tabelle zeigt die allgemeine Methoden und Operatoren, die nicht parallelitätssicher ist.  
  
|||  
|-|-|  
|[clear](reference/concurrent-queue-class.md#clear)|[unsafe_end](reference/concurrent-queue-class.md#unsafe_end)|  
|[unsafe_begin](reference/concurrent-queue-class.md#unsafe_begin)|[unsafe_size](reference/concurrent-queue-class.md#unsafe_size)|  


  
###  <a name="queue-iterators"></a> Unterstützung für iteratordebugging  
 Die `concurrent_queue` enthält Iteratoren, die nicht parallelitätssicher ist. Es wird empfohlen, dass Sie diese Iteratoren, verwenden nur für das Debuggen.  
  
 Ein `concurrent_queue` Iterator durchläuft Elemente nur vorwärts. Die folgende Tabelle zeigt die Operatoren, dass jeder Iterator unterstützt.  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[operator++](http://msdn.microsoft.com/en-us/4cfdd07e-927a-42f8-aaa0-d6881687f413)|Wechselt zum nächsten Element in der Warteschlange. Dieser Operator ist überladen, sodass Präinkrement- und Postinkrement-Semantik bereitstellen.|  
|[operator*](http://msdn.microsoft.com/en-us/a0e671fc-76e6-4fb4-b95c-ced4dd2b2017)|Ruft einen Verweis auf das aktuelle Element ab.|  
|[operator->](http://msdn.microsoft.com/en-us/41fa393d-ae1e-4a38-bb4b-19e8df709ca9)|Ruft einen Zeiger auf das aktuelle Element ab.|  
  
 [[Nach oben](#top)]  
  
##  <a name="unordered_map"></a> Concurrent_unordered_map-Klasse  
 Die [HYPERLINK "file:///C:\\\Users\\\thompet\\\AppData\\\Local\\\Temp\\\DxEditor\\\DduePreview\\\Default \\\798d7037-df37-4310-858b-6f590bbf6ebf\\\HTM\\\html\\\a217b4ac-af2b-4d41-94eb-09a75ee28622 "Concurrency:: concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) Klasse ist ein assoziative Containerklasse, die ebenso wie die [Std:: unordered_map](../../standard-library/unordered-map-class.md) Klasse, eine Elementsequenz variabler Länge Sequenz von Elementen des Typs steuert [Std:: Pair\<const Key, "ty" >](../../standard-library/pair-structure.md). Stellen Sie sich eine nicht geordnete Zuordnung als ein Wörterbuch, die Sie hinzufügen ein Schlüssel / Wert-Paar, oder Suchen nach Werten über Schlüssel. Diese Klasse ist hilfreich, wenn Sie über mehrere Threads oder Aufgaben, die gleichzeitig Zugriff auf einen freigegebenen Container, hinein INSERT- oder update verfügen.  
  
 Im folgende Beispiel wird die grundlegende Struktur für die Verwendung von `concurrent_unordered_map`. Dieses Beispiel fügt die Zeichen im Bereich ["a", "i"]. Da die Reihenfolge der Vorgänge unbestimmt ist, ist der endgültige Wert für jeden Schlüssel auch unbestimmt. Allerdings ist es sicher, parallele Einfügevorgänge.  
  
 [!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]  
  
 Ein Beispiel, verwendet `concurrent_unordered_map` zur führen Sie einer Zuordnung und zur Reduzierung von Vorgang parallel, finden Sie unter [wie: Zuordnung ausführen und Vorgänge zu reduzieren, parallel](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).  
  
###  <a name="map-differences"></a> Unterschiede zwischen Concurrent_unordered_map und "unordered_map"  
 Die `concurrent_unordered_map` -Klasse gleicht der `unordered_map` Klasse. Die folgenden Punkte veranschaulichen, wo `concurrent_unordered_map` unterscheidet sich von `unordered_map`:  
  
-   Die `erase`, `bucket`, `bucket_count`, und `bucket_size` Methoden heißen `unsafe_erase`, `unsafe_bucket`, `unsafe_bucket_count`, und `unsafe_bucket_size`zugeordnet. Die `unsafe_` Benennungskonvention gibt an, dass diese Methoden nicht parallelitätssicher ist. Weitere Informationen zu Parallelität für Sicherheit, finden Sie unter [parallelitätssicheren Vorgängen](#map-safety).  
  
-   INSERT-Vorgänge werden keine vorhandenen Zeiger oder Iteratoren ungültig werden, und ändern sie die Reihenfolge der Elemente, die in der Zuordnung bereits vorhanden sind. Einfügen und durchlaufen Vorgänge gleichzeitig auftreten können.  
  
-   `concurrent_unordered_map` unterstützt die Iteration nur weitergeleitet werden.  
  
-   Einfügung nicht für ungültig zu erklären oder aktualisieren Sie den Iteratoren zurück, die von zurückgegeben werden `equal_range`. Einfügen kann ungleichen Elemente an das Ende des Bereichs anfügen. Die Begin-Iterator verweist auf ein Element gleich.  
  
 Zum Vermeiden von Deadlocks, keine Methode `concurrent_unordered_map` beim Aufrufen der speicherbelegung, Hashfunktionen oder anderen benutzerdefinierten Code eine Sperre. Darüber hinaus müssen Sie sicherstellen, dass die Hash-Funktion immer gleich Schlüssel auf den gleichen Wert ausgewertet wird. Die besten Hashfunktionen verteilen Schlüssel gleichmäßig den Hash Code Speicherplatz.  
  
###  <a name="map-safety"></a> Parallelitätssicheren Vorgängen  
 Die `concurrent_unordered_map` Klasse ermöglicht parallelitätssicheren INSERT- und Elementzugriff Vorgängen. Einfügevorgänge werden keine vorhandenen Zeiger oder Iteratoren ungültig werden. Iterator-Zugriff und Durchlauf-Vorgänge sind auch parallelitätssicher ist. Die folgende Tabelle enthält die häufig verwendeten `concurrent_unordered_map` Methoden und Operatoren, die parallelitätssicher ist.  
  
|||||  
|-|-|-|-|  
|[at](reference/concurrent-unordered-map-class.md#at)|`count`|`find`|[key_eq](reference/concurrent-unordered-map-class.md#key_eq)|  
|`begin`|`empty`|`get_allocator`|`max_size`|  
|`cbegin`|`end`|`hash_function`|[operator&#91;&#93;](reference/concurrent-unordered-map-class.md#operator_at)|  
|`cend`|`equal_range`|[insert](reference/concurrent-unordered-map-class.md#insert)|`size`|  
  
 Obwohl die `count` Methode kann problemlos von gleichzeitig ausgeführten Threads aufgerufen werden, die verschiedenen Threads können unterschiedliche Ergebnisse erhalten, wenn ein neuer Wert gleichzeitig in den Container eingefügt wird.  
  
 Die folgende Tabelle zeigt die häufig verwendeten Methoden und Operatoren, die nicht parallelitätssicher ist.  
  
||||  
|-|-|-|  
|`clear`|`max_load_factor`|`rehash`|  
|`load_factor`|[operator=](reference/concurrent-unordered-map-class.md#operator_eq) 


  
 Neben diesen Methoden können eine beliebige Methode, die mit beginnt `unsafe_` ist auch nicht parallelitätssicher ist.  
  
 [[Nach oben](#top)]  
  
##  <a name="unordered_multimap"></a> Concurrent_unordered_multimap-Klasse  
 Die [concurrency::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) -Klasse gleicht der `concurrent_unordered_map` Klasse mit dem Unterschied, dass für mehrere Werte den gleichen Schlüssel zuordnen können. Es unterscheidet sich auch von `concurrent_unordered_map` auf folgende Weise:  
  
-   Die [concurrent_unordered_multimap:: Insert](reference/concurrent-unordered-multimap-class.md#insert) Methode gibt einen Iterator anstelle von `std::pair<iterator, bool>`.  

  
-   Die `concurrent_unordered_multimap` Klasse bietet keine `operator[]` noch die `at` Methode.  
  
 Im folgende Beispiel wird die grundlegende Struktur für die Verwendung von `concurrent_unordered_multimap`. Dieses Beispiel fügt die Zeichen im Bereich ["a", "i"]. `concurrent_unordered_multimap` ermöglicht es einen Schlüssel, um mehrere Werte haben.  
  
 [!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]  
  
 [[Nach oben](#top)]  
  
##  <a name="unordered_set"></a> Concurrent_unordered_set-Klasse  
 Die [concurrency::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) -Klasse gleicht der `concurrent_unordered_map` Klasse, außer dass es Werte anstelle von Schlüssel / Wert-Paare verwaltet. Die `concurrent_unordered_set` Klasse bietet keine `operator[]` noch die `at` Methode.  
  
 Im folgende Beispiel wird die grundlegende Struktur für die Verwendung von `concurrent_unordered_set`. In diesem Beispiel fügt Zeichenwerten enthalten, die im Bereich ["a", "i"]. Sie können ruhig Einfügevorgänge parallel ausgeführt.  
  
 [!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]  
  
 [[Nach oben](#top)]  
  
##  <a name="unordered_multiset"></a> Concurrent_unordered_multiset-Klasse  
 Die [concurrency::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) -Klasse gleicht der `concurrent_unordered_set` Klasse, außer dass sie für doppelte Werte zulässt. Es unterscheidet sich auch von `concurrent_unordered_set` auf folgende Weise:  
  

-   Die [concurrent_unordered_multiset:: Insert](reference/concurrent-unordered-multiset-class.md#insert) Methode gibt einen Iterator anstelle von `std::pair<iterator, bool>`.  

  
-   Die `concurrent_unordered_multiset` Klasse bietet keine `operator[]` noch die `at` Methode.  
  
 Im folgende Beispiel wird die grundlegende Struktur für die Verwendung von `concurrent_unordered_multiset`. In diesem Beispiel fügt Zeichenwerten enthalten, die im Bereich ["a", "i"]. `concurrent_unordered_multiset` ermöglicht einen Wert, der mehrfach vorkommen.  
  
 [!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]  
  
 [[Nach oben](#top)]  
  
##  <a name="combinable"></a> combinable-Klasse  
 Die [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) Klasse bietet wiederverwendbaren lokalen Threadspeicher, mit dem Sie differenzierte Berechnungen ausführen, und klicken Sie dann zu einem Endergebnis zusammenführen. Stellen Sie sich ein `combinable`-Objekt wie eine Reduktionsvariable vor.  
  
 Die `combinable` Klasse ist nützlich, wenn Sie eine Ressource verfügen, die von mehreren Threads oder Aufgaben gemeinsam genutzt wird. Die `combinable` Klasse können Sie die gemeinsam verwendete Zustände und bietet Zugriff auf freigegebene Ressourcen in einer Weise sperrenfreie beseitigen. Diese Klasse stellt deshalb eine Alternative zur Verwendung eines Synchronisierungsmechanismus, z. B. einen Mutex, zum Synchronisieren des Zugriffs auf freigegebene Daten von mehreren Threads bereit.  
  
###  <a name="combinable-features"></a> Methoden und Funktionen  
 Die folgende Tabelle zeigt einige der wichtigen Methoden von der `combinable` Klasse. Weitere Informationen zu allen dem `combinable` -Klassenmethoden, finden Sie unter [combinable-Klasse](../../parallel/concrt/reference/combinable-class.md).  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[local](reference/combinable-class.md#local)|Ruft einen Verweis auf die lokale Variable, die den Kontext des aktuellen Threads zugeordnet ist.|  
|[clear](reference/combinable-class.md#clear)|Entfernt alle threadlokale Variablen aus der `combinable` Objekt.|  
|[combine](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|Verwendet die bereitgestellte Combine-Funktion um einen endgültigen Wert aus dem Satz von allen lokalen Berechnungen zu generieren.|  
  
 Die `combinable` -Klasse ist eine Vorlagenklasse, die auf das Endergebnis zusammengeführte parametrisiert wird. Wenn Sie den Standardkonstruktor Aufrufen der `T` Vorlagentyp-Parameter muss einen Standardkonstruktor und einen Kopierkonstruktor haben. Wenn die `T` Vorlagentyp-Parameter verfügt nicht über einen Standardkonstruktor, rufen Sie die überladene Version des Konstruktors, die eine Initialisierungsfunktion als Parameter akzeptiert.  
  
 Können Sie zusätzliche Daten in Speichern einer `combinable` Objekt nach dem Aufruf der [kombinieren](reference/combinable-class.md#combine) oder [Combine_each](reference/combinable-class.md#combine_each) Methoden. Sie können auch aufrufen, die `combine` und `combine_each` Methoden mehrmals. Wenn kein lokaler Wert in einer `combinable` Objekts ändert, die `combine` und `combine_each` Methoden liefern das gleiche Ergebnis jedes Mal, die sie aufgerufen werden.  
  
###  <a name="combinable-examples"></a> Beispiele  
 Beispiele zur Verwendung der `combinable` Klasse, finden Sie unter den folgenden Themen:  
  
-   [Vorgehensweise: Verbessern der Leistung mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
  
-   [Vorgehensweise: Kombinieren von Gruppen mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
  
 [[Nach oben](#top)]  
  
## <a name="related-topics"></a>Verwandte Themen  
 [Vorgehensweise: Erhöhen der Effizienz mithilfe von parallelen Containern](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)  
 Zeigt, wie mithilfe von parallelen Containern effizienter zu speichern und Zugreifen auf Daten parallel.  
  
 [Vorgehensweise: Verbessern der Leistung mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
 Zeigt, wie die `combinable` -Klasse zum freigegebenen Zustand vermeiden können, und so die Leistung zu verbessern.  
  
 [Vorgehensweise: Kombinieren von Gruppen mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
 Zeigt, wie eine `combine` Funktion um threadlokalen Daten zusammenzuführen.  
  
 [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)  
 Beschreibt die PPL vor, die ein obligatorisches Programmiermodell bereitstellt, das Skalierbarkeit und Einfachheit der Verwendung beim Entwickeln gleichzeitige Anwendungen fördert.  
  
## <a name="reference"></a>Referenz  
 [concurrent_vector-Klasse](../../parallel/concrt/reference/concurrent-vector-class.md)  
  
 [concurrent_queue-Klasse](../../parallel/concrt/reference/concurrent-queue-class.md)  
  
 [concurrent_unordered_map-Klasse](../../parallel/concrt/reference/concurrent-unordered-map-class.md)  
  
 [concurrent_unordered_multimap-Klasse](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)  
  
 [concurrent_unordered_set-Klasse](../../parallel/concrt/reference/concurrent-unordered-set-class.md)  
  
 [concurrent_unordered_multiset-Klasse](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)  
  
 [combinable-Klasse](../../parallel/concrt/reference/combinable-class.md)
