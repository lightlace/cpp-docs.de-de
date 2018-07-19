---
title: '&lt;set&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- set/std::swap (map)
- set/std::swap (multiset)
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
ms.openlocfilehash: b25194dc1cdc45bc93d9e5188715e3ea01258af4
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966331"
---
# <a name="ltsetgt-functions"></a>&lt;set&gt;-Funktionen

|||
|-|-|
|[swap (map)](#swap)|[swap (multiset)](#swap_multiset)|

## <a name="swap"></a> swap (map)

Tauscht die Elemente zweier Sätze aus.

```cpp
template <class Key, class Traits, class Allocator>
void swap(set<Key, Traits, Allocator>& left, set<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*richtige* die Menge, die auszutauschenden Elemente bereitgestellt, oder die Menge, deren Elemente ausgetauscht werden, mit denen der Menge *linken*.

*linken* die Menge, deren Elemente ausgetauscht werden, mit denen der Menge *rechten*.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion ist ein Algorithmus, spezialisiert auf die Container-Klasse, legen Sie auf die Ausführung der Memberfunktion `left.` [Swap](../standard-library/set-class.md#swap)(`right`). Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die spezialisierteste Version der Vorlagenfunktion aus. Die allgemeine Version der Vorlagenfunktion

`template` \< **classT**> **void swap**( **T&**, **T&**)

in der Algorithmusklasse funktioniert mittels Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.

### <a name="example"></a>Beispiel

Im Codebeispiel für die Memberklasse [set::swap](../standard-library/set-class.md#swap) finden Sie ein Beispiel für die Verwendung der Vorlagenversion `swap`.

## <a name="swap_multiset"></a> swap (multiset)

Tauscht die Elemente zweier Multisets aus.

```cpp
template <class Key, class Traits, class Allocator>
void swap(multiset<Key, Traits, Allocator>& left, multiset<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*richtige* das Multiset, in dem die auszutauschenden Elemente oder das Multiset, dessen Elemente mit denen des Multisets ausgetauscht werden sollen *linken*.

*linken* die Multiset, dessen Elemente ausgetauscht werden, mit denen des Multisets *rechten*.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion ist ein Algorithmus, spezialisiert auf die Container-Klasse Multimenge, führen Sie die Memberfunktion `left.` [Swap](../standard-library/multiset-class.md#swap)(`right`). Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die spezialisierteste Version der Vorlagenfunktion aus. Die allgemeine Version der Vorlagenfunktion

`template` \< **classT**> **void swap**( **T&**, **T&**)

in der Algorithmusklasse funktioniert mittels Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.

### <a name="example"></a>Beispiel

Im Codebeispiel für die Memberklasse [multiset::swap](../standard-library/multiset-class.md#swap) finden Sie ein Beispiel für die Verwendung der Vorlagenversion `swap`.

## <a name="see-also"></a>Siehe auch

[\<set>](../standard-library/set.md)<br/>
