---
title: value_compare-Klasse (&lt;map&gt;) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- std::value_compare
- std.value_compare
- map/std::value_compare
- value_compare
dev_langs:
- C++
helpviewer_keywords:
- std::value_compare
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 134d364c38b30584b2f8c242cd824ea522bc9259
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
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

Die von `value_compare` bei einem Vergleich von **value_types** ganzer, in einer Zuordnung enthaltener Elemente bereitgestellten Vergleichskriterien werden von einem Vergleich der Schlüssel der jeweiligen Elemente durch die Erweiterungsklassenkonstruktion induziert. Der Operator der Memberfunktion verwendet das Objekt **comp** vom Typ `key_compare`, das in dem Funktionsobjekt gespeichert ist, das von `value_compare` für den Vergleich der Sortierschlüsselkomponenten von zwei Elementen bereitgestellt wird.

Bei Mengen und Multimengen, bei denen es sich um einfache Container handelt, bei denen die Schlüsselwerte mit den Elementwerten übereinstimmen, stimmt `value_compare` mit `key_compare` überein; bei Zuordnungen und Mehrfachzuordnungen nicht, da der Wert von Elementen vom Typ `pair` nicht mit dem Wert des Elementschlüssels identisch ist.

## <a name="example"></a>Beispiel

Im Beispiel für [value_comp](../standard-library/map-class.md#value_comp) wird verdeutlicht, wie `value_compare` deklariert und verwendet wird.

## <a name="requirements"></a>Anforderungen

**Header:** \<map>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[binary_function-Struktur](../standard-library/binary-function-struct.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
