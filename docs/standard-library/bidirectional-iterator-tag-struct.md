---
title: bidirectional_iterator_tag-Struktur
ms.date: 11/04/2016
f1_keywords:
- xutility/std::bidirectional_iterator_tag
helpviewer_keywords:
- bidirectional_iterator_tag class
- bidirectional_iterator_tag struct
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
ms.openlocfilehash: bab2664fcb552a72baa032d719cf6b0141ffe525
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456638"
---
# <a name="bidirectionaliteratortag-struct"></a>bidirectional_iterator_tag-Struktur

Eine Klasse, die einen Rückgabetyp für `iterator_category` eine Funktion bereitstellt, die einen bidirektionalen Iterator darstellt

## <a name="syntax"></a>Syntax

```cpp
struct bidirectional_iterator_tag    : public forward_iterator_tag {};
```

## <a name="remarks"></a>Hinweise

Die Kategorietagklassen werden als Kompiliertags für die Auswahl des Algorithmus verwendet. Die Vorlagenfunktion muss herausfinden, welche die spezifischste Kategorie ihres Iteratorarguments ist, um zur Kompilierzeit den effizientesten Algorithmus verwenden zu können. Für jeden Iterator des Typs `Iterator` muss `iterator_traits`< `Iterator`>::**iterator_category** definiert werden, um das spezifischste Kategorietag zu sein, das das Iteratorverhalten beschreibt.

Der-Typ ist identisch mit **Iterator** \< **ITER**>:: **Iterator_category** , `Iter` wenn ein Objekt beschreibt, das als bidirektionaler Iterator fungieren kann.

## <a name="example"></a>Beispiel

Unter [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) finden Sie ein Beispiel zur Verwendung von `bidirectional_iterator_tag`.

## <a name="requirements"></a>Anforderungen

**Header:** \<iterator>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[forward_iterator_tag-Struktur](../standard-library/forward-iterator-tag-struct.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)
