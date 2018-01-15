---
title: value_compare-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: value_compare
dev_langs: C++
helpviewer_keywords: value_compare class
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a340acbc50c629686f010f51ce07e397e4084154
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="valuecompare-class"></a>value_compare-Klasse
Stellt ein Funktionsobjekt bereit, das die Elemente einer hash_map vergleichen kann, indem die Werte ihrer Schlüssel verglichen werden, um deren relative Reihenfolge in der hash_map zu bestimmen.  
  
## <a name="syntax"></a>Syntax  
  
```
class value_compare
 : std::public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(
    const value_type& left,
    const value_type& right) const
 {
    return (comp(left.first, right.first));

 }
protected:
    value_compare(const key_compare& c) : comp (c) { }
    key_compare comp;
};
```  
  
## <a name="remarks"></a>Hinweise  
 Die von value_compare bei einem Vergleich von **value_types** ganzer, in einer hash_map enthaltener Elemente bereitgestellten Vergleichskriterien werden von einem Vergleich der Schlüssel der jeweiligen Elemente durch die Erweiterungsklassenkonstruktion induziert. Der Operator der Memberfunktion verwendet das Objekt **comp** vom Typ `key_compare`, das in dem Funktionsobjekt gespeichert ist, das von value_compare für den Vergleich der Sortierschlüsselkomponenten von zwei Elementen bereitgestellt wird.  
  
 Bei hash_sets und hash_multisets, bei denen es sich um einfache Container handelt, bei denen die Schlüsselwerte mit den Elementwerten übereinstimmen, stimmt value_compare mit `key_compare` überein; bei hash_maps und hash_multimaps nicht, da der Wert von Elementen vom Typ `pair` nicht mit dem Wert des Elementschlüssels identisch ist.  
  
   
  
## <a name="example"></a>Beispiel  
 Im Beispiel für [hash_map::value_comp](../standard-library/hash-map-class.md#value_comp) wird verdeutlicht, wie value_compare deklariert und verwendet wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<hash_map>  
  
 **Namespace:** stdext  
  
## <a name="see-also"></a>Siehe auch  
 [binary_function Struct (binary_function-Struktur)](../standard-library/binary-function-struct.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)



