---
title: "tuple_size-Klasse &lt;array&gt;"
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
  - "tuple_size-Klasse <array> (TR1)"
ms.assetid: ef95ffee-59b4-4396-817f-487d4486772d
caps.latest.revision: 20
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# tuple_size-Klasse &lt;array&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Umschließt die Größe eines Arrays.  
  
## Syntax  
  
```  
template<class Tuple>  
struct tuple_size;  
  
// struct to determine number of elements in array  
template<class T, size_t Size>  
struct tuple_size<array<T, Size> >  
: integral_constant<size_t, Size>;  
  
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
  
## Vorlagenparameter  
 `T`  
 Der Typ eines Elements.  
  
 `Size`  
 Die Größe des Arrays.  
  
## Hinweise  
 Diese Vorlage ist eine Spezialisierung der Vorlagenklasse [tuple\_size\-Klasse](../standard-library/tuple-size-class-tuple.md). Sie verfügt über einen Member `value`, der einem ganzzahligen konstanten Ausdruck entspricht, dessen Wert `N` und damit die Größe des Arrays ist.  
  
## Beispiel  
  
```  
#include <array>   
#include <iostream>   
  
using namespace std;  
  
typedef array<int, 4> MyArray;  
  
int main()  
{  
    MyArray c0 { 0, 1, 2, 3 };  
  
    // display contents " 0 1 2 3"   
    for (const auto& e : c0)  
    {  
        cout << e;  
    }  
    cout << endl;  
  
    // display size " 4"   
    cout << " " << tuple_size<MyArray>::value << endl;  
}  
/*  
Output:  
0123  
4  
*/  
  
```  
  
## Anforderungen  
 **Header:** \<Array\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<array\>](../standard-library/array.md)   
 [\<tuple\>](../standard-library/tuple.md)   
 [tuple\_size\-Klasse](../standard-library/tuple-size-class-tuple.md)