---
title: '&lt;set&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- set/std::swap (map)
- set/std::swap (multiset)
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 65d3f4ef95ee3768323e3b727b9745a1a812f27c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ltsetgt-functions"></a>&lt;set&gt;-Funktionen
|||  
|-|-|  
|[swap (map)](#swap)|[swap (multiset)](#swap_multiset)|  
  
##  <a name="swap"></a> swap (map)
 Tauscht die Elemente zweier Sätze aus.  
  
```
template <class Key, class Traits, class Allocator>  
void swap(set<Key, Traits, Allocator>& left, set<Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Die Menge, in der die auszutauschenden Elemente bereitgestellt werden, oder die Menge, deren Elemente mit denen der Menge `left` ausgetauscht werden sollen.  
  
 `left`  
 Die Menge, deren Elemente mit denen der Menge `right` ausgetauscht werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion ist ein Algorithmus, der auf die Containerklasse „set“ spezialisiert ist, um die Memberfunktion `left.`[swap](../standard-library/set-class.md#swap)( `right`) auszuführen. Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die spezialisierteste Version der Vorlagenfunktion aus. Die allgemeine Version der Vorlagenfunktion  
  
 `template` \< **classT**> **void swap**( **T&**, **T&**)  
  
 in der Algorithmusklasse funktioniert mittels Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.  
  
### <a name="example"></a>Beispiel  
  Im Codebeispiel für die Memberklasse [set::swap](../standard-library/set-class.md#swap) finden Sie ein Beispiel für die Verwendung der Vorlagenversion `swap`.  
  
##  <a name="swap_multiset"></a> swap (multiset)
 Tauscht die Elemente zweier Multisets aus.  
  
```
template <class Key, class Traits, class Allocator>  
void swap(multiset<Key, Traits, Allocator>& left, multiset<Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Das Multiset, in dem die auszutauschenden Elemente bereitgestellt werden, oder das Multiset, dessen Elemente mit denen des Multisets `left` ausgetauscht werden sollen.  
  
 `left`  
 Ein Multiset, dessen Elemente mit denen des Multisets `right` ausgetauscht werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion ist ein Algorithmus, der auf die Containerklasse „multiset“ spezialisiert ist, um die Memberfunktion `left.`[swap](../standard-library/multiset-class.md#swap)( `right`) auszuführen. Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die spezialisierteste Version der Vorlagenfunktion aus. Die allgemeine Version der Vorlagenfunktion  
  
 `template` \< **classT**> **void swap**( **T&**, **T&**)  
  
 in der Algorithmusklasse funktioniert mittels Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.  
  
### <a name="example"></a>Beispiel  
  Im Codebeispiel für die Memberklasse [multiset::swap](../standard-library/multiset-class.md#swap) finden Sie ein Beispiel für die Verwendung der Vorlagenversion `swap`.  
  
## <a name="see-also"></a>Siehe auch  
 [\<set>](../standard-library/set.md)



