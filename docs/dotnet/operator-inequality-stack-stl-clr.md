---
title: Operator! = (Stapel) (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::stack::operator!=
dev_langs: C++
helpviewer_keywords: operator!= member [STL/CLR]
ms.assetid: d28aca6a-685c-4d3d-bc97-de80d75ccd60
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e2583c89028f64e0739309f2cf78d8726d489782
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="operator-stack-stlclr"></a>operator!= (stack) (STL/CLR)
Stack-Vergleich nicht gleich sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Value,  
    typename Container>  
    bool operator!=(stack<Value, Container>% left,  
        stack<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 links  
 Linker zu vergleichender Container.  
  
 Rechts  
 Rechter zu vergleichender Container.  
  
## <a name="remarks"></a>Hinweise  
 Gibt die Operatorfunktion `!(left == right)`. Sie verwenden es, um zu testen, ob `left` nicht sortiert wird, ist identisch mit `right` bei beiden verglichenen elementweise sind.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_stack_operator_ne.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] != [a b c] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[a b c] != [a b d] is {0}",   
        c1 != c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] != [a b c] is False  
[a b c] != [a b d] is True  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Stack >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Stack (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [Operator == (Stapel) (STL/CLR)](../dotnet/operator-equality-stack-stl-clr.md)   
 [Operator\< (Stapel) (STL/CLR)](../dotnet/operator-less-than-stack-stl-clr.md)   
 [Operator > = (Stapel) (STL/CLR)](../dotnet/operator-greater-or-equal-stack-stl-clr.md)   
 [Operator > (Stapel) (STL/CLR)](../dotnet/operator-greater-than-stack-stl-clr.md)   
 [operator<= (stack) (STL/CLR)](../dotnet/operator-less-or-equal-stack-stl-clr.md)