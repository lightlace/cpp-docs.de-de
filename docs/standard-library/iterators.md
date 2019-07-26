---
title: Iterators
ms.date: 11/04/2016
helpviewer_keywords:
- iterator conventions
- C++ Standard Library, iterator conventions
ms.assetid: 2f746be7-b37d-4bfc-bf05-be4336ca982f
ms.openlocfilehash: ec23cbea63bc6884a361600362fcf0061e927ca6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449966"
---
# <a name="iterators"></a>Iterators

Ein Iterator ist ein Objekt, das Elemente in einem C++-Standardbibliothekscontainer durchlaufen kann und den Zugriff auf einzelne Elemente bereitstellt. Alle C++-Standardbibliothekscontainer stellen Iteratoren bereit, damit Algorithmen standardisiert auf ihre Elemente zugreifen können, ohne dass die Art des Containers von Bedeutung ist, in dem die Elemente gespeichert werden.

Sie können Iteratoren explizit mit Element-und globalen Funktionen `begin()` wie und `end()` und Operatoren wie **++** und **--** verwenden, um vorwärts oder rückwärts zu wechseln. Sie können Iteratoren auch implizit mit einer Range-for-Schleife oder (bei einigen iteratortypen) dem Index Operator  **\[]** verwenden.

In der C++-Standardbibliothek ist der Anfang einer Sequenz oder eines Bereichs das erste Element. Das Ende einer Sequenz oder eines Bereichs wird immer als eins hinter dem letzten Element definiert. Die globalen Funktionen `begin` und `end` geben Iteratoren zu einem angegebenen Container zurück. Die typische explizite Iteratorschleife durch alle Elemente in einem Container sieht folgendermaßen aus:

```cpp
vector<int> vec{ 0,1,2,3,4 };
for (auto it = begin(vec); it != end(vec); it++)
{
    // Access element using dereference operator
    cout << *it << " ";
}
```

Das Gleiche kann einfacher mit einer range-for-Schleife erreicht werden:

```cpp
for (auto num : vec)
{
    // no deference operator
    cout << num << " ";
}
```

Es gibt fünf Kategorien von Iteratoren. Die Kategorien zum Erhöhen der Leistung sind:

- **Output**. Ein  `X` Ausgabeiterator kann eine Sequenz mithilfe des **++** -Operators vorwärts durchlaufen und ein Element nur einmal schreiben, indem der __\*__ -Operator verwendet wird.

- **Input**. Ein  `X` eingabeiterator kann eine Sequenz mit dem Operator + + vorwärts durchlaufen, und ein Element kann beliebig oft mithilfe des **&ast;** -Operators gelesen werden. Sie können eingabeiteratoren mithilfe der **++** Operatoren und **! =** vergleichen. Nach der Inkrementierung einer Kopie eines Eingabeiterators kann keine der anderen Kopien sicher verglichen, dereferenziert oder inkrementiert werden.

- **Forward**. Ein *forward-Iterator* `X` kann eine Sequenz mit dem Operator + + vorwärts durchlaufen und jedes beliebige Element lesen oder nicht konstante Elemente beliebig oft mithilfe des **&ast;** -Operators schreiben. Sie können mithilfe des **->** -Operators auf Element Elemente zugreifen und Forward-Iteratoren mithilfe der **==** Operatoren und **! =** vergleichen. Sie können mehrere Kopien eines Forward-Iterators anfertigen, wobei jede einzelne unabhängig dereferenziert und inkrementiert werden kann. Ein forward-Iterator, der ohne Verweis auf einen Container initialisiert wird, wird als *null-forward-Iterator*bezeichnet. Null-Forward-Iteratoren vergleichen immer gleich.

- **Bidirektional**. Ein *bidirektionaler Iterator* `X` kann an die Stelle eines Forward-Iterators gelangen. Sie können jedoch auch einen bidirektionalen Iterator Dekrement wie in `--X`, `X--`oder `(V = *X--)`verringern. Sie können auf Elementmitglieder zugreifen und bidirektionale Iteratoren genauso wie Forward-Iteratoren vergleichen.

- **Random Access**. `X` Ein *Iterator mit zufälligem Zugriff* kann den Platz eines bidirektionalen Iterators einnehmen. Mit einem Random-Access-Iterator können Sie den Index Operator  **\[]** verwenden, um auf Elemente zuzugreifen. Sie können die **+** Operatoren **-** **+=** , und **-=** verwenden, um eine angegebene Anzahl von Elementen vorwärts oder rückwärts zu bewegen und den Abstand zwischen Iteratoren zu berechnen. **==** Bidirektionale Iteratoren können mit, **! =** , **\<** , **\< =** **>** , und **>=** verglichen werden.

Alle Iteratoren können zugewiesen oder kopiert werden. Es wird angenommen, dass es sich bei ihnen um Lightweight-Objekte handelt, und sie werden oftmals nach Wert und nicht nach Verweis weiter- und zurückgegeben. Beachten Sie zudem, dass einer der zuvor beschriebenen Vorgänge eine Ausnahme auslösen kann, wenn er für einen gültigen Iterator ausgeführt wird.

Die Hierarchie der Iteratorkategorien kann durch das Zeigen von drei Sequenzen zusammengefasst werden. Für den schreibgeschützten Zugriff auf eine Sequenz können Sie Folgendes verwenden:

> Ausgabeiterator \
> -> forward-Iterator \
> -> bidirektionaler Iterator \
> -> Random-Access-Iterator

Der Pfeil nach rechts meint: „kann ersetzt werden durch“. Jeder einen Ausgabeiterator aufrufende Algorithmus sollte beispielsweise problemlos mit einem Forward-Iterator funktionieren; dies gilt jedoch *nicht* umgekehrt.

Für den schreibgeschützten Zugriff auf eine Sequenz können Sie Folgendes verwenden:

> eingabeiterator \
> -> forward-Iterator \
> -> bidirektionaler Iterator \
> -> Random-Access-Iterator

In diesem Fall ist ein Eingabeiterator die schwächste aller Kategorien.

Schließlich können Sie für den Lese-/Schreibzugriff auf eine Sequenz Folgendes verwenden:

> forward-Iterator \
> -> bidirektionaler Iterator \
> -> Random-Access-Iterator

Ein Objektzeiger kann immer als ein Random-Access-Iterator fungieren. Er kann demnach als eine beliebige Kategorie des Iterators fungieren, wenn er den entsprechenden Lese-/Schreibzugriff auf die Sequenz unterstützt, die er festlegt.

Ein Iterator `Iterator`, der dem Objektzeiger nicht entspricht, muss zudem die Membertypen definieren, die durch die Spezialisierung `iterator_traits<Iterator>` erforderlich ist. Bitte beachten Sie, dass diese Anforderungen erfüllt werden können, indem `Iterator` aus der öffentlichen Basisklasse [iterator](../standard-library/iterator-struct.md) abgeleitet wird.

Es ist wichtig, die Zusagen und Einschränkungen jeder Iteratorkategorie zu verstehen, um nachzuvollziehen, wie Iteratoren durch Container und Algorithmen in der C++-Standardbibliothek verwendet werden.

> [!NOTE]
> Sie können die explizite Verwendung von Iteratoren mithilfe von range-for-Schleifen umgehen. Weitere Informationen finden Sie unter [Range-based for-Anweisung](../cpp/range-based-for-statement-cpp.md).

Microsoft C++ bietet jetzt überprüfte Iteratoren und Debugiteratoren an, um sicherzustellen, dass Sie die Begrenzungen Ihres Containers nicht überschreiben. Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md) und [Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md).

## <a name="see-also"></a>Siehe auch

[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
