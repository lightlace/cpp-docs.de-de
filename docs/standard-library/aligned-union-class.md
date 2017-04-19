---
title: aligned_union-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- aligned_union
- type_traits/std::aligned_union
dev_langs:
- C++
helpviewer_keywords:
- aligned_union
ms.assetid: 9931a44d-3a67-4f29-a0f6-d47a7cf560ac
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: d6ecefd7d6877bc65bbf6f5542ae6b7f318a9d27
ms.lasthandoff: 02/24/2017

---
# <a name="alignedunion-class"></a>aligned_union-Klasse
Stellt einen POD-Typ bereit, der groß genug ist und passend ausgerichtet ist, um einen Union-Typ zu speichern. Außerdem bietet er die benötigte Größe.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <std::size_t Len, class... Types>  
struct aligned_union;  
 
template <std::size_t Len, class... Types>  
using aligned_union_t = typename aligned_union<Len, Types...>::type;  
```  
  
#### <a name="parameters"></a>Parameter  
 `Len`  
 Der Ausrichtungswert für den größten Typ in der Union.  
  
 `Types`  
 Die unterschiedlichen Typen in der zugrunde liegenden Union.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie die Vorlagenklasse, um eine Ausrichtung und die benötigte Größe zu schaffen, die für das Speichern einer Union in einem nicht initialisierten Speicherplatz erforderlich sind. Der typedef-Member `type` benennt einen POD-Typ, der zum Speichern jedes unter `Types` aufgelisteten Typen geeignet ist; die minimale Größe beträgt `Len`. Der statische Member `alignment_value` des Typs `std::size_t` enthält die striktesten Ausrichtungen, die für alle unter `Types` aufgelisteten Typen erforderliche sind.  
  
## <a name="example"></a>Beispiel  
 Folgendes Beispiel veranschaulicht den Gebrauch von `aligned_union`, um einen ausgerichteten Stapelpuffer zuzuweisen, um eine Union zu platzieren.  
  
```  
// std__type_traits__aligned_union.cpp  
#include <iostream>  
#include <type_traits>  
  
union U_type  
{  
    int i;  
    float f;  
    double d;  
    U_type(float e) : f(e) {}  
};  
  
typedef std::aligned_union<16, int, float, double>::type aligned_U_type;  
  
int main()  
{  
    // allocate memory for a U_type aligned on a 16-byte boundary  
    aligned_U_type au;  
    // do placement new in the aligned memory on the stack  
    U_type* u = new (&au) U_type(1.0f);  
    if (nullptr != u)  
    {  
        std::cout << "value of u->i is " << u->i << std::endl;  
        // must clean up placement objects manually!  
        u->~U_type();  
    }  
}  
```  
  
```Output  
value of u->i is 1065353216  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)   
 [alignment_of-Klasse](../standard-library/alignment-of-class.md)

