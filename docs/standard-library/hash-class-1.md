---
title: "hash-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "std.hash"
  - "xfunctional/std::hash"
  - "hash"
  - "typeindex/std::hash"
  - "std::hash"
  - "std.tr1.hash"
  - "std::tr1::hash"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash-Klasse"
  - "hash-Klasse [TR1]"
ms.assetid: e1b500c6-a5c8-4f6f-ad33-7ec52eb8e2e4
caps.latest.revision: 21
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# hash-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Berechnet Hashcode für einen Wert.  
  
## Syntax  
  
```  
template<class Ty>  
    struct hash  
        : public unary_function<Ty, size_t> {  
    size_t operator()(Ty _Val) const;  
    };  
```  
  
## Hinweise  
 Die Memberfunktion wird eine Hashfunktion, die zum Zuordnen von Werten des Typs `Ty` auf eine Verteilung von Indexwerten geeignet ist.  Der Memberoperator gibt einen Hashcode für `_Val` zurück, entsprechend für Vorlagenklassen `unordered_map`, `unordered_multimap`, `unordered_set` und `unordered_multiset`.  `Ty` kann entweder skalarer Typ, `string`, `wstring`, `error_code`, `error_condition`, `u16string` oder `u32string`.  
  
## Beispiel  
  
```  
// std_tr1__functional__hash.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
#include <unordered_set>   
  
int main()   
    {   
    std::unordered_set<int, std::hash<int> > c0;   
    c0.insert(3);   
    std::cout << *c0.find(3) << std::endl;   
  
    return (0);   
    }  
  
```  
  
 **3**   
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<unordered\_map\>](../standard-library/unordered-map.md)   
 [unordered\_multimap\-Klasse](../standard-library/unordered-multimap-class.md)   
 [unordered\_multiset\-Klasse](../standard-library/unordered-multiset-class.md)   
 [\<unordered\_set\>](../standard-library/unordered-set.md)