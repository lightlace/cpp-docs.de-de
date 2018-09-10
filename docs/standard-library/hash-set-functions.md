---
title: '&lt;hash_set&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
ms.openlocfilehash: 5c96ac897d870e1f8dc153847797379b6720dc7b
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44103245"
---
# <a name="lthashsetgt-functions"></a>&lt;hash_set&gt; Funktionen

|||
|-|-|
|[swap](#swap)|[swap (hash_multiset)](#swap_hash_multiset)|

## <a name="swap"></a>  swap

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist [unordered_set-Klasse](../standard-library/unordered-set-class.md).

Tauscht die Elemente zweier hash_sets aus.

```cpp
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Hash_set-Objekt, in dem Elemente ausgetauscht werden sollen, oder das Hash_set, dessen Elemente ausgetauscht werden, mit denen des Hash_set *linken*.

*left*<br/>
Das Hash_set, dessen Elemente ausgetauscht werden, mit denen des Hash_set *rechten*.

### <a name="remarks"></a>Hinweise

Die `swap` Vorlagenfunktion ist ein Algorithmus, spezialisiert auf die Hash_set-Containerklasse für die Ausführung der Memberfunktion `left.` [Swap](../standard-library/hash-set-class.md#swap)(`right`). Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die spezialisierteste Version der Vorlagenfunktion aus. Die allgemeine Version der Vorlagenfunktion

**template \<class T> void swap(T&, T&),**

in der Algorithmusklasse funktioniert mittels Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.

### <a name="example"></a>Beispiel

Im Codebeispiel für die Memberklasse [hash_set::swap](../standard-library/hash-set-class.md#swap) finden Sie ein Beispiel, das die Vorlagenversion `swap` verwendet.

## <a name="swap_hash_multiset"></a> swap (hash_multiset)

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist [unordered_set-Klasse](../standard-library/unordered-set-class.md).

Tauscht die Elemente zweier hash_multisets aus.

```cpp
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Das hash_multiset-Objekt, in dem Elemente ausgetauscht werden sollen, oder das Hash_multiset, dessen Elemente ausgetauscht werden, mit denen des Hash_multiset *linken*.

*left*<br/>
Das Hash_multiset, dessen Elemente ausgetauscht werden, mit denen des Hash_multiset *rechten*.

### <a name="remarks"></a>Hinweise

Die `swap` Vorlagenfunktion ist ein Algorithmus, spezialisiert auf die Hash_multiset-Containerklasse für die Ausführung der Memberfunktion `left.` [Swap](../standard-library/hash-multiset-class.md#swap)(`right`). Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die spezialisierteste Version der Vorlagenfunktion aus. Die allgemeine Version der Vorlagenfunktion

**template \<class T> void swap(T&, T&),**

in der Algorithmusklasse funktioniert mittels Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.

### <a name="example"></a>Beispiel

Im Codebeispiel für die Memberklasse [hash_multiset::swap](../standard-library/hash-multiset-class.md#swap) finden Sie ein Beispiel, das die Vorlagenversion `swap` verwendet.

## <a name="see-also"></a>Siehe auch

[<hash_set>](../standard-library/hash-set.md)<br/>
