---
title: '&lt;vector&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
caps.latest.revision: 10
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 239ac662d19e3d0aa788e830557c28bc84835828
ms.contentlocale: de-de
ms.lasthandoff: 04/19/2017

---
# <a name="ltvectorgt-functions"></a>&lt;vector&gt;-Funktionen

  
##  <a name="swap"></a> swap  
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
 Die Vorlagenfunktion ist ein Algorithmus für die Container-Klasse zu führen Sie die Memberfunktion Vektor spezialisierten `left`. [Vector:: Swap](../standard-library/vector-class.md) *(rechts*). Hierbei handelt es sich um Instanzen der partiellen Sortierung von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die am meisten spezialisierte Version der Vorlagenfunktion. Die allgemeine Version der Vorlagenfunktion, **template** \< **class T**> **void swap**( **T&**, **T&**), in der Algorithmusklasse funktioniert per Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse genutzt werden kann.  
  
### <a name="example"></a>Beispiel  
  Im Codebeispiel für die Memberfunktion [vector::swap](../standard-library/vector-class.md) finden Sie ein Beispiel, in dem die Vorlagenversion `swap` verwendet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [\<vector>](../standard-library/vector.md)


