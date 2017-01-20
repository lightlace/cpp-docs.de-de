---
title: "tuple_element-Klasse &lt;array&gt;"
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
  - "std.tr1.tuple_element"
  - "tuple_element"
  - "std::tr1::tuple_element"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tuple_element-Klasse <array> (TR1)"
ms.assetid: 99201ca4-190a-4d9e-9013-de95ddfe5901
caps.latest.revision: 21
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# tuple_element-Klasse &lt;array&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Umschließt den Typ eines Arrayelements.  
  
## Syntax  
  
```  
// CLASS tuple_element (find element by index)  
template<size_t Index, class Tuple>  
struct tuple_element;  
  
template<size_t Index, class T, size_t Size>  
struct tuple_element<Index, array<T, Size>>  
  
// tuple_element for const  
template<size_t Index, class Tuple>  
struct tuple_element<Index, const Tuple>;  
  
// tuple_element for volatile  
template<size_t Index, class Tuple>  
struct tuple_element<Index, volatile Tuple>;  
  
// tuple_element for const volatile  
template<size_t Index, class Tuple>  
struct tuple_element<Index, const volatile Tuple>;  
  
template<size_t Index, class Tuple>  
using tuple_element_t = typename tuple_element<Index, Tuple>::type;  
  
```  
  
## Parameter  
 `Index`  
 Die Position des Elements.  
  
 `T`  
 Der Typ eines Elements.  
  
 `N`  
 Die Größe des Arrays.  
  
## Hinweise  
 Diese Vorlagenklasse ist eine Spezialisierung der Vorlagenklasse [tuple\_element\-Klasse](../standard-library/tuple-element-class-tuple.md) für Arrays. Diese Klasse stellt eine Schnittstelle für ein Array als Tupel von N Elementen bereit, von denen jedes denselben Typ aufweist. Jede Spezialisierung verfügt über ein geschachteltes Typedef `type`, das ein Synonym für den Typ des `Index`\-Elements des `array` ist, wobei alle Qualifikationen von „const\-volatile“ beibehalten werden.  
  
## Beispiel  
  
```  
  
#include <array>   
#include <iostream>   
  
using namespace std;  
typedef array<int, 4> MyArray;  
  
int main()  
{  
    MyArray c0 { 0, 1, 2, 3 };  
  
    for (const auto& e : c0)  
    {  
        cout << " " << e;  
    }  
    cout << endl;  
  
    // display first element " 0"   
    tuple_element<0, MyArray>::type val = c0.front();  
    cout << " " << val << endl;  
}  
  
/*  
Output:  
0 1 2 3  
0  
*/  
  
```  
  
## Anforderungen  
 **Header:** \<Array\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<array\>](../standard-library/array.md)   
 [\<tuple\>](../standard-library/tuple.md)   
 [tuple\_element\-Klasse](../standard-library/tuple-element-class-tuple.md)