---
title: 'deque:: Operator! = (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::operator!=
dev_langs:
- C++
helpviewer_keywords:
- operator!= member [STL/CLR]
ms.assetid: c23c7bd1-813e-4518-9947-eb13d1176a13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 46898ab8c6f747dbd72c94e490ec79034231bf81
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dequeoperator-stlclr"></a>deque::operator!= (STL/CLR)
Deque nicht gleich sein Vergleich aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Value>  
    bool operator!=(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 `left`  
 Linker zu vergleichender Container.  
  
 `right`  
 Rechter zu vergleichender Container.  
  
## <a name="remarks"></a>Hinweise  
 Gibt die Operatorfunktion `!(left == right)`. Sie zum Testen verwenden, ob `left` nicht sortiert wird, ist identisch mit `right` Wenn den zwei deque-Objekten aus verglichenen elementweise sind.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// cliext_deque_operator_ne.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
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
 **Header:** \<Cliext/doppelschlange >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [Operator == (Deque) (STL/CLR)](../dotnet/operator-equality-deque-stl-clr.md)   
 [Operator\< (Deque) (STL/CLR)](../dotnet/operator-less-than-deque-stl-clr.md)   
 [Operator > = (Deque) (STL/CLR)](../dotnet/operator-greater-or-equal-deque-stl-clr.md)   
 [Operator > (Deque) (STL/CLR)](../dotnet/operator-greater-than-deque-stl-clr.md)   
 [operator<= (deque) (STL/CLR)](../dotnet/operator-less-or-equal-deque-stl-clr.md)