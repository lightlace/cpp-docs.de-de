---
title: Algorithmen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2018
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
ms.openlocfilehash: 0388a3c21fec2d902b74856e4a0ca596b4b3bcca
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063021"
---
# <a name="algorithms"></a>Algorithmen

Algorithmen sind grundlegender Bestandteil der C++-Standardbibliothek. Algorithmen arbeiten nicht mit Containern selbst, sondern mit Iteratoren. Daher kann der gleiche Algorithmus von den meisten, wenn nicht gar allen, C++-Standardbibliothekcontainern verwendet werden. Dieser Abschnitt beschreibt die Konventionen und die Terminologie von C++-Standardbibliothekalgorithmen.

## <a name="remarks"></a>Hinweise

Die Beschreibungen der Algorithmusvorlagenfunktionen verwenden einige Kurznotationsausdrücke:

- Der Ausdruck "im Bereich von \[ *ein*, *B*)" bezeichnet eine Sequenz von keinem oder mehreren diskreten Werten beginnend mit *ein* bis, jedoch nicht einschließlich *B* . Ein Bereich gilt nur, wenn *B* aus erreichbar ist *A;* können Sie speichern *ein* in einem Objekt *N* (*N*  =  *Ein*), erhöhen Sie das Objekt NULL oder mehr Vorkommen (++*N*), und dass das Objekt, das mit gleich *B* nach einer endlichen Anzahl von Schritten (*N*   ==  *B*).

- Der Ausdruck "jedes *N* im Bereich von \[ *ein*, *B*)" bedeutet, dass *N* beginnt mit dem Wert *eine*und erhöht wird, NULL oder mehrmals, bis es gleich dem Wert *B*. Der Fall N** == B* ist nicht im Bereich.

- Der Ausdruck "der niedrigste Wert der *N* im Bereich von \[ *ein*, *B*) so, dass *X*" bedeutet, dass die Bedingung *X* wird bestimmt, für die einzelnen *N* im Bereich von \[ *ein*, *B*) bis die Bedingung *X*erfüllt ist.

- Der Ausdruck "der höchste Wert von *N* im Bereich von \[ *ein*, *B*) so, dass *X* bedeutet, dass *X* wird bestimmt, für die einzelnen *N* im Bereich von \[ *ein*, *B*). Die Funktion speichert im *K* eine Kopie des *N* jedes Mal, wenn die Bedingung *X* erfüllt ist. Wenn eine solche Speicherung auftritt, ersetzt die Funktion den endgültigen Wert der *N*, der gleich *B*, mit dem Wert des *K*. Bei einem bidirektionalen Iterator oder einem Iterator mit wahlfreiem Zugriff kann dies jedoch auch bedeuten, dass *N* mit dem höchsten Wert des Bereichs beginnt und so lange über den Bereich erniedrigt wird, bis die Bedingung *X* erfüllt ist.

- Ausdrücke wie *Y* - *Y*, wobei *X* und *Y* andere Iteratoren als solche mit wahlfreiem Zugriff sein können, sind im mathematischen Sinn vorgesehen. Die Funktion wertet Operator nicht unbedingt **-** , wenn sie einen solchen Wert bestimmen muss. Gleiches gilt für Ausdrücke wie *X* + *N* und *X* - *N*, wobei *N* ein Ganzzahltyp ist.

Mehrere Algorithmen verwenden ein Prädikat, das einen paarweisen Vergleich, wie z. B. führt `operator==`, um eine **"bool"** Ergebnis. Die Prädikatfunktion `operator==`, oder jeder Ersatz hierfür, darf keinen der beiden Operanden ändern. Es muss die gleiche liefern **"bool"** führt jedes Mal ausgewertet wird, und es muss das gleiche Ergebnis liefern, wenn eine Kopie einer der Operanden für den Operanden ersetzt wird.

Mehrere Algorithmen verwenden ein Prädikat, das eine strikte schwache Sortierung für Elementpaare aus einer Sequenz anwendet. Für das Prädikat *Pred*(*X*, *Y*):

- Bedeutet "Strict", die *Pred*(*X*, *X*) ist "false".

- Schwache bedeutet, dass *X* und *Y* haben Sie eine entsprechende Sortierung If \! *Pred*(*X*, *Y*) & & \! *Pred*(*Y*, *X*) (*X* == *Y*muss nicht definiert werden).

- Reihenfolge bedeutet, dass *Pred*(*X*, *Y*) & & *Pred*(*Y*, *Z*) impliziert *Pred*(*X*, *Z*).

Einige dieser Algorithmen verwenden implizit das Prädikat *X* \< *Y*. Andere Prädikate, die in der Regel die strikten schwachen Sortierung Anforderung zu erfüllen sind *X* > *Y*, `less`(*X*, *Y*), und `greater`(*X*, *Y*). Beachten Sie jedoch, dass Prädikate wie *X* \<= *Y* und *X* >= *Y* diese Anforderung nicht erfüllen.

Eine Sequenz von Elementen, die durch Iteratoren im Bereich festgelegt, \[ *erste*, *letzten*) ist eine Sequenz, geordnet nach Operator **<** If, für jede  *N* im Bereich von \[0 (null) *letzten* - *erste*) und für jede *M* im Bereich (*N*, *Letzten* - *erste*) das Prädikat \!(\*(*erste*  +  *M*) < \*(*erste* + *N*)) ist "true". (Beachten Sie, dass die Elemente in aufsteigender Reihenfolge sortiert werden.) Die Prädikatfunktion `operator<`, oder jeder Ersatz hierfür, darf keinen der beiden Operanden ändern. Es muss die gleiche liefern **"bool"** führt jedes Mal ausgewertet wird, und es muss das gleiche Ergebnis liefern, wenn eine Kopie einer der Operanden für den Operanden ersetzt wird. Darüber hinaus muss sie eine strikte schwache Sortierung für die verglichenen Operanden anwenden.

Eine Sequenz von Elementen, die durch Iteratoren im Bereich festgelegt, \[ `First`, `Last`) ist ein Heap sortiert nach `operator<` Wenn für jedes *N* im Bereich von \[1 *letzte*  -  *Erste*) das Prädikat \!(\*_erste_ < \*(*erste*  +  *N*)) ist "true". (Das erste Element ist das größte.) Seine interne Struktur ist andernfalls nur an die Vorlagenfunktionen bezeichnet [Make_heap](../standard-library/algorithm-functions.md#make_heap), [Pop_heap](../standard-library/algorithm-functions.md#pop_heap), und [Push_heap](../standard-library/algorithm-functions.md#push_heap). Wie bei eine geordnete Sequenz, die Prädikatfunktion `operator<`, oder jeder Ersatz hierfür, darf nicht beiden Operanden ändern, und sie muss eine strikte schwache Sortierung auf die verglichenen Operanden anwenden. Es muss die gleiche liefern **"bool"** führt jedes Mal ausgewertet wird, und es muss das gleiche Ergebnis liefern, wenn eine Kopie einer der Operanden für den Operanden ersetzt wird.

Die C++-Standardbibliotheksalgorithmen in den Headerdateien [\<algorithm>](../standard-library/algorithm.md) und [\<numeric>](../standard-library/numeric.md) zu finden.

## <a name="see-also"></a>Siehe auch

[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
