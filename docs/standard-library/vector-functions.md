---
title: '&lt;vector&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vector/std::swap
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
helpviewer_keywords:
- std::swap [vector]
ms.openlocfilehash: c93f535bb02cbaa1f688fba84f15d832381156c6
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50079314"
---
# <a name="ltvectorgt-functions"></a>&lt;vector&gt;-Funktionen

## <a name="swap"></a>  swap

Tauscht die Elemente zweier Vektoren aus.

```cpp
template <class Type, class Allocator>
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Der Vektor Elemente ausgetauscht werden sollen, oder der Vektor, dessen Elemente ausgetauscht werden, mit denen des Vektors *linken*.

*left*<br/>
Der Vektor, dessen Elemente ausgetauscht werden, mit denen des Vektors *rechten*.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion ist ein Algorithmus, spezialisiert auf Container-Klasse Vector, führen Sie die Memberfunktion `left`. [Vector:: Swap](../standard-library/vector-class.md) *(rechts*). Hierbei handelt es sich um Instanzen der partiellen Sortierung von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die am meisten spezialisierte Version der Vorlagenfunktion. Die allgemeine Version der Vorlagenfunktion, **template** \< **class T**> **void swap**( **T&**, **T&**), in der Algorithmusklasse funktioniert per Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.

### <a name="example"></a>Beispiel

Im Codebeispiel für die Memberfunktion [vector::swap](../standard-library/vector-class.md) finden Sie ein Beispiel, in dem die Vorlagenversion `swap` verwendet wird.

## <a name="see-also"></a>Siehe auch

[\<vector>](../standard-library/vector.md)<br/>
