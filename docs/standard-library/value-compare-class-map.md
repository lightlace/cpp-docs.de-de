---
title: value_compare-Klasse (&lt;map&gt;) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::value_compare
- std.value_compare
- map/std::value_compare
- value_compare
dev_langs:
- C++
helpviewer_keywords:
- value_compare class
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: 200e62472c8c6002cdc45181ad019a1d78ca7977
ms.lasthandoff: 02/24/2017

---
# <a name="valuecompare-class-ltmapgt"></a>value_compare-Klasse (&lt;map&gt;)
Stellt ein Funktionsobjekt bereit, das die Elemente einer Zuordnung vergleichen kann, indem die Werte ihrer Schlüssel verglichen werden, um deren relative Reihenfolge in der Zuordnung zu bestimmen.  
  
## <a name="syntax"></a>Syntax  
  
```
class value_compare : public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(const value_type& left, const value_type& right) const;
    value_compare(key_compare pred) : comp(pred);
protected:
    key_compare comp;
};
```  
  
## <a name="remarks"></a>Hinweise  
 Die von `value_compare` bei einem Vergleich von **value_types** ganzer, in einer Zuordnung enthaltener Elemente bereitgestellten Vergleichskriterien werden von einem Vergleich der Schlüssel der jeweiligen Elemente durch die Erweiterungsklassenkonstruktion induziert. Der Operator der Memberfunktion verwendet das Objekt **comp** vom Typ `key_compare`, das in dem Funktionsobjekt gespeichert ist, das von `value_compare` für den Vergleich der Sortierschlüsselkomponenten von zwei Elementen bereitgestellt wird.  
  
 Bei Mengen und Multimengen, bei denen es sich um einfache Container handelt, bei denen die Schlüsselwerte mit den Elementwerten übereinstimmen, stimmt `value_compare` mit `key_compare` überein; bei Zuordnungen und Mehrfachzuordnungen nicht, da der Wert von Elementen vom Typ `pair` nicht mit dem Wert des Elementschlüssels identisch ist.  
  
## <a name="example"></a>Beispiel  
  Im Beispiel für [value_comp](../standard-library/map-class.md#map__value_comp) wird verdeutlicht, wie `value_compare` deklariert und verwendet wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<map>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [binary_function Struct (binary_function-Struktur)](../standard-library/binary-function-struct.md)   
 [Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)




