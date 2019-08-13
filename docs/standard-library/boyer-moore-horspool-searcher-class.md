---
title: boyer_moore_horspool_searcher-Klasse
ms.date: 08/03/2019
f1_keywords:
- functional/std::boyer_moore_horspool_searcher
helpviewer_keywords:
- std::boyer_moore_horspool_searcher [C++]
ms.openlocfilehash: c7d24fee4a47fc588b00e527594682f1c4aadf76
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957158"
---
# <a name="boyer_moore_horspool_searcher-class"></a>boyer_moore_horspool_searcher-Klasse

Die `boyer_moore_horspool_searcher` -Klasse ist ein Funktions Objekttyp, der den Boyer-Moore-Horspool-Algorithmus verwendet, um nach einer Sequenz zu suchen, die im Konstruktor des-Objekts angegeben ist. Die Suche erfolgt innerhalb einer anderen Sequenz, die für den Funktions Aufrufoperator des Objekts bereitgestellt wird. Diese Klasse wird als Parameter an eine der über Ladungen von " [Std:: Search](algorithm-functions.md#search)" übergeben.

## <a name="syntax"></a>Syntax

```cpp
template <
    class RandomAccessIterator,
    class Hash = hash<typename iterator_traits<RandomAccessIterator>::value_type>,
    class BinaryPredicate = equal_to<>>
class boyer_moore_horspool_searcher
{
    boyer_moore_horspool_searcher(
        RandomAccessIterator pat_first,
        RandomAccessIterator pat_last,
        Hash hf = Hash(),
        BinaryPredicate pred = BinaryPredicate());

    template <class RandomAccessIterator2>
    pair<RandomAccessIterator2, RandomAccessIterator2> operator()(
        RandomAccessIterator2 first,
        RandomAccessIterator2 last) const;
};
```

## <a name="members"></a>Member

| | |
| - | - |
| **Konstruktor** | |
| [boyer_moore_horspool_searcher](#boyer-moore-horspool-searcher-constructor) | |
| **Operatoren** | |
| [Operator()](#operator-call) | |

## <a name="boyer-moore-horspool-searcher-constructor"></a>boyer_moore_horspool_searcher-Konstruktor

Erstellt ein `boyer_moore_horspool_searcher` Funktions Objekt, indem die zu suchende Sequenz, ein Hash Funktions Objekt und ein Gleichheits Prädikat verwendet werden.

```cpp
boyer_moore_horspool_searcher(
    RandomAccessIterator pat_first,
    RandomAccessIterator pat_last,
    Hash hf = Hash(),
    BinaryPredicate pred = BinaryPredicate());
```

### <a name="parameters"></a>Parameter

*pat_first*\
Das ursprüngliche Element der Sequenz, nach der gesucht werden soll.

*pat_last*\
Das Ende der Sequenz, nach der gesucht werden soll.

*HF*\
Ein Aufruf bares Objekt, das zum Hash der Sequenz Elemente verwendet wird.

*pred*\
Das optionale Gleichheits Vergleichs Prädikat für Sequenz Elemente. Wenn kein Gleichheits Vergleichstyp angegeben wird, ist `std::equal_to`der Standardwert.

### <a name="remarks"></a>Hinweise

Löst eine beliebige Ausnahme aus, die vom Kopierkonstruktor der Typen *BinaryPredicate*, *Hash*oder *RandomAccessIterator* ausgelöst wird, oder den calloperator von *BinaryPredicate* oder *Hash*.

Diese Klasse ist neu in c++ 17.

## <a name="operator-call"></a>Operator ()

Der calloperator des Funktions Objekts. Sucht innerhalb der Argument Sequenz `[first, last)` nach der Sequenz, die für den Konstruktor angegeben wird.

```cpp
template <class ForwardIterator2>   // C++17
pair<RandomAccessIterator2, RandomAccessIterator2> operator()(
    RandomAccessIterator2 first,
    RandomAccessIterator2 last) const;
```

### <a name="parameters"></a>Parameter

*erstes*\
Das ursprüngliche Element der Sequenz, in der gesucht werden soll.

*letzten*\
Das Ende der Sequenz, in der gesucht werden soll.

### <a name="remarks"></a>Hinweise

Wenn das Suchmuster `[pat_first, pat_last)` leer ist, wird `make_pair(first, first)`zurückgegeben. Wenn das Suchmuster nicht gefunden wird, `make_pair(last, last)`wird zurückgegeben. Andernfalls wird ein paar von Iteratoren an den Anfang und das Ende einer Sequenz in `[first, last)` zurückgegeben, das `[pat_first, pat_last)` entsprechend der Prädikat- *präd*gleich ist.

Diese Klasse ist neu in c++ 17.

## <a name="see-also"></a>Siehe auch

[\<functional>](functional.md)\
[algorithmusfunktionen](algorithm-functions.md)\
[boyer_moore_searcher-Klasse](boyer-moore-searcher-class.md)\
[Std:: Search](algorithm-functions.md#search)
