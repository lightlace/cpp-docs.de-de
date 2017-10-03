---
title: '&lt;hash_map&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- hash_map/std::swap
- hash_map/std::swap (hash_map)
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
caps.latest.revision: 9
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 43c9501c49f59ec4b6949c75b294d3cd6012dde0
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="lthashmapgt-functions"></a>&lt;Hash_map&gt; Funktionen
|||  
|-|-|  
|[swap](#swap)|[swap (hash_map)](#swap_hash_map)|  
  
##  <a name="swap_hash_map"></a> swap (hash_map)  
  
> [!NOTE]
>  Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).  
  
 Tauscht die Elemente zweier hash_maps aus.  
  
```
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Die hash_map, deren Elemente mit denen der Zuordnung `left` ausgetauscht werden sollen.  
  
 `left`  
 Die hash_map, deren Elemente mit denen der Zuordnung `right` ausgetauscht werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion ist ein Algorithmus, der auf die Containerklasse „hash_map“ spezialisiert ist, um die Memberfunktion `left.` [swap](../standard-library/basic-ios-class.md#swap)*(right*) auszuführen. Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die spezialisierteste Version der Vorlagenfunktion. Die allgemeine Version der Vorlagenfunktion, **template \<class T> void swap (T& T&)**, in der Algorithmus-Headerdatei funktioniert per Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse genutzt werden kann.  
  
 In Visual C++ .NET 2003 sind Member der [<hash_map>](../standard-library/hash-map.md)- und [<hash_set>](../standard-library/hash-set.md)-Headerdateien nicht mehr im STD-Namespace enthalten. Sie wurden stattdessen in den stdext-Namespace verschoben. Weitere Informationen finden Sie unter [Der stdext-Namespace](../standard-library/stdext-namespace.md).  
  
##  <a name="swap"></a> swap  
  
> [!NOTE]
>  Diese API ist veraltet. Die Alternative ist die [unordered_multimap-Klasse](../standard-library/unordered-multimap-class.md).  
  
 Tauscht die Elemente zweier hash_multimaps aus.  
  
```
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Die hash_multimap, deren Elemente mit denen der Zuordnung `left` ausgetauscht werden sollen.  
  
 `left`  
 Die hash_multimap, deren Elemente mit denen der Zuordnung `right` ausgetauscht werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion ist ein Algorithmus, der auf die Containerklasse „hash_multimap“ spezialisiert ist, um die Memberfunktion `left.`[swap](../standard-library/hash-multimap-class.md#swap)*(right*`)`. auszuführen. Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die spezialisierteste Version der Vorlagenfunktion. Die allgemeine Version der Vorlagenfunktion, **template \<class T> void swap (T& T&)**, in der Algorithmus-Headerdatei funktioniert per Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse genutzt werden kann.  
  
 In Visual C++ .NET 2003 sind Member der [<hash_map>](../standard-library/hash-map.md)- und [<hash_set>](../standard-library/hash-set.md)-Headerdateien nicht mehr im STD-Namespace enthalten. Sie wurden stattdessen in den stdext-Namespace verschoben. Weitere Informationen finden Sie unter [Der stdext-Namespace](../standard-library/stdext-namespace.md).  
  
## <a name="see-also"></a>Siehe auch  
 [<hash_map>](../standard-library/hash-map.md)




