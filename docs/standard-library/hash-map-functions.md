---
title: '&lt;hash_map&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- hash_map/std::swap
- hash_map/std::swap (hash_map)
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
ms.openlocfilehash: 12ceb799ccf0944b8f0e8d48975da25c39f22505
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100949"
---
# <a name="lthashmapgt-functions"></a>&lt;Hash_map&gt; Funktionen

|||
|-|-|
|[swap](#swap)|[swap (hash_map)](#swap_hash_map)|

## <a name="swap_hash_map"></a> swap (hash_map)

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).

Tauscht die Elemente zweier hash_maps aus.

```cpp
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Das hash_map-Element, dessen Elemente sind mit denen der Zuordnung ausgetauscht werden sollen *linken*.

*left*<br/>
Das hash_map-Element, dessen Elemente sind mit denen der Zuordnung ausgetauscht werden sollen *rechten*.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion ist ein Algorithmus, der auf die Containerklasse „hash_map“ spezialisiert ist, um die Memberfunktion `left.` [swap](../standard-library/basic-ios-class.md#swap)*(right*) auszuführen. Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die spezialisierteste Version der Vorlagenfunktion. Die allgemeine Version der Vorlagenfunktion, **template \<class T> void swap (T& T&)**, in der Algorithmus-Headerdatei funktioniert per Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.

## <a name="swap"></a>  swap

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_multimap-Klasse](../standard-library/unordered-multimap-class.md).

Tauscht die Elemente zweier hash_multimaps aus.

```cpp
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Die Hash_multimap, deren Elemente ausgetauscht werden, mit denen der Zuordnung *linken*.

*left*<br/>
Die Hash_multimap, deren Elemente ausgetauscht werden, mit denen der Zuordnung *rechten*.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion ist ein Algorithmus, der auf die Containerklasse „hash_multimap“ spezialisiert ist, um die Memberfunktion `left.`[swap](../standard-library/hash-multimap-class.md#swap)*(right*`)`. auszuführen. Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die spezialisierteste Version der Vorlagenfunktion. Die allgemeine Version der Vorlagenfunktion, **template \<class T> void swap (T& T&)**, in der Algorithmus-Headerdatei funktioniert per Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.

## <a name="see-also"></a>Siehe auch

[<hash_map>](../standard-library/hash-map.md)<br/>
