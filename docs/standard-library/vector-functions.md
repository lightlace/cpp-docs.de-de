---
title: '&lt;vector&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
caps.latest.revision: 10
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: bb62c0c4e5b2965438539b17ec5a2c465e647ed7
ms.lasthandoff: 02/24/2017

---
# <a name="ltvectorgt-functions"></a>&lt;vector&gt;-Funktionen

  
##  <a name="a-nameswapa--swap"></a><a name="swap"></a> swap  
 Tauscht die Elemente zweier Vektoren aus.  
  
```  
template <class Type, class Allocator>  
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Der Vektor, in dem die auszutauschenden Elemente bereitgestellt werden, oder der Vektor, dessen Elemente mit denen des Vektors ` left` ausgetauscht werden sollen.  
  
 ` left`  
 Der Vektor, dessen Elemente mit denen des Vektors ` right` ausgetauscht werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion ist ein Algorithmus, der zur Ausführung der Memberfunktion ` left.` [vector::swap](../standard-library/vector-class.md) *( right*) auf die Containerklasse „vector“ spezialisiert ist. Hierbei handelt es sich um Instanzen der partiellen Sortierung von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die am meisten spezialisierte Version der Vorlagenfunktion. Die allgemeine Version der Vorlagenfunktion, **template** \< **class T**> **void swap**( **T&**, **T&**), in der Algorithmusklasse funktioniert per Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse genutzt werden kann.  
  
### <a name="example"></a>Beispiel  
  Im Codebeispiel für die Memberfunktion [vector::swap](../standard-library/vector-class.md) finden Sie ein Beispiel, in dem die Vorlagenversion `swap` verwendet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [\<vector>](../standard-library/vector.md)


