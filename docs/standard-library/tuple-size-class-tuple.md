---
title: tuple_size-Klasse;
ms.date: 11/04/2016
f1_keywords:
- tuple_size
- std::tuple_size
- utility/std::tuple_size
helpviewer_keywords:
- std::tuple_size
ms.assetid: 73852fc5-eb68-41f1-8379-465cedc2314a
ms.openlocfilehash: 1c03c02dde3178a257a83720ff437f7981f5f7ed
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68241551"
---
# <a name="tuplesize-class"></a>tuple_size-Klasse;

Ruft die Anzahl der Elemente in einem `tuple` ab.

## <a name="syntax"></a>Syntax

```cpp
// TEMPLATE STRUCT tuple_size
template <class Tuple>
   struct tuple_size;

// number of elements in array
template <class Elem, size_t Size>
   struct tuple_size<array<Elem, Size>>
      : integral_constant<size_t, Size>;

// size of pair
template <class T1, class T2>
   struct tuple_size<pair<T1, T2>>
      : integral_constant<size_t, 2>

// size of tuple
template <class... Types>
   struct tuple_size<tuple<Types...>>
      : integral_constant<size_t, sizeof...(Types)>;

// size of const tuple
template <class Tuple>
   struct tuple_size<const Tuple>;

// size of volatile tuple
template <class Tuple>
   struct tuple_size<volatile Tuple>;

// size of const volatile tuple
template <class Tuple>
   struct tuple_size<const volatile Tuple>;
```

```cpp
template <class T> inline constexpr size_t tuple_size_v = tuple_size<T>::value;
```

### <a name="parameters"></a>Parameter

*Tupel*\
Der Typ des Tupels.

*Elem*\
Der Typ der Arrayelemente.

*Größe*\
Die Größe des Arrays.

*T1*\
Der Typ des ersten Members des Paares.

*T2*\
Der Typ des zweiten Members des Paares.

*Typen*\
Die Typen der Elemente des Tupels.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse verfügt über einen Member `value` , ein ganzzahliger konstanter Ausdruck, dessen Wert dem Wertebereich des Tupeltyps *Tupel*.

Der vorlagenspezialisierung für Arrays verfügt über einen Member `value` , ein ganzzahliger konstanter Ausdruck, dessen Wert *Größe*, d.h. die Größe des Arrays.

Die Vorlagenspezialisierung für Paare verfügt über einen Member `value`, der ein ganzzahliger konstanter Ausdruck ist, dessen Wert 2 ist.

## <a name="example"></a>Beispiel

```cpp
#include <tuple>
#include <iostream>

using namespace std;

typedef tuple<int, double, int, double> MyTuple;
int main()
{
    MyTuple c0(0, 1.5, 2, 3.7);

    // display contents "0 1 2 3"
    cout << get<0>(c0);
    cout << " " << get<1>(c0);
    cout << " " << get<2>(c0);
    cout << " " << get<3>(c0) << endl;

    // display size "4"
    cout << " " << tuple_size<MyTuple>::value << endl;
}
```

```Output
0 1.5 2 3.7
4
```

## <a name="requirements"></a>Anforderungen

**Header:** \<tuple>

**Header:** \<array> (für Arrayspezialisierung)

**Header:** \<utility> (für Paarspezialisierung)

**Namespace:** std
