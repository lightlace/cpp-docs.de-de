---
title: Algorithmen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- libraries [C++], C++ algorithm conventions
- algorithms [C++], C++
- C++ Standard Library, algorithms
- algorithm template function C++ library conventions
- conventions [C++], C++ algorithm
ms.assetid: dec9b373-7d5c-46cc-b7d2-21a938ecd0a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5338ddeb802d13d100e5e3026152793f866c90f6
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961024"
---
# <a name="algorithms"></a>Algorithmen

Algorithmen sind grundlegender Bestandteil der C++-Standardbibliothek. Algorithmen arbeiten nicht mit Containern selbst, sondern mit Iteratoren. Daher kann der gleiche Algorithmus von den meisten, wenn nicht gar allen, C++-Standardbibliothekcontainern verwendet werden. Dieser Abschnitt beschreibt die Konventionen und die Terminologie von C++-Standardbibliothekalgorithmen.

## <a name="remarks"></a>Hinweise

Die Beschreibungen der Algorithmusvorlagenfunktionen verwenden einige Kurznotationsausdrücke:

- Der Ausdruck „im Bereich (*A*, *B*)“ bezeichnet eine Sequenz von 0 oder mehreren diskreten Werten beginnend mit *A* bis, jedoch nicht einschließlich, *B*. Ein Bereich ist nur gültig, wenn *B* von *A* aus erreichbar ist. Sie können *A* in einem Objekt *N* (*N* = *A*) speichern, das Objekt null oder mehrmals erhöhen (++*N*) und das Objekt nach einer endlichen Anzahl von Erhöhungsschritten (N == B *) gleich *B* entsprechen lassen.*

- Der Ausdruck „jedes *N* im Bereich (*A*, *B*)“ bedeutet, dass *N* mit dem Wert *A* beginnt und null oder mehrmals erhöht wird, bis es gleich dem Wert *B* ist. Der Fall *N* == *B* ist nicht im Bereich.

- Der Ausdruck „der niedrigste Wert von *N* im Bereich (*A*, *B*), sodass *X*“ bedeutet, dass die Bedingung *X* für jedes *N* im Bereich (*A*, *B*) bestimmt wird, bis die Bedingung *X* erfüllt ist.

- Der Ausdruck „der höchste Wert von *N* im Bereich (*A*, *B*), sodass *X*“ bedeutet, dass *X* für jedes *N* im Bereich (*A*, *B*) bestimmt wird. Die Funktion speichert in `K` eine Kopie von *N*, jedes Mal, wenn die Bedingung *X* erfüllt wird. Wenn eine solche Speicherung auftritt, ersetzt die Funktion den endgültigen Wert von *N*, der gleich *B* ist, mit dem Wert von `K`. Bei einem bidirektionalen Iterator oder einem Iterator mit wahlfreiem Zugriff kann dies jedoch auch bedeuten, dass *N* mit dem höchsten Wert des Bereichs beginnt und so lange über den Bereich erniedrigt wird, bis die Bedingung *X* erfüllt ist.

- Ausdrücke wie *Y* - *Y*, wobei *X* und *Y* andere Iteratoren als solche mit wahlfreiem Zugriff sein können, sind im mathematischen Sinn vorgesehen. Die Funktion wertet den Operator **-** nicht notwendigerweise aus, wenn sie einen solchen Wert bestimmen muss. Gleiches gilt für Ausdrücke wie *X* + *N* und *X* - *N*, wobei *N* ein Ganzzahltyp ist.

Mehrere Algorithmen verwenden ein Prädikat, das einen paarweisen Vergleich, wie z. B. führt `operator==`, um eine **"bool"** Ergebnis. Die Prädikatfunktion `operator==`, oder jeder Ersatz hierfür, darf keinen der beiden Operanden ändern. Es muss die gleiche liefern **"bool"** führt jedes Mal ausgewertet wird, und es muss das gleiche Ergebnis liefern, wenn eine Kopie einer der Operanden für den Operanden ersetzt wird.

Mehrere Algorithmen verwenden ein Prädikat, das eine strikte schwache Sortierung für Elementpaare aus einer Sequenz anwendet. Für das Prädikat `pr`(*X*, *Y*):

- „Strict“ bedeutet, dass `pr`(*X*, *X*) falsch ist.

- „Schwach“ bedeutet, dass *X* und *Y* die gleiche Sortierung aufweisen, wenn !`pr`(*X*, *Y*) && !`pr`(*Y*, *X*) (*X* == *Y* muss nicht definiert sein).

- „Sortierung“ bedeutet, dass `pr`(*X*, *Y)* && `pr`(*Y*, Z) `pr`(*X*, Z) impliziert.

Einige dieser Algorithmen verwenden implizit das Prädikat *X* \< *Y*. Andere Prädikate, die in der Regel die strikten schwachen Sortierung Anforderung zu erfüllen sind *X* > *Y*, `less`(*X*, *Y*), und `greater`(*X*, *Y*). Beachten Sie jedoch, dass Prädikate wie *X* \<= *Y* und *X* >= *Y* diese Anforderung nicht erfüllen.

Eine Sequenz von Elementen, durch Iteratoren festgelegt, im Bereich (`First`, `Last`) ist eine durch den Operator **<** sortierte Sequenz, wenn für jedes *N* im Bereich (0, `Last` - `First`) und für jedes *M* im Bereich (N, `Last` - `First`) das Prädikat !(\*(`First` + *M*) < \*(*First* + *N*) erfüllt ist. (Beachten Sie, dass die Elemente in aufsteigender Reihenfolge sortiert werden.) Die Prädikatfunktion `operator<`, oder jeder Ersatz hierfür, darf keinen der beiden Operanden ändern. Sie muss bei jeder Auswertung dasselbe `bool`-Ergebnis ausgeben. Außerdem muss sie dasselbe Ergebnis ausgeben, wenn eine Kopie einer der Operanden für den Operanden ersetzt wird. Darüber hinaus muss sie eine strikte schwache Sortierung für die verglichenen Operanden anwenden.

Eine Sequenz von Elementen, die durch Iteratoren im Bereich festgelegt, [`First`, `Last`) ist ein Heap sortiert nach `operator<` Wenn für jedes *N* im Bereich [1, `Last`  -  `First`) die das Prädikat! (\*`First` < \*(`First` + *N*)) ist "true". (Das erste Element ist das größte.) Seine interne Struktur ist andernfalls nur an die Vorlagenfunktionen bezeichnet [Make_heap](../standard-library/algorithm-functions.md#make_heap), [Pop_heap](../standard-library/algorithm-functions.md#pop_heap), und [Push_heap](../standard-library/algorithm-functions.md#push_heap). Wie bei eine geordnete Sequenz, die Prädikatfunktion `operator<`, oder jeder Ersatz hierfür, darf nicht beiden Operanden ändern, und sie muss eine strikte schwache Sortierung auf die verglichenen Operanden anwenden. Es muss die gleiche liefern **"bool"** führt jedes Mal ausgewertet wird, und es muss das gleiche Ergebnis liefern, wenn eine Kopie einer der Operanden für den Operanden ersetzt wird.

Die C++-Standardbibliotheksalgorithmen in den Headerdateien [\<algorithm>](../standard-library/algorithm.md) und [\<numeric>](../standard-library/numeric.md) zu finden.

## <a name="see-also"></a>Siehe auch

[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
