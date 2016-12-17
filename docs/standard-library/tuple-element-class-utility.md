---
title: "tuple_element-Klasse &lt;utility&gt;"
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
  - "tuple_element-Klasse <utility> (TR1)"
ms.assetid: f9db79e8-685c-49e3-97ee-81763e516ce3
caps.latest.revision: 20
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# tuple_element-Klasse &lt;utility&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Umschließt den Typ eines `pair`\-Elements.  
  
## Syntax  
  
```  
// CLASS tuple_element (find element by index)  
template<size_t Index, class Tuple>  
struct tuple_element;  
  
// struct to determine type of element 0 in pair  
template<class Ty1, class Ty2>  
struct tuple_element<0, pair<Ty1, Ty2> >;  
  
// struct to determine type of element 1 in pair  
template<class Ty1, class Ty2>  
struct tuple_element<1, pair<Ty1, Ty2> >;  
  
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
  
#### Parameter  
 Index  
 Die Position des Elements. Für Paare ist dieser Wert 0 oder 1.  
  
 `T1`  
 Der Typ des ersten Paarelements.  
  
 `T2`  
 Der Typ des zweiten Paarelements.  
  
 Typ  
  
## Hinweise  
 Die Vorlagen sind Spezialisierungen der [tuple\_element\-Klasse](../standard-library/tuple-element-class-tuple.md)\-Vorlagenklasse. Jede verfügt über ein einzelnes „typedef“\-Member, `type`, das ein Synonym für den Typ des Elements an der angegebenen Position im `pair` ist, wobei alle „const“ und\/oder „volatile“ Qualifikationen beibehalten werden.`tuple_element_t` ist ein zweckmäßiger Alias für `tuple_element<N, pair<T1, T2>>::type`. Verwenden Sie die [get\-Funktion](../Topic/get%20Function%20%3Cutility%3E.md), um das Element an einer angegebenen Position oder \(in C\+\+14\/Visual Studio 2015\) mit einem angegebenen Typ zurückzugeben.  
  
## Beispiel  
  
```  
#include <utility>   
#include <iostream>   
  
using namespace std;  
  
typedef pair<int, double> MyPair;  
int main()  
{  
    MyPair c0(0, 1.333);  
  
    // display contents " 0 1"   
    cout << " " << get<0>(c0);  
    cout << " " << get<1>(c0) << endl;  
  
    // display first element " 0" by index  
    tuple_element<0, MyPair>::type val = get<0>(c0);  
    cout << " " << val;  
  
    // display second element by type   
    tuple_element<1, MyPair>::type val2 = get<double>(c0);  
    cout << " " << val2 << endl;  
}  
  
/*  
Output:  
0 1.333  
0 1.333  
*/  
```  
  
## Anforderungen  
 **Header:** \<utility\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<utility\>](../standard-library/utility.md)   
 [get\-Funktion](../Topic/get%20Function%20%3Cutility%3E.md)   
 [tuple\_size\-Klasse](../standard-library/tuple-size-class-utility.md)