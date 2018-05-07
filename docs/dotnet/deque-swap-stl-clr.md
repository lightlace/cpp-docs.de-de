---
title: 'deque:: Swap (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::swap
dev_langs:
- C++
helpviewer_keywords:
- swap member [STL/CLR]
ms.assetid: 511e1aa8-3069-43f3-aa77-150f1de1e195
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 61c38d929c64aa3386a22292f8c6b395d472740d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dequeswap-stlclr"></a>deque::swap (STL/CLR)
Vertauscht den Inhalt von zwei Containern.  
  
## <a name="syntax"></a>Syntax  
  
```  
void swap(deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 Rechts  
 Container für den Tausch von Inhalten.  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion tauscht die kontrollierten Sequenzen zwischen `*this` und `right`aus. Dies erfolgt in konstanter Zeit, und es löst keine Ausnahmen. Sie verwenden es als eine schnelle Möglichkeit zum Austauschen von den Inhalt von zwei Containern.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_deque_swap.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::deque<wchar_t> c2(5, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
x x x x x  
x x x x x  
a b c  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/doppelschlange >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque:: Assign (STL/CLR)](../dotnet/deque-assign-stl-clr.md)   
 [operator= (deque) (STL/CLR)](../dotnet/operator-assign-deque-stl-clr.md)