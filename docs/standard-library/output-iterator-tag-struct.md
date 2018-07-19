---
title: output_iterator_tag-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xutility/std::output_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- output_iterator_tag class
- output_iterator_tag struct
ms.assetid: c23a4331-b069-4fa0-9c3a-1c9be7095553
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6130a6de2504f2a625677ceaac00d23bdbcd9372
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961083"
---
# <a name="outputiteratortag-struct"></a>output_iterator_tag-Struktur

Eine Klasse, die einen Rückgabetyp für eine `iterator_category` -Funktion, die einen Ausgabeiterator darstellt.

## <a name="syntax"></a>Syntax

Struktur Output_iterator_tag {};

## <a name="remarks"></a>Hinweise

Die Kategorietagklassen werden als Kompiliertags für die Auswahl des Algorithmus verwendet. Die Vorlagenfunktion muss herausfinden, welche die spezifischste Kategorie ihres Iteratorarguments ist, um zur Kompilierzeit den effizientesten Algorithmus verwenden zu können. Für jeden Iterator des Typs `Iterator` muss `iterator_traits`< `Iterator`> **::iterator_category** definiert werden, um das spezifischste Kategorietag zu werden, das das Iteratorverhalten beschreibt.

Der Typ ist identisch mit **Iterator** \< **Iter**> **:: Iterator_category** beim `Iter` beschreibt ein Objekt, das als dienen kann ein der Ausgabeiterator.

Dieses Tag ist nicht auf die `value_type` oder `difference_type` für den Iterator parametrisiert, wie bei anderen Iteratortags, da Ausgabe -Iteratoren nicht entweder `value_type` oder `difference_type` haben.

## <a name="example"></a>Beispiel

Finden Sie unter [Iterator_traits](../standard-library/iterator-traits-struct.md) oder [Random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) ein Beispiel zur Verwendung für `iterator_tag`s.

## <a name="requirements"></a>Anforderungen

**Header:** \<iterator>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
