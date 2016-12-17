---
title: "Parallele Container und Objekte"
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
helpviewer_keywords: 
  - "Parallele Objekte"
  - "Parallele Container"
  - "Parallele Container"
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
caps.latest.revision: 34
caps.handback.revision: "34"
ms.author: "mblome"
manager: "ghogen"
---
# Parallele Container und Objekte
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Parallel Patterns Library (PPL) enthält mehrere Container und Objekte, die threadsicheren Zugriff auf ihre Elemente bieten.  
  
 Ein *parallele Container* parallelitätssicher, die Zugriff auf die wichtigsten Vorgänge. Die Funktionalität dieser Container ähnelt denen, die von der Standardvorlagenbibliothek (STL) bereitgestellt werden. Z. B. die [Concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) -Klasse ähnelt der [Std:: vector](vector%20Class.md) Klasse, außer dass die `concurrent_vector` -Klasse können Sie die Elemente parallel angefügt. Verwenden Sie parallele Container bei parallelen Code, der Lese- und Schreibzugriff auf den gleichen Container erfordert.  
  
 Ein *Parallele Objekte* zwischen Komponenten gleichzeitig freigegeben wird. Ein Prozess, der den Zustand eines Objekts gleichzeitigen parallel berechnet erzeugt das gleiche Ergebnis wie ein anderer Prozess, der den gleichen Status seriell berechnet. Die [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) Klasse ist ein Beispiel für einen parallelen Objekttyp. Die `combinable` -Klasse können Sie die Berechnungen parallel auszuführen, und kombinieren Sie diese Berechnungen in einem Endergebnis. Verwenden Sie parallele Objekte, wenn Sie andernfalls einen Synchronisierungsmechanismus, z. B. einen Mutex, zum Synchronisieren des Zugriffs auf eine freigegebene Variable oder Ressource verwenden würden.  
  
##  <a name="a-nametopa-sections"></a><a name="top"></a> Abschnitte  
 Dieses Thema beschreibt die folgenden parallelen Container und Objekte im Detail beschrieben.  
  
 Parallele Container:  
  
