---
title: 'List:: pop_front (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::list::pop_front
dev_langs:
- C++
helpviewer_keywords:
- pop_front member [STL/CLR]
ms.assetid: 6a0bad42-6796-41d9-a3e9-1488b3882574
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4122e485075ae5c6586fd92a4cae3a04fa08431a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="listpopfront-stlclr"></a>list::pop_front (STL/CLR)
Entfernt das erste Element.  
  
## <a name="syntax"></a>Syntax  
  
```  
void pop_front();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion entfernt das erste Element der gesteuerten Sequenz, die nicht leer sein darf. Sie verwenden es, um ein Element am Anfang die Liste zu verkürzen.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_list_pop_front.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop_front();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
b c  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/List >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List:: pop_back (STL/CLR)](../dotnet/list-pop-back-stl-clr.md)   
 [List:: push_back (STL/CLR)](../dotnet/list-push-back-stl-clr.md)   
 [list::push_front (STL/CLR)](../dotnet/list-push-front-stl-clr.md)