---
title: Algorithmen
ms.date: 10/18/2018
helpviewer_keywords:
- libraries [C++], C++ algorithm conventions
- algorithms [C++], C++
- C++ Standard Library, algorithms
- algorithm template function C++ library conventions
- conventions [C++], C++ algorithm
ms.assetid: dec9b373-7d5c-46cc-b7d2-21a938ecd0a6
ms.openlocfilehash: d363dc3f06222121ac5efc79b30516ebd55ff539
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456485"
---
# <a name="algorithms"></a>Algorithmen

Algorithmen sind grundlegender Bestandteil der C++-Standardbibliothek. Algorithmen arbeiten nicht mit Containern selbst, sondern mit Iteratoren. Daher kann der gleiche Algorithmus von den meisten, wenn nicht gar allen, C++-Standardbibliothekcontainern verwendet werden. Dieser Abschnitt beschreibt die Konventionen und die Terminologie von C++-Standardbibliothekalgorithmen.

## <a name="remarks"></a>Hinweise

Die Beschreibungen der Algorithmusvorlagenfunktionen verwenden einige Kurznotationsausdrücke:

- Der Ausdruck " \[im Bereich *A*, *b*)" bezieht sich auf die Sequenz von 0 (null) oder mehr diskreten Werten, beginnend mit *a* bis einschließlich *b*. Ein Bereich ist nur gültig, *Wenn B* von einem erreichbar ist. Sie können *ein* -Objekt in einem Objekt *n* (*n* = *A*) speichern, das Objekt NULL oder mehrmals erhöhen (+ +*N*) und das Objekt gleich *B* vergleichen *.* nach einer endlichen Anzahl von Inkrementen (*N* == *B*).

- Der Ausdruck "jedes *N* im Bereich \[ *a*, *B*)" bedeutet, dass *N* mit dem Wert *A* beginnt und NULL oder mehrmals erhöht wird, bis es gleich dem Wert *B*ist. Der Fall *N*  ==  *B* ist nicht im Bereich.

- Der Ausdruck "der niedrigste Wert von *N* im \[Bereich *a*, *b*) für *X*" bedeutet, dass die Bedingung *x* für jedes *N* im Bereich \[ *a*, *b*) bestimmt wird, bis die Bedingung *X* ist erfüllt.

- Der Ausdruck "der höchste Wert von *N* im \[Bereich *a*, b), d. *h*. *x* bedeutet, dass *x* für *jedes N* im Bereich \[ *a*, *b*) bestimmt wird. Die Funktion speichert immer *dann eine Kopie* von *N* , wenn die Bedingung *X* erfüllt ist. Wenn ein solcher Speicher auftritt, ersetzt die Funktion den endgültigen Wert von *N*, der *B*entspricht, mit dem Wert *K*. Bei einem bidirektionalen Iterator oder einem Iterator mit wahlfreiem Zugriff kann dies jedoch auch bedeuten, dass *N* mit dem höchsten Wert des Bereichs beginnt und so lange über den Bereich erniedrigt wird, bis die Bedingung *X* erfüllt ist.

- Ausdrücke wie *Y* - *Y*, wobei *X* und *Y* andere Iteratoren als solche mit wahlfreiem Zugriff sein können, sind im mathematischen Sinn vorgesehen. Die Funktion wertet den Operator **-** nicht notwendigerweise aus, wenn Sie einen solchen Wert bestimmen muss. Gleiches gilt für Ausdrücke wie *X* + *N* und *X* - *N*, wobei *N* ein Ganzzahltyp ist.

Mehrere Algorithmen verwenden ein Prädikat, das einen paar weisen Vergleich ausführt, z. b. mit `operator==`, um ein boolescher Ergebnis zu erzielen. Die Prädikatfunktion `operator==`, oder jeder Ersatz hierfür, darf keinen der beiden Operanden ändern. Es muss jedes Mal,  wenn es ausgewertet wird, dasselbe boolesche Ergebnis erhalten, und es muss dasselbe Ergebnis erzielen, wenn eine Kopie eines der beiden Operanden für den Operanden ersetzt wird.

Mehrere Algorithmen verwenden ein Prädikat, das eine strikte schwache Sortierung für Elementpaare aus einer Sequenz anwendet. Für Prädikat *präd*(*X*, *Y*):

- Strict bedeutet, dass *pred*(*x*, *x*) "false" ist.

- Schwach bedeutet, dass *x* und *y* eine äquivalente Reihen \!Folge aufweisen, wenn *pred*(*x*, \! *y*) & & *pred*(*y*, *x*) (*x* == *Y* nicht muss definiert werden).

- Die Reihenfolge bedeutet, dass *pred*(*x*, *Y*) & & *pred*(*y*, *z*) eine *pred*(*x*, *z*) impliziert.

Einige dieser Algorithmen verwenden implizit das Prädikat *X* \< *Y*. Andere Prädikate, die in der Regel die strenge Anforderungen an schwache Reihen `less`Folge erfüllen, sind *x* > *Y*, `greater`(*x*, *y*) und (*X*, *y*). Beachten Sie jedoch, dass Prädikate wie *X* \<= *Y* und *X* >= *Y* diese Anforderung nicht erfüllen.

Eine Sequenz von Elementen, die durch Iteratoren im Bereich \[ *First*, *Last*) festgelegt ist, ist eine **<** Sequenz, geordnet nach Operator, wenn für \[jedes *N* im Bereich 0, *zuletzt* - *zuerst* ) und für jedes *M* im Bereich (*N*, *zuletzt* - *zuerst*) das \!Prädikat (\*(*First* + *M*) < \*(First + *N*)) ist "true". (Beachten Sie, dass die Elemente in aufsteigender Reihenfolge sortiert werden.) Die Prädikatfunktion `operator<`, oder jeder Ersatz hierfür, darf keinen der beiden Operanden ändern. Es muss jedes Mal,  wenn es ausgewertet wird, dasselbe boolesche Ergebnis erhalten, und es muss dasselbe Ergebnis erzielen, wenn eine Kopie eines der beiden Operanden für den Operanden ersetzt wird. Darüber hinaus muss sie eine strikte schwache Sortierung für die verglichenen Operanden anwenden.

Eine Sequenz von Elementen, die durch Iteratoren im Bereich \[ `First`, `Last`) festgelegt ist, ist `operator<` ein Heap, geordnet  nach, wenn für \[jedes N im Bereich 1, *zuletzt* - *zuerst*) der Prädikat \!(\*_erstes_ *(erstes*N)) ist "true". +  < \* (Das erste Element ist das größte.) Die interne Struktur ist andernfalls nur den Vorlagen Funktionen [Make_heap](../standard-library/algorithm-functions.md#make_heap), [pop_heap](../standard-library/algorithm-functions.md#pop_heap)und [Push_heap](../standard-library/algorithm-functions.md#push_heap)bekannt. Wie bei einer geordneten Sequenz darf die Prädikat Funktion `operator<`oder ein beliebiger Ersatz dafür keinen der Operanden ändern, und Sie muss eine strikte schwache Reihenfolge für die Operanden erzwingen, die Sie vergleicht. Es muss jedes Mal,  wenn es ausgewertet wird, dasselbe boolesche Ergebnis erhalten, und es muss dasselbe Ergebnis erzielen, wenn eine Kopie eines der beiden Operanden für den Operanden ersetzt wird.

Die C++-Standardbibliotheksalgorithmen in den Headerdateien [\<algorithm>](../standard-library/algorithm.md) und [\<numeric>](../standard-library/numeric.md) zu finden.

## <a name="see-also"></a>Siehe auch

[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