-   [Concurrent_vector-Klasse](#vector)  
  
    -   [Unterschiede zwischen Concurrent_vector und vector](#vector-differences)  
  
    -   [Parallelitätssichere Vorgänge](#vector-safety)  
  
    -   [Ausnahmebehandlung](#vector-exceptions)  
  
-   [Concurrent_queue-Klasse](#queue)  
  
    -   [Unterschiede zwischen Concurrent_queue und queue](#queue-differences)  
  
    -   [Parallelitätssichere Vorgänge](#queue-safety)  
  
    -   [Unterstützung für iteratordebugging](#queue-iterators)  
  
-   [Concurrent_unordered_map-Klasse](#unordered_map)  
  
    -   [Unterschiede zwischen Concurrent_unordered_map und unordered_map-Element](#map-differences)  
  
    -   [Parallelitätssichere Vorgänge](#map-safety)  
  
-   [Concurrent_unordered_multimap-Klasse](#unordered_multimap)  
  
-   [Concurrent_unordered_set-Klasse](#unordered_set)  
  
-   [Concurrent_unordered_multiset-Klasse](#unordered_multiset)  
  
 Parallele Objekte:  
  
-   [combinable-Klasse](#combinable)  
  
    -   [Methoden und Funktionen](#combinable-features)  
  
    -   [Beispiele für](#combinable-examples)  
  
##  <a name="a-namevectora-concurrentvector-class"></a><a name="vector"></a> Concurrent_vector-Klasse  
 Die [Concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) -Klasse ist eine Sequenzcontainerklasse, die genau wie die [Std:: vector](vector%20Class.md) Klasse, können Sie die Elemente nach dem Zufallsprinzip zugreifen. Die `concurrent_vector` -Klasse ermöglicht parallelitätssichere Anfügen und Zugreifen auf Elemente Vorgänge. Fügen Sie Vorgänge werden keine vorhandene Zeiger und Iteratoren ungültig. Iterator-Zugriff und parallelitätssichere Vorgänge sind ebenfalls parallelitätssicher ist.  
  
###  <a name="a-namevector-differencesa-differences-between-concurrentvector-and-vector"></a><a name="vector-differences"></a> Unterschiede zwischen Concurrent_vector und vector  
 Die `concurrent_vector` -Klasse gleicht der `vector` Klasse. Die Komplexität der anfügen, Elementzugriff und Iteratorzugriff sind für ein `concurrent_vector` Objekt sind die gleichen wie für eine `vector` Objekt. Die folgenden Punkte veranschaulichen, wo `concurrent_vector` unterscheidet sich von `vector`:  
  
-   Anfügen, Elementzugriff, Iteratorzugriff und Iteratordurchläufe sind auf ein `concurrent_vector` -Objekt sind parallelitätssicher.  
  
-   Sie können Elemente hinzufügen, nur bis zum Ende einer `concurrent_vector` Objekt. Die `concurrent_vector` -Klasse keinen der `insert` Methode.  
  
-   Ein `concurrent_vector` Objekt verwendet keine [Verschiebesemantik](../../cpp/rvalue-reference-declarator-amp-amp.md) Wenn Sie anfügen.  
  
-   Die `concurrent_vector` -Klasse keinen der `erase` oder `pop_back` Methoden. Wie bei `vector`, verwenden Sie die [deaktivieren](../Topic/concurrent_vector::clear%20Method.md) -Methode entfernt alle Elemente aus einer `concurrent_vector` Objekt.  
  
-   Die `concurrent_vector` Klasse speichern seiner Elemente nicht zusammenhängend im Arbeitsspeicher. Aus diesem Grund können keine der `concurrent_vector` -Klasse in der Weise, dass Sie ein Array verwenden können. Z. B. für eine Variable namens `v` vom Typ `concurrent_vector`, den Ausdruck `&v[0]+2` erzeugt nicht definiertes Verhalten.  
  
-   Die `concurrent_vector` -Klasse definiert die [Grow_by](../Topic/concurrent_vector::grow_by%20Method.md) und [Grow_to_at_least](../Topic/concurrent_vector::grow_to_at_least%20Method.md) Methoden. Diese Methoden entsprechen die [Größe](../Topic/concurrent_vector::resize%20Method.md) -Methode, sind aber parallelitätssicher ist.  
  
-   Ein `concurrent_vector` Objekt zu seiner Elemente nicht verschieben, beim Anfügen oder die Größe ändern. Dadurch können vorhandene Zeiger und Iteratoren bei gleichzeitigen Vorgängen gültig bleibt.  
  
-   Die Common Language Runtime definiert keine spezielle Version des `concurrent_vector` für Typ `bool`.  
  
###  <a name="a-namevector-safetya-concurrency-safe-operations"></a><a name="vector-safety"></a> Parallelitätssichere Vorgänge  
 Alle Methoden, die angefügt oder vergrößern Sie ein `concurrent_vector` -Objekt oder Zugriff auf ein Element in ein `concurrent_vector` Objekt, sind parallelitätssicher. Die Ausnahme von dieser Regel ist die `resize` Methode.  
  
 Die folgende Tabelle zeigt die allgemeine `concurrent_vector` Methoden und Operatoren, die sicher sind.  
  
||||  
|-|-|-|  
|[am](../Topic/concurrent_vector::at%20Method.md)|[Ende](../Topic/concurrent_vector::end%20Method.md)|[Operator &#91; &#93;](../Topic/concurrent_vector::operatorOperator.md)|  
|[beginnen](../Topic/concurrent_vector::begin%20Method.md)|[Vorderseite](../Topic/concurrent_vector::front%20Method.md)|[push_back](../Topic/concurrent_vector::push_back%20Method.md)|  
|[Zurück](../Topic/concurrent_vector::back%20Method.md)|[grow_by](../Topic/concurrent_vector::grow_by%20Method.md)|[rbegin](../Topic/concurrent_vector::rbegin%20Method.md)|  
|[Kapazität](../Topic/concurrent_vector::capacity%20Method.md)|[grow_to_at_least](../Topic/concurrent_vector::grow_to_at_least%20Method.md)|[REND](../Topic/concurrent_vector::rend%20Method.md)|  
|[leere](../Topic/concurrent_vector::empty%20Method.md)|[max_size](../Topic/concurrent_vector::max_size%20Method.md)|[Größe](../Topic/concurrent_vector::size%20Method.md)|  
  
 Vorgänge, die die Laufzeit für die Kompatibilität mit der STL, z. B. bereitstellt `reserve`, sind nicht parallelitätssicher ist. Die folgende Tabelle zeigt die gängigen Methoden und Operatoren, die nicht parallelitätssicher sind.  
  
|||  
|-|-|  
|[Zuweisen](../Topic/concurrent_vector::assign%20Method.md)|[Reservieren](../Topic/concurrent_vector::reserve%20Method.md)|  
|[Deaktivieren](../Topic/concurrent_vector::clear%20Method.md)|[Ändern der Größe](../Topic/concurrent_vector::resize%20Method.md)|  
|[Operator =](../Topic/concurrent_vector::operator=%20Operator.md)|[shrink_to_fit](../Topic/concurrent_vector::shrink_to_fit%20Method.md)|  
  
 Vorgänge, die den Wert des vorhandenen Elemente zu ändern, sind nicht parallelitätssicher ist. Verwenden Sie ein Synchronisierungsobjekt, wie z. B. eine [Reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) -Objekt zum Synchronisieren des gleichzeitigen Lese- und Schreibvorgänge für das gleiche Datenelement. Weitere Informationen zu Synchronisierungsobjekten finden Sie unter [Strukturen für Synchronisierungsdaten](../../parallel/concrt/synchronization-data-structures.md).  
  
 Beim Konvertieren von vorhandenen Codes, der verwendet `vector` verwenden `concurrent_vector`, gleichzeitige Vorgänge können dazu führen, dass das Verhalten der Anwendung ändern. Betrachten Sie beispielsweise das folgende Programm, das gleichzeitig zwei Aufgaben durchführt ein `concurrent_vector` Objekt. Die erste Aufgabe fügt zusätzliche Elemente ein `concurrent_vector` Objekt. Die zweite Aufgabe berechnet die Summe aller Elemente im selben Objekt.  
  
 [!CODE [concrt-vector-safety#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-vector-safety#1)]  
  
 Obwohl die `end` Methode ist nebenläufigkeitssicher, ein gleichzeitiger Aufruf der [Push_back](../Topic/concurrent_vector::push_back%20Method.md) Methode bewirkt, dass den Wert, der von zurückgegebene `end` ändern. Die Anzahl der Elemente, die der Iterator durchläuft, ist unbestimmt. Daher kann dieses Programm ein anderes Ergebnis jedes Mal erzeugen, die Sie es ausführen.  
  
###  <a name="a-namevector-exceptionsa-exception-safety"></a><a name="vector-exceptions"></a> Ausnahmebehandlung  
 Wenn ein Vorgang Wachstum oder Zuweisung der Status der eine Ausnahme auslöst, die `concurrent_vector` Objekt ungültig wird. Das Verhalten einer `concurrent_vector` Objekt, das in einem ungültigen Zustand ist nicht definiert, wenn nicht anders angegeben. Allerdings frei der Destruktor immer den Speicher, den das Objekt belegt wird, selbst wenn das Objekt in einem ungültigen Zustand befindet.  
  
 Der Datentyp der Vektorelemente `T`, müssen die folgenden Kriterien erfüllen. Andernfalls das Verhalten der `concurrent_vector` Klasse ist nicht definiert.  
  
-   Der Destruktor darf nicht auslösen.  
  
-   Wenn der Standard- oder Kopierkonstruktor auslöst, der Destruktor darf nicht deklariert werden mithilfe der `virtual` -Schlüsselwort und müssen ordnungsgemäß mit 0 initialisiert.  
  
 [[Nach oben](#top)]  
  
##  <a name="a-namequeuea-concurrentqueue-class"></a><a name="queue"></a> Concurrent_queue-Klasse  
 Die [Concurrency:: concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) Klasse, wie die [Std:: Queue](../../standard-library/queue-class.md) Klasse, können Sie den Zugriff auf ihre Front- und back-Elemente. Die `concurrent_queue` -Klasse ermöglicht parallelitätssichere enqueue- und dequeue-Vorgänge. Die `concurrent_queue` Klasse bietet auch Unterstützung für iteratordebugging, die nicht parallelitätssicher ist.  
  
###  <a name="a-namequeue-differencesa-differences-between-concurrentqueue-and-queue"></a><a name="queue-differences"></a> Unterschiede zwischen Concurrent_queue und queue  
 Die `concurrent_queue` -Klasse gleicht der `queue` Klasse. Die folgenden Punkte veranschaulichen, wo `concurrent_queue` unterscheidet sich von `queue`:  
  
-   Enqueue und dequeue-Vorgänge für ein `concurrent_queue` -Objekt sind parallelitätssicher.  
  
-   Die `concurrent_queue` -Klasse unterstützt Iterator, der nicht parallelitätssicher ist.  
  
-   Die `concurrent_queue` -Klasse keinen der `front` oder `pop` Methoden. Die `concurrent_queue` -Klasse ersetzt diese Methoden durch die Definition der [Try_pop](../Topic/concurrent_queue::try_pop%20Method.md) Methode.  
  
-   Die `concurrent_queue` -Klasse keinen der `back` Methode. Daher können Sie nicht am Ende der Warteschlange verweisen.  
  
-   Die `concurrent_queue` -Klasse stellt die [Unsafe_size](../Topic/concurrent_queue::unsafe_size%20Method.md) -Methode anstelle der `size` Methode. Die `unsafe_size` Methode ist nicht parallelitätssicher ist.  
  
###  <a name="a-namequeue-safetya-concurrency-safe-operations"></a><a name="queue-safety"></a> Parallelitätssichere Vorgänge  
 Alle Methoden für enqueue- und dequeue-Vorgänge ein `concurrent_queue` -Objekt sind parallelitätssicher.  
  
 Die folgende Tabelle zeigt die allgemeine `concurrent_queue` Methoden und Operatoren, die sicher sind.  
  
|||  
|-|-|  
|[leere](../Topic/concurrent_queue::empty%20Method.md)|[Push](../Topic/concurrent_queue::push%20Method.md)|  
|[get_allocator](../Topic/concurrent_queue::get_allocator%20Method.md)|[try_pop](../Topic/concurrent_queue::try_pop%20Method.md)|  
  
 Obwohl die `empty` -Methode parallelitätssicher ist, ein gleichzeitiger Vorgang kann dazu führen, dass die Warteschlange vergrößert oder verkleinert wird, bevor die `empty` -Methode zurückgegeben.  
  
 Die folgende Tabelle zeigt die gängigen Methoden und Operatoren, die nicht parallelitätssicher sind.  
  
|||  
|-|-|  
|[Deaktivieren](../Topic/concurrent_queue::clear%20Method.md)|[unsafe_end](../Topic/concurrent_queue::unsafe_end%20Method.md)|  
|[unsafe_begin](../Topic/concurrent_queue::unsafe_begin%20Method.md)|[unsafe_size](../Topic/concurrent_queue::unsafe_size%20Method.md)|  
  
###  <a name="a-namequeue-iteratorsa-iterator-support"></a><a name="queue-iterators"></a> Unterstützung für iteratordebugging  
 Die `concurrent_queue` bietet Iteratoren, die nicht parallelitätssicher sind. Es wird empfohlen, dass Sie diese Iteratoren nur zum Debuggen verwenden.  
  
 Ein `concurrent_queue` Iterator durchläuft die Elemente nur vorwärts. In der folgenden Tabelle wird gezeigt, die Operatoren, dass jeder Iterator unterstützt.  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[Operator ++](assetId:///4cfdd07e-927a-42f8-aaa0-d6881687f413)|Wechselt zum nächsten Element in der Warteschlange. Dieser Operator wird überladen, um Präinkrement- und Postinkrement-Semantik bereitstellen.|  
|[Operator *](assetId:///a0e671fc-76e6-4fb4-b95c-ced4dd2b2017)|Ruft einen Verweis auf das aktuelle Element ab.|  
|[Operator ->](assetId:///41fa393d-ae1e-4a38-bb4b-19e8df709ca9)|Ruft einen Zeiger auf das aktuelle Element ab.|  
  
 [[Nach oben](#top)]  
  
##  <a name="a-nameunorderedmapa-concurrentunorderedmap-class"></a><a name="unordered_map"></a> Concurrent_unordered_map-Klasse  
 Die [HYPERLINK "file:///C:\\\Users\\\thompet\\\AppData\\\Local\\\Temp\\\DxEditor\\\DduePreview\\\Default\\\798d7037-df37-4310-858b-6f590bbf6ebf\\\HTM\\\html\\\a217b4ac-af2b-4d41-94eb-09a75ee28622" concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) Klasse ist ein assoziativer Container-Klasse, die genau wie die [Std:: unordered_map](../../standard-library/unordered-map-class.md) Klasse, steuert ein variabler Länge Abfolge von Elementen des Typs [Std:: Pair \< const Key, Ty >](../../standard-library/pair-structure.md). Stellen Sie sich eine nicht geordnete Zuordnung als ein Wörterbuch, die ein Schlüssel-Wert-Paar zum Hinzufügen oder einen Wert von Key suchen können. Diese Klasse ist hilfreich, wenn Sie mehrere Threads oder Aufgaben, die gleichzeitig Zugriff auf einen freigegebenen Container, in sie einfügen oder aktualisieren, haben.  
  
 Im folgende Beispiel wird die grundlegende Struktur für die Verwendung von `concurrent_unordered_map`. Dieses Beispiel fügt die Zeichen im Bereich ['a', ' i']. Da die Reihenfolge der Vorgänge unbestimmt ist, ist der endgültige Wert für jeden Schlüssel auch unbestimmt. Allerdings ist es sicher ist, die Einfügevorgänge parallel.  
  
 [!CODE [concrt-unordered-map-structure#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-unordered-map-structure#1)]  
  
 Ein Beispiel für die `concurrent_unordered_map` eine Karte und reduce-Vorgang parallel, finden Sie unter [Gewusst wie: Ausführen-Zuordnung und Reduzierung Vorgänge parallel](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).  
  
###  <a name="a-namemap-differencesa-differences-between-concurrentunorderedmap-and-unorderedmap"></a><a name="map-differences"></a> Unterschiede zwischen Concurrent_unordered_map und unordered_map-Element  
 Die `concurrent_unordered_map` -Klasse gleicht der `unordered_map` Klasse. Die folgenden Punkte veranschaulichen, wo `concurrent_unordered_map` unterscheidet sich von `unordered_map`:  
  
-   Die `erase`, `bucket`, `bucket_count`, und `bucket_size` Methoden mit dem Namen `unsafe_erase`, `unsafe_bucket`, `unsafe_bucket_count`, und `unsafe_bucket_size`, bzw.. Die `unsafe_` Benennungskonvention gibt an, dass diese Methoden nicht parallelitätssicher ist. Weitere Informationen über Parallelität Sicherheit finden Sie unter [parallelitätssicheren Vorgängen](#map-safety).  
  
-   Einfügevorgänge werden keine vorhandene Zeiger und Iteratoren ungültig, und ändern sie die Reihenfolge der Elemente, die in der Zuordnung bereits vorhanden sind. Einfügen und durchlaufen Vorgänge gleichzeitig auftreten können.  
  
-   `concurrent_unordered_map` unterstützt das Weiterleiten nur Iteration.  
  
-   Einfügung ungültig oder aktualisieren Sie die Iteratoren, die von zurückgegeben werden `equal_range`. Einfügen kann ungleichen Elemente am Ende des Bereichs anfügen. Die Begin-Iterator zeigt auf ein Element gleich.  
  
 Zum Vermeiden von Deadlocks keine Methode zum `concurrent_unordered_map` eine Sperre, die beim Aufrufen der Speicherbelegungsfunktion, Hashfunktionen oder anderen benutzerdefinierten Code. Darüber hinaus müssen Sie sicherstellen, dass die Hash-Funktion immer gleich Schlüssel auf den gleichen Wert ausgewertet wird. Die beste Hashfunktionen werden Schlüssel gleichmäßig auf die Codebereich Hash verteilen.  
  
###  <a name="a-namemap-safetya-concurrency-safe-operations"></a><a name="map-safety"></a> Parallelitätssichere Vorgänge  
 Die `concurrent_unordered_map` -Klasse parallelitätssichere einfügen und Element-Access-Vorgänge ermöglicht. Einfügevorgänge werden keine vorhandene Zeiger und Iteratoren ungültig. Iterator-Zugriff und parallelitätssichere Vorgänge sind ebenfalls parallelitätssicher ist. Die folgende Tabelle enthält häufig verwendete `concurrent_unordered_map` Methoden und Operatoren, die sicher sind.  
  
|||||  
|-|-|-|-|  
|[am](../Topic/concurrent_unordered_map::at%20Method.md)|`count`|`find`|[key_eq](../Topic/concurrent_unordered_map::key_eq%20Method.md)|  
|`begin`|`empty`|`get_allocator`|`max_size`|  
|`cbegin`|`end`|`hash_function`|[Operator &#91; &#93;](../Topic/concurrent_unordered_map::operatorOperator.md)|  
|`cend`|`equal_range`|[Einfügen](../Topic/concurrent_unordered_map::insert%20Method.md)|`size`|  
  
 Obwohl die `count` Methode kann problemlos von gleichzeitig ausgeführten Threads aufgerufen werden, andere Threads können unterschiedliche Ergebnisse erhalten, wird ein neuer Wert gleichzeitig in den Container eingefügt.  
  
 Die folgende Tabelle zeigt die häufig verwendeten Methoden und Operatoren, die nicht parallelitätssicher sind.  
  
||||  
|-|-|-|  
|`clear`|`max_load_factor`|`rehash`|  
|`load_factor`|[Operator =](../Topic/concurrent_unordered_map::operator=%20Operator.md)|[Swap](../Topic/concurrent_unordered_map::swap%20Method.md)|  
  
 Zusätzlich zu diesen Methoden können eine beliebige Methode beginnt mit `unsafe_` ist auch nicht parallelitätssicher ist.  
  
 [[Nach oben](#top)]  
  
##  <a name="a-nameunorderedmultimapa-concurrentunorderedmultimap-class"></a><a name="unordered_multimap"></a> Concurrent_unordered_multimap-Klasse  
 Die [concurrency::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) -Klasse gleicht der `concurrent_unordered_map` Klasse mehrere Werte den gleichen Schlüssel zuordnen können. Sie unterscheidet sich auch von `concurrent_unordered_map` auf folgende Weise:  
  
-   Die [concurrent_unordered_multimap:: Insert](../Topic/concurrent_unordered_multimap::insert%20Method.md) Methode gibt einen Iterator anstelle von `std::pair<iterator, bool>`.  
  
-   Die `concurrent_unordered_multimap` -Klasse keinen `operator[]` noch die `at` Methode.  
  
 Im folgende Beispiel wird die grundlegende Struktur für die Verwendung von `concurrent_unordered_multimap`. Dieses Beispiel fügt die Zeichen im Bereich ['a', ' i']. `concurrent_unordered_multimap` können eine Taste, um mehrere Werte verfügen.  
  
 [!CODE [concrt-unordered-multimap-structure#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-unordered-multimap-structure#1)]  
  
 [[Nach oben](#top)]  
  
##  <a name="a-nameunorderedseta-concurrentunorderedset-class"></a><a name="unordered_set"></a> Concurrent_unordered_set-Klasse  
 Die [concurrency::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) -Klasse gleicht der `concurrent_unordered_map` Klasse, außer dass es Werte anstelle von Schlüssel-Wert-Paare verwaltet. Die `concurrent_unordered_set` -Klasse keinen `operator[]` noch die `at` Methode.  
  
 Im folgende Beispiel wird die grundlegende Struktur für die Verwendung von `concurrent_unordered_set`. Dieses Beispiel fügt Zeichenwerte im Bereich ['a', ' i']. Es ist sicher, die Einfügevorgänge parallel.  
  
 [!CODE [concrt-unordered-set#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-unordered-set#1)]  
  
 [[Nach oben](#top)]  
  
##  <a name="a-nameunorderedmultiseta-concurrentunorderedmultiset-class"></a><a name="unordered_multiset"></a> Concurrent_unordered_multiset-Klasse  
 Die [concurrency::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) -Klasse gleicht der `concurrent_unordered_set` Klasse, außer dass sie doppelte Werte zulässt. Sie unterscheidet sich auch von `concurrent_unordered_set` auf folgende Weise:  
  
-   Die [concurrent_unordered_multiset:: Insert](../Topic/concurrent_unordered_multiset::insert%20Method.md) Methode gibt einen Iterator anstelle von `std::pair<iterator, bool>`.  
  
-   Die `concurrent_unordered_multiset` -Klasse keinen `operator[]` noch die `at` Methode.  
  
 Im folgende Beispiel wird die grundlegende Struktur für die Verwendung von `concurrent_unordered_multiset`. Dieses Beispiel fügt Zeichenwerte im Bereich ['a', ' i']. `concurrent_unordered_multiset` aktiviert einen Wert, der mehrfach vorkommen.  
  
 [!CODE [concrt-unordered-multiset#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-unordered-multiset#1)]  
  
 [[Nach oben](#top)]  
  
##  <a name="a-namecombinablea-combinable-class"></a><a name="combinable"></a> combinable-Klasse  
 Die [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) Klasse bietet wieder verwendbare, Thread-Local Storage, mit dem Sie differenzierte Berechnungen ausführen und dann zu einem Endergebnis zusammenführen. Stellen Sie sich ein `combinable`-Objekt wie eine Reduktionsvariable vor.  
  
 Die `combinable` -Klasse ist hilfreich, wenn Sie eine Ressource verfügen, die von mehreren Threads bzw. Aufgaben gemeinsam genutzt wird. Die `combinable` -Klasse können Sie die freigegebenen Zustand vermeiden können durch Zugriff auf freigegebene Ressourcen auf eine Sperre freizugeben. Diese Klasse stellt daher eine Alternative zur Verwendung eines Synchronisierungsmechanismus, z. B. einen Mutex, zum Synchronisieren des Zugriffs auf freigegebene Daten von mehreren Threads.  
  
###  <a name="a-namecombinable-featuresa-methods-and-features"></a><a name="combinable-features"></a> Methoden und Funktionen  
 Die folgende Tabelle zeigt einige der wichtigen Methoden der `combinable` Klasse. Weitere Informationen zu den `combinable` -Klassenmethoden, finden Sie unter [combinable-Klasse](../../parallel/concrt/reference/combinable-class.md).  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[lokale](../Topic/combinable::local%20Method.md)|Ruft einen Verweis auf die lokale Variable, die den aktuellen Kontext des Threads zugeordnet ist.|  
|[Deaktivieren](../Topic/combinable::clear%20Method.md)|Entfernt alle lokalen Threadvariablen aus der `combinable` Objekt.|  
|[Kombinieren](../Topic/combinable::combine%20Method.md)<br /><br /> [combine_each](../Topic/combinable::combine_each%20Method.md)|Verwendet die bereitgestellte Combine-Funktion einen endgültigen Wert aus dem Satz von allen lokalen Thread-Berechnungen zu generieren.|  
  
 Die `combinable` -Klasse ist eine Vorlagenklasse, die auf Grundlage der endgültigen zusammengeführten Ergebnisses parametrisiert wird. Wenn Sie den Standardkonstruktor Aufrufen der `T` Vorlagentyp-Parameter muss einen Standardkonstruktor und einen Kopierkonstruktor verfügen. Wenn die `T` Vorlagentyp-Parameter nicht über einen Standardkonstruktor verfügen, rufen Sie die überladene Version des Konstruktors, der eine Initialisierungsfunktion als Parameter akzeptiert.  
  
 Können Sie zusätzliche Daten in speichern ein `combinable` -Objekt nach dem Aufruf der [kombinieren](../Topic/combinable::combine%20Method.md) oder [Combine_each](../Topic/combinable::combine_each%20Method.md) Methoden. Sie können auch aufrufen, die `combine` und `combine_each` Methoden mehrmals. Wenn kein lokaler Wert in einem `combinable` -Objekts ändert, die `combine` und `combine_each` Methoden liefern das gleiche Ergebnis jedes Mal aus, die sie aufgerufen werden.  
  
###  <a name="a-namecombinable-examplesa-examples"></a><a name="combinable-examples"></a> Beispiele für  
 Beispiele zur Verwendung der `combinable` Klasse, finden Sie unter den folgenden Themen:  
  
-   [Gewusst wie: Verbessern der Leistung mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
  
-   [Gewusst wie: Kombinieren von combinable](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
  
 [[Nach oben](#top)]  
  
## <a name="related-topics"></a>Verwandte Themen  
 [Gewusst wie: Erhöhen der Effizienz mithilfe von parallelen Containern](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)  
 Veranschaulicht, wie mithilfe von parallelen Containern effizient zu speichern und Zugreifen auf Daten parallel.  
  
 [Gewusst wie: Verbessern der Leistung mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
 Veranschaulicht, wie die `combinable` Klasse, um die freigegebenen Zustand vermeiden können, und so die Leistung zu verbessern.  
  
 [Gewusst wie: Kombinieren von combinable](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
 Veranschaulicht, wie eine `combine` Funktion, um lokale Daten zusammenzuführen.  
  
 [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)  
 Beschreibt die PPL, die ein obligatorisches Programmiermodell bereitstellt, das Skalierbarkeit und einfache Handhabung beim Entwickeln gleichzeitige Anwendungen fördert.  
  
## <a name="reference"></a>Verweis  
 [Concurrent_vector-Klasse](../../parallel/concrt/reference/concurrent-vector-class.md)  
  
 [Concurrent_queue-Klasse](../../parallel/concrt/reference/concurrent-queue-class.md)  
  
 [Concurrent_unordered_map-Klasse](../../parallel/concrt/reference/concurrent-unordered-map-class.md)  
  
 [Concurrent_unordered_multimap-Klasse](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)  
  
 [Concurrent_unordered_set-Klasse](../../parallel/concrt/reference/concurrent-unordered-set-class.md)  
  
 [Concurrent_unordered_multiset-Klasse](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)  
  
 [combinable-Klasse](../../parallel/concrt/reference/combinable-class.md)
