---
title: '&lt;vector&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vector/std::swap
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
helpviewer_keywords:
- std::swap [vector]
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: e752c3d39787466928b11ff8d644cf9a6558b656
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ltvectorgt-functions"></a>&lt;vector&gt;-Funktionen

  
##  <a name="swap"></a>  swap  
 Tauscht die Elemente zweier Vektoren aus.  
  
```  
template <class Type, class Allocator>  
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Der Vektor, in dem die auszutauschenden Elemente bereitgestellt werden, oder der Vektor, dessen Elemente mit denen des Vektors `left` ausgetauscht werden sollen.  
  
 `left`  
 Der Vektor, dessen Elemente mit denen des Vektors `right` ausgetauscht werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion ist ein Algorithmus für die Container-Klasse zu führen Sie die Memberfunktion Vektor spezialisierten `left`. [Vector:: Swap](../standard-library/vector-class.md) *(rechts*). Hierbei handelt es sich um Instanzen der partiellen Sortierung von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die am meisten spezialisierte Version der Vorlagenfunktion. Die allgemeine Version der Vorlagenfunktion, **template** \< **class T**> **void swap**( **T&**, **T&**), in der Algorithmusklasse funktioniert per Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.  
  
### <a name="example"></a>Beispiel  
  Im Codebeispiel für die Memberfunktion [vector::swap](../standard-library/vector-class.md) finden Sie ein Beispiel, in dem die Vorlagenversion `swap` verwendet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [\<vector>](../standard-library/vector.md)

