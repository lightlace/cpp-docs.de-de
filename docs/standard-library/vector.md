---
title: '&lt;vector&gt;'
ms.date: 11/04/2016
f1_keywords:
- <vector>
helpviewer_keywords:
- vector header
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
ms.openlocfilehash: 348b5c53ecd3fb7900d03fed7c1209a2c94eeb4c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410855"
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

*Type*<br/>
Der Vorlagenparameter für den Typ der Daten, die im Vektor gespeichert sind.

*Allocator*<br/>
Der Vorlagenparameter für das gespeicherte Zuweisungsobjekt, das für die Speicherbelegung und -freigabe verantwortlich ist.

*left*<br/>
Der erste (linke) Vektor in einem Vergleichsvorgang.

*right*<br/>
Der zweite (rechte) Vektor in einem Vergleichsvorgang.

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
