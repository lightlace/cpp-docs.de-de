---
title: 'List:: Reverse (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::reverse
dev_langs:
- C++
helpviewer_keywords:
- reverse member [STL/CLR]
ms.assetid: de3bce1e-01fe-461d-a785-5cf4fcea988f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: db07199116ec1956c706ef60284ed9f123c7b521
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="listreverse-stlclr"></a>list::reverse (STL/CLR)
Kehrt die gesteuerte Sequenz.  
  
## <a name="syntax"></a>Syntax  
  
```  
void reverse();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion kehrt die Reihenfolge aller Elemente in der kontrollierten Sequenz. Damit können sie eine Liste mit Elementen entsprechen.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_list_reverse.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// reverse and redisplay   
    c1.reverse();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
c b a  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/List >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)