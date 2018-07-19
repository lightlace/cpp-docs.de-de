---
title: bidirectional_iterator_tag-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xutility/std::bidirectional_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- bidirectional_iterator_tag class
- bidirectional_iterator_tag struct
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a04265a68a03edc9f957161991d2ddd91a8e6096
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958178"
---
# <a name="bidirectionaliteratortag-struct"></a>bidirectional_iterator_tag-Struktur

Eine Klasse, die einen Rückgabetyp für eine `iterator_category` -Funktion, die einen bidirektionalen Iterator darstellt.

## <a name="syntax"></a>Syntax

```cpp
struct bidirectional_iterator_tag    : public forward_iterator_tag {};
```

## <a name="remarks"></a>Hinweise

Die Kategorietagklassen werden als Kompiliertags für die Auswahl des Algorithmus verwendet. Die Vorlagenfunktion muss herausfinden, welche die spezifischste Kategorie ihres Iteratorarguments ist, um zur Kompilierzeit den effizientesten Algorithmus verwenden zu können. Für jeden Iterator des Typs `Iterator` muss `iterator_traits`< `Iterator`>::**iterator_category** definiert werden, um das spezifischste Kategorietag zu sein, das das Iteratorverhalten beschreibt.

Der Typ ist identisch mit **Iterator** \< **Iter**>:: **Iterator_category** beim `Iter` beschreibt ein Objekt, das als eine bidirektionale dienen kann Iterator.

## <a name="example"></a>Beispiel

Unter [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) finden Sie ein Beispiel zur Verwendung von `bidirectional_iterator_tag`.

## <a name="requirements"></a>Anforderungen

**Header:** \<iterator>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[forward_iterator_tag-Struktur](../standard-library/forward-iterator-tag-struct.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
