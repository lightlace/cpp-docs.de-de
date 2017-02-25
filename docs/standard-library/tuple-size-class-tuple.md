---
title: "tuple_size-Klasse &lt;tuple&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tuple_size"
  - "std::tr1::tuple_size"
  - "std.tr1.tuple_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tuple_size-Klasse <tuple> (TR1)"
ms.assetid: 73852fc5-eb68-41f1-8379-465cedc2314a
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# tuple_size-Klasse &lt;tuple&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt die Anzahl der Elemente, die eine `tuple` enthält.  
  
## <a name="syntax"></a>Syntax  
  
```  
// TEMPLATE STRUCT tuple_size  
template <class Tuple>  
struct tuple_size;  
 
// size of tuple  
template <class... Types>  
struct tuple_size<tuple<Types...>>  
: integral_constant<size_t, sizeof...(Types)>;  
 
// size of const tuple  
template <class Tuple>  
struct tuple_size<const Tuple>;  
 
// size of volatile tuple  
template <class Tuple>  
struct tuple_size<volatile Tuple>;  
 
// size of const volatile tuple  
template <class Tuple>  
struct tuple_size<const volatile Tuple>;   
```  
  
#### <a name="parameters"></a>Parameter  
 `Tuple`  
 Der Typ des Tupels.  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenklasse verfügt über einen Member `value` ein ganzzahligen Konstanten Ausdruck, dessen Wert dem Wertebereich des Tupeltyps `Tuple`.  
  
## <a name="example"></a>Beispiel  
  
```  
#include <tuple>   
#include <iostream>  
  
using namespace std;  
  
typedef tuple<int, double, int, double> MyTuple;  
int main()  
{  
    MyTuple c0(0, 1.5, 2, 3.7);  
  
    // display contents " 0 1 2 3"   
    cout << " " << get<0>(c0);  
    cout << " " << get<1>(c0);  
    cout << " " << get<2>(c0);  
    cout << " " << get<3>(c0) << endl;  
  
    // display size " 4"   
    cout << " " << tuple_size<MyTuple>::value << endl;  
}  
  
/*  
Output:  
0 1.5 2 3.7  
4  
*/  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< Tupel>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [\< Tupel>](../standard-library/tuple.md)   
 [Tupel](../standard-library/tuple-class.md)  
 [Tuple_element-Klasse](../standard-library/tuple-element-class-tuple.md)
