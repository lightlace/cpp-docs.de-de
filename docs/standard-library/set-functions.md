---
title: '&lt;set&gt;-Funktionen'
ms.date: 11/04/2016
f1_keywords:
- set/std::swap (map)
- set/std::swap (multiset)
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
ms.openlocfilehash: a3a63fb86caa3485b1ee14538c3eb1f1ff72923e
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246410"
---
# <a name="ltsetgt-functions"></a>&lt;set&gt;-Funktionen

## <a name="swap"></a> Swap (Map)

Tauscht die Elemente zweier Sätze aus.

```cpp
template <class Key, class Traits, class Allocator>
void swap(set<Key, Traits, Allocator>& left, set<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*Richting*\
Die Gruppe, in dem Elemente ausgetauscht werden sollen, oder die Menge, deren Elemente mit denen der Menge ausgetauscht werden sollen *linken*.

*Links*\
Die Menge, deren Elemente ausgetauscht werden, mit denen der Menge *rechten*.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion ist ein Algorithmus, spezialisiert auf die Container-Klasse, legen Sie auf die Ausführung der Memberfunktion `left.` [Swap](../standard-library/set-class.md#swap)(`right`). Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die spezialisierteste Version der Vorlagenfunktion aus. Die allgemeine Version der Vorlagenfunktion

`template` \< **classT**> **void swap**( **T&** , **T&** )

in der Algorithmusklasse funktioniert mittels Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.

### <a name="example"></a>Beispiel

Im Codebeispiel für die Memberklasse [set::swap](../standard-library/set-class.md#swap) finden Sie ein Beispiel für die Verwendung der Vorlagenversion `swap`.

## <a name="swap_multiset"></a> Swap (Multiset)

Tauscht die Elemente zweier Multisets aus.

```cpp
template <class Key, class Traits, class Allocator>
void swap(multiset<Key, Traits, Allocator>& left, multiset<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*Richting*\
Das Multiset, in dem die auszutauschenden Elemente oder das Multiset, dessen Elemente mit denen des Multisets ausgetauscht werden sollen *linken*.

*Links*\
Die Multiset, dessen Elemente ausgetauscht werden, mit denen des Multisets *rechten*.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion ist ein Algorithmus, spezialisiert auf die Container-Klasse Multimenge, führen Sie die Memberfunktion `left.` [Swap](../standard-library/multiset-class.md#swap)(`right`). Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die spezialisierteste Version der Vorlagenfunktion aus. Die allgemeine Version der Vorlagenfunktion

`template` \< **classT**> **void swap**( **T&** , **T&** )

in der Algorithmusklasse funktioniert mittels Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.

### <a name="example"></a>Beispiel

Im Codebeispiel für die Memberklasse [multiset::swap](../standard-library/multiset-class.md#swap) finden Sie ein Beispiel für die Verwendung der Vorlagenversion `swap`.
