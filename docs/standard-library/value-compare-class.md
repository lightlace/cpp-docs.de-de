---
title: value_compare-Klasse
ms.date: 11/04/2016
f1_keywords:
- value_compare
helpviewer_keywords:
- value_compare class
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
ms.openlocfilehash: 0e057a6229c903402a51b34a8f4e844e80ace187
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452374"
---
# <a name="valuecompare-class"></a>value_compare-Klasse

Stellt ein Funktionsobjekt bereit, das die Elemente einer hash_map vergleichen kann, indem die Werte ihrer Schlüssel verglichen werden, um deren relative Reihenfolge in der hash_map zu bestimmen.

## <a name="syntax"></a>Syntax

```cpp
class value_compare
    : std::public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(
        const value_type& left,
        const value_type& right) const
    {
        return (comp(left.first, right.first));
    }

protected:
    value_compare(const key_compare& c) : comp (c) { }
    key_compare comp;
};
```

## <a name="remarks"></a>Hinweise

Die von Value_compare bereitgestellten Vergleichskriterien `value_types` zwischen den vollständigen Elementen in einer hash_map werden von einem Vergleich zwischen den Schlüsseln der entsprechenden Elemente durch die Erweiterung der Erweiterungs Klasse verursacht. Der Member-Funktions Operator verwendet das `comp` -Objekt `key_compare` vom Typ, das im von Value_compare bereitgestellten Funktions Objekt gespeichert ist, um die Sortierschlüssel Komponenten von zwei Elementen zu vergleichen.

Bei hash_sets und hash_multisets, bei denen es sich um einfache Container handelt, bei denen die Schlüsselwerte mit den Elementwerten übereinstimmen, stimmt value_compare mit `key_compare` überein; bei hash_maps und hash_multimaps nicht, da der Wert von Elementen vom Typ `pair` nicht mit dem Wert des Elementschlüssels identisch ist.

## <a name="example"></a>Beispiel

Im Beispiel für [hash_map::value_comp](../standard-library/hash-map-class.md#value_comp) wird verdeutlicht, wie value_compare deklariert und verwendet wird.

## <a name="requirements"></a>Anforderungen

**Header:** \<hash_map>

**Namespace:** stdext

## <a name="see-also"></a>Siehe auch

[binary_function Struct (binary_function-Struktur)](../standard-library/binary-function-struct.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)
