---
title: input_iterator_tag-Struktur
ms.date: 11/04/2016
f1_keywords:
- xutility/std::input_iterator_tag
helpviewer_keywords:
- input_iterator_tag class
- input_iterator_tag struct
ms.assetid: ad68a4c6-f315-4ce1-8b74-c1fc71bd1577
ms.openlocfilehash: 47e0d08f79cfa41c414ac4fcd570ce8fdfbd0b35
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455315"
---
# <a name="inputiteratortag-struct"></a>input_iterator_tag-Struktur

Eine Klasse, die einen Rückgabetyp für `iterator_category` eine Funktion bereitstellt, die einen eingabeiterator darstellt

## <a name="syntax"></a>Syntax

Struktur Input_iterator_tag {};

## <a name="remarks"></a>Hinweise

Die Kategorietagklassen werden als Kompiliertags für die Auswahl des Algorithmus verwendet. Die Vorlagenfunktion muss herausfinden, welche die spezifischste Kategorie ihres Iteratorarguments ist, um zur Kompilierzeit den effizientesten Algorithmus verwenden zu können. Für jeden Iterator des Typs `Iterator` muss `iterator_traits`< `Iterator`>  **::iterator_category** definiert werden, um das spezifischste Kategorietag zu werden, das das Iteratorverhalten beschreibt.

Der Typ ist identisch mit **Iterator** \< **ITER**>  **:: Iterator_category** , wenn `Iter` ein Objekt beschreibt, das als eingabeiterator fungieren kann.

## <a name="example"></a>Beispiel

Ein Beispiel für [](../standard-library/random-access-iterator-tag-struct.md) die Verwendung `iterator_tag`von s finden Sie unter [Iterator_traits](../standard-library/iterator-traits-struct.md) oder Random_access_iterator_tag.

## <a name="requirements"></a>Anforderungen

**Header:** \<iterator>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)
