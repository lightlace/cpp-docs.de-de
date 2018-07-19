---
title: '&lt;map&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- map/std::swap (map)
- map/std::swap (multimap)
ms.assetid: 7cb3d1a5-7add-4726-a73f-61927eafd466
ms.openlocfilehash: 3c6cb7d0308e4bafc531fe0baf0c5d666228c3ec
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966367"
---
# <a name="ltmapgt-functions"></a>&lt;map&gt;-Funktionen

|||
|-|-|
|[swap (map)](#swap)|[swap (multimap)](#swap_multimap)|

## <a name="swap_multimap"></a> swap (map)

Tauscht die Elemente zweier Zuordnungen aus.

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    map<Key, Traits, Compare, Alloctor>& left,
    map<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>Parameter

*richtige* der Karte, in dem Elemente ausgetauscht werden sollen, oder die Zuordnung, deren Elemente ausgetauscht werden, mit denen der Zuordnung *linken*.

*linken* die Zuordnung, deren Elemente ausgetauscht werden, mit denen der Zuordnung *rechten*.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion ist ein Algorithmus, spezialisiert auf die Container-Klasse-Karte, um die Ausführung der Memberfunktion `left`.[ Swap](../standard-library/map-class.md#swap)( `right`). Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die meist spezialisierte Version der Vorlagenfunktion. Die allgemeine Version der Vorlagenfunktion, **template** \< **class T**> **void swap**( **T&**, **T&**), in der Algorithmusklasse funktioniert per Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.

### <a name="example"></a>Beispiel

Im Codebeispiel für die Memberfunktion [map::swap](../standard-library/map-class.md#swap) finden Sie ein Beispiel, das die Vorlagenversion `swap` verwendet.

## <a name="swap"></a> swap (multimap)

Tauscht die Elemente zweier multimap-Objekte aus.

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    multimap<Key, Traits, Compare, Alloctor>& left,
    multimap<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>Parameter

*richtige* das multimap-Klasse, die Elemente ausgetauscht werden sollen, oder die multimap-Klasse, deren Elemente mit denen der mehrfachzuordnung ausgetauscht werden *linken*.

*linken* das multimap-Klasse, deren Elemente ausgetauscht werden, mit denen der mehrfachzuordnung *rechten*.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion ist ein Algorithmus, spezialisiert auf die Container, auf die Containerklasse "Multimap" zum Ausführen von der Memberfunktion auszuführen Map `left`.[ Swap](../standard-library/multimap-class.md#swap) (`right`). Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die meist spezialisierte Version der Vorlagenfunktion. Die allgemeine Version der Vorlagenfunktion, **template** \< **class T**> **void swap**( **T&**, **T&**), in der Algorithmusklasse funktioniert per Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.

### <a name="example"></a>Beispiel

Im Codebeispiel für die Memberfunktion [multimap::swap](../standard-library/multimap-class.md#swap) finden Sie ein Beispiel, das die Vorlagenversion `swap` verwendet.

## <a name="see-also"></a>Siehe auch

[\<map>](../standard-library/map.md)<br/>
