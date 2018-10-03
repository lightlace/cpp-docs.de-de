---
title: value_compare-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- value_compare
dev_langs:
- C++
helpviewer_keywords:
- value_compare class
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a3be65e867c243bd6a32dd35dd3128872a1f8d1
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234111"
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

Die von Value_compare bereitgestellten Vergleichskriterien `value_types` ganzer, in einer Hash_map enthaltener Elemente durch einen Vergleich der Schlüssel der jeweiligen Elemente durch die erweiterungsklassenkonstruktion induziert ausgelöst wird. Operator der Memberfunktion verwendet das Objekt `comp` des Typs `key_compare` gespeichert, in dem Funktionsobjekt, das von Value_compare für den Vergleich der sortierschlüsselkomponenten von zwei Elementen bereitgestellt.

Bei hash_sets und hash_multisets, bei denen es sich um einfache Container handelt, bei denen die Schlüsselwerte mit den Elementwerten übereinstimmen, stimmt value_compare mit `key_compare` überein; bei hash_maps und hash_multimaps nicht, da der Wert von Elementen vom Typ `pair` nicht mit dem Wert des Elementschlüssels identisch ist.

## <a name="example"></a>Beispiel

Im Beispiel für [hash_map::value_comp](../standard-library/hash-map-class.md#value_comp) wird verdeutlicht, wie value_compare deklariert und verwendet wird.

## <a name="requirements"></a>Anforderungen

**Header:** \<hash_map>

**Namespace:** stdext

## <a name="see-also"></a>Siehe auch

[binary_function-Struktur](../standard-library/binary-function-struct.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
