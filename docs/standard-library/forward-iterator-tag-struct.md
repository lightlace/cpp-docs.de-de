---
title: forward_iterator_tag-Struktur
ms.date: 11/04/2016
f1_keywords:
- xutility/std::forward_iterator_tag
helpviewer_keywords:
- forward_iterator_tag struct
- forward_iterator_tag class
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
ms.openlocfilehash: 687e39ce752bc0d4d289421887570dea6870f8f3
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457122"
---
# <a name="forwarditeratortag-struct"></a>forward_iterator_tag-Struktur

Eine Klasse, die einen Rückgabetyp für eine **iterator_category**-Funktion bereitstellt, die einen Forward-Iterator darstellt.

## <a name="syntax"></a>Syntax

```cpp
struct forward_iterator_tag    : public input_iterator_tag {};
```

## <a name="remarks"></a>Hinweise

Die Tagklassen von Kategorien werden als Kompiliertags für die Auswahl des Algorithmus verwendet. Die Vorlagenfunktion muss herausfinden, welche die spezifischste Kategorie ihres Iteratorarguments ist, um zur Kompilierzeit das effizienteste Argument verwenden zu können. Für jeden Iterator des Typs `Iterator` muss `iterator_traits`< `Iterator`>  **::iterator_category** definiert werden, um das spezifischste Kategorietag zu werden, das das Iteratorverhalten beschreibt.

Der Typ ist identisch mit **iterator**\< **Iter**>  **::iterator_category**, wenn **Iter** ein Objekt beschreibt, das als Forward-Iterator verwendet werden kann.

## <a name="example"></a>Beispiel

Ein Beispiel zur Verwendung der **iterator_tags** finden Sie unter [iterator_traits](../standard-library/iterator-traits-struct.md) oder [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md).

## <a name="requirements"></a>Anforderungen

**Header:** \<iterator>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[input_iterator_tag-Struktur](../standard-library/input-iterator-tag-struct.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)
