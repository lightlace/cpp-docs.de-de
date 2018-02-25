---
title: '&lt;map&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- map/std::swap (map)
- map/std::swap (multimap)
ms.assetid: 7cb3d1a5-7add-4726-a73f-61927eafd466
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 29fa327fe892cba8c7cd9d9f4f428baa130ded29
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ltmapgt-functions"></a>&lt;map&gt;-Funktionen
|||  
|-|-|  
|[swap (map)](#swap)|[swap (multimap)](#swap_multimap)|  
  
##  <a name="swap_multimap"></a> swap (map)
 Tauscht die Elemente zweier Zuordnungen aus.  
  
```  
template <class key, class T, class _Pr, class _Alloc>  
void swap(
    map<Key, Traits, Compare, Alloctor>& left,  
    map<Key, Traits, Compare, Alloctor>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Die Zuordnung, in der die auszutauschenden Elemente bereitgestellt werden, oder die Zuordnung, deren Elemente mit denen der Zuordnung `left` ausgetauscht werden sollen.  
  
 `left`  
 Die Zuordnung, deren Elemente mit denen der Zuordnung `right` ausgetauscht werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion ist ein Algorithmus für die Container-Klasse-Zuordnung, führen Sie die Memberfunktion spezialisierten `left`.[ Swap](../standard-library/map-class.md#swap)( `right`). Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die meist spezialisierte Version der Vorlagenfunktion. Die allgemeine Version der Vorlagenfunktion, **template** \< **class T**> **void swap**( **T&**, **T&**), in der Algorithmusklasse funktioniert per Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.  
  
### <a name="example"></a>Beispiel  
  Im Codebeispiel für die Memberfunktion [map::swap](../standard-library/map-class.md#swap) finden Sie ein Beispiel, das die Vorlagenversion `swap` verwendet.  
  
##  <a name="swap"></a> swap (multimap)
 Tauscht die Elemente zweier multimap-Objekte aus.  
  
```  
template <class key, class T, class _Pr, class _Alloc>  
void swap(
    multimap<Key, Traits, Compare, Alloctor>& left,  
    multimap<Key, Traits, Compare, Alloctor>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Die multimap-Klasse, in der die auszutauschenden Elemente bereitgestellt werden, oder die multimap-Klasse, deren Elemente mit denen des multimap-Objekts `left` ausgetauscht werden sollen.  
  
 `left`  
 Die multimap-Klasse, deren Elemente mit denen des multimap-Parameters `right` ausgetauscht werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion ist ein Algorithmus für die Container-Klasse-Zuordnung, führen Sie auf die Container-Klasse mehrfachzuordnung, führen Sie die Memberfunktion spezialisierten `left`.[ Swap](../standard-library/multimap-class.md#swap) ( `right`). Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die meist spezialisierte Version der Vorlagenfunktion. Die allgemeine Version der Vorlagenfunktion, **template** \< **class T**> **void swap**( **T&**, **T&**), in der Algorithmusklasse funktioniert per Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.  
  
### <a name="example"></a>Beispiel  
  Im Codebeispiel für die Memberfunktion [multimap::swap](../standard-library/multimap-class.md#swap) finden Sie ein Beispiel, das die Vorlagenversion `swap` verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [\<map>](../standard-library/map.md)
