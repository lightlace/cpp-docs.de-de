---
title: '&lt;numerisch&gt;'
ms.date: 11/04/2016
f1_keywords:
- <numeric>
helpviewer_keywords:
- <numeric> header
ms.assetid: 6d6ccb94-48cc-479b-b4a9-bd9c78d4896a
ms.openlocfilehash: 5862ddd812308c7bf81a5029249caf7e9b4a1168
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453551"
---
# <a name="ltnumericgt"></a>&lt;numerisch&gt;

Definiert Containervorlagenfunktionen, die Algorithmen für die numerische Verarbeitung durchführen.

## <a name="requirements"></a>Anforderungen

**Header**: \<numeric >

**Namespace:** std

## <a name="remarks"></a>Hinweise

Die numerischen Algorithmen ähneln den Algorithmen der C++-Standardbibliothek in [\<algorithm>](algorithm.md) und können für einer Vielzahl von Datenstrukturen ausgeführt werden. Dazu gehören Standard-Bibliothekscontainerklassen, z.B. [vector](../standard-library/vector-class.md) und [list](../standard-library/list-class.md), sowie programmdefinierte Datenstrukturen und Arrays von Elementen, die die Anforderungen eines bestimmten Algorithmus erfüllen. Algorithmen erzielen dieses Maß an Allgemeingültigkeit, indem sie indirekt über Iteratoren auf die Elemente eines Containers zugreifen und diese durchlaufen. Die Process-Iteratorbereiche für Algorithmen werden in der Regel durch ihre Start- oder Zielpositionen angegeben. Die Bereiche, die angegeben werden, müssen in dem Sinne gültig sein, dass alle Zeiger in den Bereichen dereferenzierbar sind und innerhalb der Sequenzen der einzelnen Bereiche liegen. Die letzte Position muss außerdem von der ersten mittels Zunahme erreichbar sein.

Die Algorithmen erweitern die Aktionen, die durch die Vorgänge und Memberfunktionen der einzelnen C++-Standardbibliothekscontainer unterstützt werden, und aktivieren die Interaktion mit verschiedenen Typen von Containerobjekten gleichzeitig.

## <a name="members"></a>Member

### <a name="functions"></a>Funktionen

|||
|-|-|
|[accumulate](../standard-library/numeric-functions.md#accumulate)|Berechnet die Summe aller Elemente in einem angegebenen Bereich, einschließlich Anfangswert, indem aufeinander folgende Teilsummen berechnet werden, oder berechnet das Ergebnis der aufeinander folgenden Teilergebnisse, die mithilfe eines angegebenen binären Vorgangs (außer Summe) abgerufen werden.|
|[adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference)|Berechnet die aufeinander folgenden Unterschiede zwischen einem Element und seinem Vorgänger in einem Eingabebereich und gibt die Ergebnisse in einem Zielbereich aus oder berechnet das Ergebnis einer allgemeinen Prozedur, in der der Vorgang zum Feststellen von Unterschieden durch einen anderen angegebenen binären Vorgang ersetzt wird.|
|[exclusive_scan](../standard-library/numeric-functions.md#exclusive_scan)||
|[GCD](../standard-library/numeric-functions.md#gcd)||
|[inclusive_scan](../standard-library/numeric-functions.md#inclusive_scan)||
|[inner_product](../standard-library/numeric-functions.md#inner_product)|Berechnet die Summe des elementweisen Produkts von zwei Bereichen und fügt sie einem angegebenen Anfangswert hinzu oder berechnet das Ergebnis einer allgemeinen Prozedur, in der die Summen- und Produktvorgänge durch andere angegebene binäre Vorgänge ersetzt werden.|
|[iota](../standard-library/numeric-functions.md#iota)|Speichert einen Startwert, beginnend mit dem ersten Element und füllt ihn mit aufeinander folgenden Schritten des Werts (`value++`) in jedem der Elemente im Intervall `[first, last)` auf.|
|[LCM](../standard-library/numeric-functions.md#lcm)||
|[partial_sum](../standard-library/numeric-functions.md#partial_sum)|Berechnet eine Reihe von Summen in einem Eingabebereich vom ersten Element bis zum *i*th-Element und speichert das Ergebnis jeder Summe im *i*th-Element eines Zielbereichs oder berechnet das Ergebnis einer allgemeinen Prozedur, in der der Summenvorgang durch einen anderen angegebenen binären Vorgang ersetzt wird.|
|[Ver](../standard-library/numeric-functions.md#reduce)||
|[transform_exclusive_scan](../standard-library/numeric-functions.md#transform_exclusive_scan)||
|[transform_inclusive_scan](../standard-library/numeric-functions.md#transform_inclusive_scan)||
|[transform_reduce](../standard-library/numeric-functions.md#transform_reduce)||

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)
