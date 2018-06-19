---
title: '&lt;hash_set&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
ms.openlocfilehash: 083d928198d8d83d8a56d8a74a6204e94c86aa67
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33846284"
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

`right` Hash_set-Objekt die auszutauschenden Elemente bereitgestellt oder hash_set-Objekt, dessen Elemente sind mit denen der Hash_set ausgetauscht werden sollen `left`.

`left` Hash_set-Objekt, dessen Elemente sind mit denen der Hash_set ausgetauscht werden sollen `right`.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion `swap` ist ein Algorithmus, der auf die Containerklasse „hash_set“ spezialisiert ist, um die Memberfunktion `left.`[swap](../standard-library/hash-set-class.md#swap)( `right`) auszuführen. Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die spezialisierteste Version der Vorlagenfunktion aus. Die allgemeine Version der Vorlagenfunktion

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

`right` Hash_multiset-Objekt die auszutauschenden Elemente bereitgestellt oder hash_multiset-Objekt, dessen Elemente sind mit denen der Hash_multiset ausgetauscht werden sollen `left`.

`left` Hash_multiset-Objekt, dessen Elemente sind mit denen der Hash_multiset ausgetauscht werden sollen `right`.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion `swap` ist ein Algorithmus, der auf die Containerklasse „hash_multiset“ spezialisiert ist, um die Memberfunktion `left.`[swap](../standard-library/hash-multiset-class.md#swap)( `right`) auszuführen. Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die spezialisierteste Version der Vorlagenfunktion aus. Die allgemeine Version der Vorlagenfunktion

**template \<class T> void swap(T&, T&),**

in der Algorithmusklasse funktioniert mittels Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.

### <a name="example"></a>Beispiel

Im Codebeispiel für die Memberklasse [hash_multiset::swap](../standard-library/hash-multiset-class.md#swap) finden Sie ein Beispiel, das die Vorlagenversion `swap` verwendet.

## <a name="see-also"></a>Siehe auch

[<hash_set>](../standard-library/hash-set.md)<br/>
