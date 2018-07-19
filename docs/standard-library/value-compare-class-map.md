---
title: value_compare-Klasse (&lt;map&gt;) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 46f8d00877aa4147e4b3e4ec2a6a23b70d8154c8
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965847"
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

Die gebotenen Vergleichskriterium `value_compare` zwischen `value_types` ganzer von einer Zuordnung enthaltener Elemente durch einen Vergleich der Schlüssel der jeweiligen Elemente durch die erweiterungsklassenkonstruktion induziert ausgelöst wird. Operator der Memberfunktion verwendet das Objekt `comp` des Typs `key_compare` gespeichert, in dem Funktionsobjekt gebotenen `value_compare` zum Vergleich der sortierschlüsselkomponenten von zwei Elementen.

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
