---
title: '&lt;vector&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- <vector>
dev_langs:
- C++
helpviewer_keywords:
- vector header
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 284afc807465d5b8d694926f60787afdf010fe30
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="ltvectorgt"></a>&lt;vector&gt;

Definiert den Containervorlagenklassenvektor und einige unterstützende Vorlagen.

Der `vector` ist ein Container, der Elemente eines bestimmten Typs in einer linearen Sequenz organisiert. Er ermöglicht schnellen zufälligen Zugriff auf alle Elemente sowie dynamische Hinzufügungen und Entfernungen zu und aus der Sequenz. Der `vector` ist der bevorzugte Container für eine Sequenz, wenn die Leistung mit wahlfreiem Zugriff ein wichtiger Faktor ist.

Weitere Informationen zur `vector`-Klasse finden Sie unter [vector-Klasse](../standard-library/vector-class.md). Weitere Informationen zu der Spezialisierung `vector<bool>` finden Sie unter [vector\<bool>-Klasse](../standard-library/vector-bool-class.md).

## <a name="syntax"></a>Syntax

```cpp
namespace std {
template <class Type, class Allocator>
class vector;
template <class Allocator>
class vector<bool>;

template <class Allocator>
struct hash<vector<bool, Allocator>>;
 // TEMPLATE FUNCTIONS
template <class Type, class Allocator>
bool operator== (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator!= (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator<(
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator> (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator<= (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator>= (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
void swap (
    vector<Type, Allocator>& left,
    vector<Type, Allocator>& right);

}  // namespace std
```

### <a name="parameters"></a>Parameter

Geben Sie die Vorlagenparameter für den Typ der im Vektor gespeicherten Daten.

Zuweisung der Vorlagenparameter für das gespeicherte Zuweisungsobjekt für die speicherbelegung und-Freigabe verantwortlich.

`left` Der erste (linke) Vektor in einem Vergleichsvorgang.

`right` Der zweite (Rechte) Vektor in einem Vergleichsvorgang.

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator! =](../standard-library/vector-operators.md#op_neq)|Testet, ob das Vektorobjekt links vom Operator ungleich dem Vektorobjekt rechts vom Operator ist.|
|[operator<](../standard-library/vector-operators.md#op_lt)|Testet, ob das Vektorobjekt links vom Operator kleiner als das Vektorobjekt auf der rechten Seite ist.|
|[operator\<=](../standard-library/vector-operators.md#op_gt_eq)|Testet, ob das Vektorobjekt links vom Operator kleiner als oder gleich dem Vektorobjekt rechts vom Operator ist.|
|[operator==](../standard-library/vector-operators.md#op_eq_eq)|Testet, ob das Vektorobjekt links vom Operator gleich dem Vektorobjekt rechts vom Operator ist.|
|[operator>](../standard-library/vector-operators.md#op_gt)|Testet, ob das Vektorobjekt links vom Operator größer als das Vektorobjekt auf der rechten Seite ist.|
|[operator>=](../standard-library/vector-operators.md#op_gt_eq)|Testet, ob das Vektorobjekt links vom Operator größer als oder gleich dem Vektorobjekt rechts vom Operator ist.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[vector-Klasse](../standard-library/vector-class.md)|Eine Vorlagenklasse von Sequenzcontainern, die Elemente eines bestimmten Typs in einer linearen Anordnung anordnen und schnellen zufälligen Zugriff auf ein Element ermöglichen.|

### <a name="specializations"></a>Spezialisierungen

|||
|-|-|
|[vector\<bool>-Klasse](../standard-library/vector-bool-class.md)|Eine vollständige Spezialisierung des Vorlagenklassenvektors für Elemente des Typs `bool` mit einer Zuweisung für den zugrunde liegenden Typ, der von der Spezialisierung verwendet wird.|

## <a name="requirements"></a>Anforderungen

**Header:** \<vector>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
