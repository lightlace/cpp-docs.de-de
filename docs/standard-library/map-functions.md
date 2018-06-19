---
title: '&lt;map&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- map/std::swap (map)
- map/std::swap (multimap)
ms.assetid: 7cb3d1a5-7add-4726-a73f-61927eafd466
ms.openlocfilehash: d6f62868d17cec9215b18451527c3a2e4e22b7f2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854921"
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

`right` Die Zuordnung, die die auszutauschenden Elemente bereitgestellt oder die Zuordnung, deren Elemente sind mit denen der Karte ausgetauscht werden sollen `left`.

`left` Die Zuordnung, deren Elemente sind mit denen der Karte ausgetauscht werden sollen `right`.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion ist ein Algorithmus für die Container-Klasse-Zuordnung, führen Sie die Memberfunktion spezialisierten `left`.[ Swap](../standard-library/map-class.md#swap)( `right`). Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die meist spezialisierte Version der Vorlagenfunktion. Die allgemeine Version der Vorlagenfunktion, **template** \< **class T**> **void swap**( **T&**, **T&**), in der Algorithmusklasse funktioniert per Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.

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

`right` Der mehrfachzuordnung Elemente ausgetauscht werden sollen, oder der mehrfachzuordnung zurück, dessen Elemente sind mit denen der mehrfachzuordnung ausgetauscht werden sollen `left`.

`left` Die mehrfachzuordnung zurück, dessen Elemente sind mit denen der mehrfachzuordnung spezifiziertes `right`.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion ist ein Algorithmus für die Container-Klasse-Zuordnung, führen Sie auf die Container-Klasse mehrfachzuordnung, führen Sie die Memberfunktion spezialisierten `left`.[ Swap](../standard-library/multimap-class.md#swap) ( `right`). Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die meist spezialisierte Version der Vorlagenfunktion. Die allgemeine Version der Vorlagenfunktion, **template** \< **class T**> **void swap**( **T&**, **T&**), in der Algorithmusklasse funktioniert per Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.

### <a name="example"></a>Beispiel

Im Codebeispiel für die Memberfunktion [multimap::swap](../standard-library/multimap-class.md#swap) finden Sie ein Beispiel, das die Vorlagenversion `swap` verwendet.

## <a name="see-also"></a>Siehe auch

[\<map>](../standard-library/map.md)<br/>
