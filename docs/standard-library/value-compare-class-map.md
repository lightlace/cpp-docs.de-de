---
title: value_compare-Klasse (&lt;map&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::value_compare
- std.value_compare
- map/std::value_compare
- value_compare
helpviewer_keywords:
- std::value_compare
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
ms.openlocfilehash: d098e947aec1ea543f29c168a632d1f4c9412e82
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448324"
---
# <a name="valuecompare-class-ltmapgt"></a>value_compare-Klasse (&lt;map&gt;)

Stellt ein Funktionsobjekt bereit, das die Elemente einer Zuordnung vergleichen kann, indem die Werte ihrer Schlüssel verglichen werden, um deren relative Reihenfolge in der Zuordnung zu bestimmen.

## <a name="syntax"></a>Syntax

```cpp
class value_compare : public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(const value_type& left, const value_type& right) const;
    value_compare(key_compare pred) : comp(pred);
protected:
    key_compare comp;
};
```

## <a name="remarks"></a>Hinweise

Das Vergleichskriterium, das `value_compare` von `value_types` der zwischen Zahl ganzer Elemente in einer Zuordnung bereitgestellt wird, wird von einem Vergleich zwischen den Schlüsseln der entsprechenden Elemente durch die Erweiterung der Erweiterungs Klasse verursacht. Der Member-Funktions Operator verwendet das `comp` -Objekt `key_compare` des Typs, das in dem von `value_compare` bereitgestellten Funktions Objekt gespeichert ist, um die Sortierschlüssel Komponenten von zwei Elementen zu vergleichen.

Bei Mengen und Multimengen, bei denen es sich um einfache Container handelt, bei denen die Schlüsselwerte mit den Elementwerten übereinstimmen, stimmt `value_compare` mit `key_compare` überein; bei Zuordnungen und Mehrfachzuordnungen nicht, da der Wert von Elementen vom Typ `pair` nicht mit dem Wert des Elementschlüssels identisch ist.

## <a name="example"></a>Beispiel

Im Beispiel für [value_comp](../standard-library/map-class.md#value_comp) wird verdeutlicht, wie `value_compare` deklariert und verwendet wird.

## <a name="requirements"></a>Anforderungen

**Header:** \<map>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[binary_function Struct (binary_function-Struktur)](../standard-library/binary-function-struct.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)
