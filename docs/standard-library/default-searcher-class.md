---
title: default_searcher-Klasse
ms.date: 08/03/2019
f1_keywords:
- functional/std::default_searcher
helpviewer_keywords:
- std::default_searcher [C++]
ms.openlocfilehash: f2b1fe83b5223bbb60e9e32149c101e6379f93c3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "68268822"
---
# <a name="default_searcher-class"></a>default_searcher-Klasse

Ein `default_searcher` ist ein Funktions Objekttyp für Vorgänge, die nach einer im Konstruktor des Objekts angegebenen Sequenz suchen. Die Suche erfolgt innerhalb einer anderen Sequenz, die für den Funktions Aufrufoperator des Objekts bereitgestellt wird. Ruft Std [:: Search](algorithm-functions.md#search) auf, um die Suche auszuführen. `default_searcher`

## <a name="syntax"></a>Syntax

```cpp
template <class ForwardIterator, class BinaryPredicate = equal_to<>>
class default_searcher
{
    default_searcher(
        ForwardIterator pat_first,
        ForwardIterator pat_last,
        BinaryPredicate pred = BinaryPredicate());

    template <class ForwardIterator2>
    pair<ForwardIterator2, ForwardIterator2> operator()(
        ForwardIterator2 first,
        ForwardIterator2 last) const;
};
```

## <a name="members"></a>Member

| | |
| - | - |
| **Konstruktor** | |
| [default_searcher](#default-searcher-constructor) | |
| **Operatoren** | |
| [Operator()](#operator-call) | |

## <a name="default-searcher-constructor"></a>default_searcher-Konstruktor

Erstellt ein `default_searcher` Funktions Objekt, indem die zu suchende Sequenz und ein Gleichheits Prädikat verwendet werden.

```cpp
default_searcher(                   // C++17
    ForwardIterator pat_first,
    ForwardIterator pat_last,
    BinaryPredicate pred = BinaryPredicate());

constexpr default_searcher(         // C++20
    ForwardIterator pat_first,
    ForwardIterator pat_last,
    BinaryPredicate pred = BinaryPredicate());
```

### <a name="parameters"></a>Parameter

*pat_first*\
Das ursprüngliche Element der Sequenz, nach der gesucht werden soll.

*pat_last*\
Das Ende der Sequenz, nach der gesucht werden soll.

*pred*\
Das optionale Gleichheits Vergleichs Prädikat für Sequenz Elemente. Wenn kein Gleichheits Vergleichstyp angegeben wird, ist `std::equal_to`der Standardwert.

### <a name="remarks"></a>Hinweise

Löst eine beliebige Ausnahme aus, die vom Kopierkonstruktor der Typen *BinaryPredicate* oder *ForwardIterator* ausgelöst wird.

Diese Klasse ist neu in c++ 17. C++ 20 hat den Konstruktor `constexpr`erstellt.

## <a name="operator-call"></a>Operator ()

Der calloperator des Funktions Operators. Sucht innerhalb der Argument Sequenz `[first, last)` nach der Sequenz, die für den Konstruktor angegeben wird.

```cpp
template <class ForwardIterator2>   // C++17
pair<ForwardIterator2, ForwardIterator2> operator()(
    ForwardIterator2 first,
    ForwardIterator2 last) const;

template <class ForwardIterator2>   // C++20
constexpr pair<ForwardIterator2, ForwardIterator2> operator()(
    ForwardIterator2 first,
    ForwardIterator2 last) const;
```

### <a name="parameters"></a>Parameter

*erstes*\
Das ursprüngliche Element der Sequenz, in der gesucht werden soll.

*letzten*\
Das Ende der Sequenz, in der gesucht werden soll.

### <a name="remarks"></a>Hinweise

Gibt ein Paar von Iteratoren zurück. Der anfängliche Iterator *i* ist das effektive Ergebnis von:

`std::search( first, last, pat_first, pat_last, pred )`

Der zweite Iterator des Paars ist " *Last* ", wenn " *i**" der *Letzte*Wert ist. Andernfalls ist dies das effektive Ergebnis von:

`std::next( i, std::distance( pat_first, pat_last ))`

Diese Klasse ist neu in c++ 17. C++ 20 hat den-Operator `constexpr`aufgerufen.

## <a name="see-also"></a>Siehe auch

[\<functional>](functional.md)\
[algorithmusfunktionen](algorithm-functions.md)\
[Std:: Search](algorithm-functions.md#search)
