---
title: Iteratoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- iterator conventions
- C++ Standard Library, iterator conventions
ms.assetid: 2f746be7-b37d-4bfc-bf05-be4336ca982f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 858612ebdda30e68972d11072b4c2ac7f4f88954
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235489"
---
# <a name="iterators"></a>Iterators

Ein Iterator ist ein Objekt, das Elemente in einem C++-Standardbibliothekscontainer durchlaufen kann und den Zugriff auf einzelne Elemente bereitstellt. Alle C++-Standardbibliothekscontainer stellen Iteratoren bereit, damit Algorithmen standardisiert auf ihre Elemente zugreifen können, ohne dass die Art des Containers von Bedeutung ist, in dem die Elemente gespeichert werden.

Sie können Iteratoren explizit mit Member- und globalen Funktionen wie z. B. `begin()` und `end()` und Operatoren, z. B. **++** und **--** voranschreiten oder rückwärts. Sie können Iteratoren auch implizit verwenden, mit einer Range-for-Schleife oder (für bestimmte iteratortypen) den tiefgestellt-Operator  **\[]**.

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

- **Output**. Ein *Ausgabeiterator* `X` kann vorwärts Durchlaufen einer Sequenz mithilfe der **++** -Operator, und ein Element mit nur einmal schreiben zu können die **&ast;** Operator.

- **Input**. Ein *eingabeiterator* `X` kann vorwärts Durchlaufen einer Sequenz mithilfe der ++-Operator, und erhalten ein Element beliebig häufig mithilfe der **&ast;** Operator. Sie können eingabeiteratoren mithilfe von Vergleichen die **++** und **! =** Operatoren. Nach der Inkrementierung einer Kopie eines Eingabeiterators kann keine der anderen Kopien sicher verglichen, dereferenziert oder inkrementiert werden.

- **Forward**. Ein *forward-Iterator* `X` eine Sequenz mit kann vorwärts durchlaufen den-Operator und beliebiges Element lesen oder Schreiben nicht Konstante Elemente beliebig häufig mithilfe der **&ast;** Operator. Sie können auf elementmitglieder zugreifen, mithilfe der **->** Iteratoren mithilfe weiterleiten, Operator und Vergleichen der **==** und **! =** Operatoren. Sie können mehrere Kopien eines Forward-Iterators anfertigen, wobei jede einzelne unabhängig dereferenziert und inkrementiert werden kann. Ein forward-Iterator, der initialisiert wird, ohne Verweis auf einen beliebigen Container aufgerufen wird, eine *null-forward-Iterator*. Null-Forward-Iteratoren vergleichen immer gleich.

- **Bidirektionale**. Ein *bidirektionaler Iterator, der* `X` kann die Stelle eines forward-Iterators treten. Sie können jedoch auch einen bidirektionaler Iterator, wie in verringern `--X`, `X--`, oder `(V = *X--)`. Sie können auf Elementmitglieder zugreifen und bidirektionale Iteratoren genauso wie Forward-Iteratoren vergleichen.

- **Random Access**. Ein *Iterator mit wahlfreiem Zugriff* `X` kann die Stelle eines bidirektionalen Iterators treten. Mit einem Iterator mit wahlfreiem Zugriff können Sie den tiefgestellten-Operator  **\[]** Zugriff auf Elemente. Sie können die **+**, **-**, **+=** und **-=** Operatoren verschieben Vorwärts oder rückwärts eine angegebene Anzahl von Elementen und den Abstand zwischen Iteratoren berechnen. Sie können Bidirektionale Iteratoren vergleichen, mithilfe von **==**, **! =**, **\<**, **>**, **\< =**, und **>=**.

Alle Iteratoren können zugewiesen oder kopiert werden. Es wird angenommen, dass es sich bei ihnen um Lightweight-Objekte handelt, und sie werden oftmals nach Wert und nicht nach Verweis weiter- und zurückgegeben. Beachten Sie zudem, dass einer der zuvor beschriebenen Vorgänge eine Ausnahme auslösen kann, wenn er für einen gültigen Iterator ausgeführt wird.

Die Hierarchie der Iteratorkategorien kann durch das Zeigen von drei Sequenzen zusammengefasst werden. Für den schreibgeschützten Zugriff auf eine Sequenz können Sie Folgendes verwenden:

> Ausgabe-iterator<br/>
> forward-Iterator -><br/>
> bidirektionaler Iterator, der -><br/>
> random-Access-Iterator -><br/>

Der Pfeil nach rechts meint: „kann ersetzt werden durch“. Jeder einen Ausgabeiterator aufrufende Algorithmus sollte beispielsweise problemlos mit einem Forward-Iterator funktionieren; dies gilt jedoch *nicht* umgekehrt.

Für den schreibgeschützten Zugriff auf eine Sequenz können Sie Folgendes verwenden:

> Eingabe-iterator<br/>
> forward-Iterator -><br/>
> bidirektionaler Iterator, der -><br/>
> random-Access-Iterator -><br/>

In diesem Fall ist ein Eingabeiterator die schwächste aller Kategorien.

Schließlich können Sie für den Lese-/Schreibzugriff auf eine Sequenz Folgendes verwenden:

> Forward-iterator<br/>
> bidirektionaler Iterator, der -><br/>
> random-Access-Iterator -><br/>

Ein Objektzeiger kann immer als ein Random-Access-Iterator fungieren. Er kann demnach als eine beliebige Kategorie des Iterators fungieren, wenn er den entsprechenden Lese-/Schreibzugriff auf die Sequenz unterstützt, die er festlegt.

Ein Iterator `Iterator`, der dem Objektzeiger nicht entspricht, muss zudem die Membertypen definieren, die durch die Spezialisierung `iterator_traits<Iterator>` erforderlich ist. Bitte beachten Sie, dass diese Anforderungen erfüllt werden können, indem `Iterator` aus der öffentlichen Basisklasse [iterator](../standard-library/iterator-struct.md) abgeleitet wird.

Es ist wichtig, die Zusagen und Einschränkungen jeder Iteratorkategorie zu verstehen, um nachzuvollziehen, wie Iteratoren durch Container und Algorithmen in der C++-Standardbibliothek verwendet werden.

> [!NOTE]
> Sie können die explizite Verwendung von Iteratoren mithilfe von range-for-Schleifen umgehen. Weitere Informationen finden Sie unter [bereichsbasiert für Anweisung](../cpp/range-based-for-statement-cpp.md).

Visual C++ bietet jetzt überprüfte Iteratoren und Debug-Iteratoren, um sicherzustellen, dass Sie die Grenzen Ihres Containers nicht überschreiben. Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md) und [Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md).

## <a name="see-also"></a>Siehe auch

[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
