---
title: "tuple_size-Klasse &lt;utility&gt;"
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
  - "tuple_size"
  - "std::tr1::tuple_size"
  - "std.tr1.tuple_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tuple_size-Klasse <utility> (TR1)"
ms.assetid: 36d04207-ed87-4c11-9875-150c59833b79
caps.latest.revision: 21
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# tuple_size-Klasse &lt;utility&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Umschließt die `pair`\-Elementanzahl.  
  
## Syntax  
  
```  
template<class Tuple>  
struct tuple_size;  
  
template<class T1, class T2>  
struct tuple_size<pair<T1, T2>>   : integral_constant<size_t, 2>  
  
// size of const tuple  
template<class Tuple>  
struct tuple_size<const Tuple>;  
  
// size of volatile tuple  
template<class Tuple>  
struct tuple_size<volatile Tuple>;  
  
// size of const volatile tuple  
template<class Tuple>  
struct tuple_size<const volatile Tuple>;  
```  
  
#### Parameter  
 `T1`  
 Der Typ des ersten Paarelements.  
  
 `T2`  
 Der Typ des zweiten Paarelements.  
  
## Hinweise  
 Die Vorlage ist eine Spezialisierung der Vorlagenklasse [tuple\_size\-Klasse](../standard-library/tuple-size-class-tuple.md). Sie hat einen `value`\-Member, der ein ganzzahliger konstanter Ausdruck ist, der den Wert 2 hat.  
  
## Beispiel  
  
```  
#include <utility>   
#include <iostream>   
  
using namespace std;  
  
typedef pair<int, double> MyPair;  
  
int main()  
{  
    MyPair c0(0, 1.1);  
  
    // display contents " 0 1.1"   
    cout << " " << get<0>(c0);  
    cout << " " << get<1>(c0) << endl;  
  
    // display size " 2"   
    cout << " " << tuple_size<MyPair>::value << endl;  
  
}  
  
/*  
Output:  
0 1.1  
2  
*/  
```  
  
## Anforderungen  
 **Header:** \<utility\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<utility\>](../standard-library/utility.md)   
 [get\-Funktion](../Topic/get%20Function%20%3Cutility%3E.md)   
 [tuple\_element\-Klasse](../standard-library/tuple-element-class-utility.md)