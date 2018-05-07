---
title: bind2nd (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::bind2nd
dev_langs:
- C++
helpviewer_keywords:
- bind2nd function [STL/CLR]
ms.assetid: 457cebea-38e4-4466-a468-fe9eb138e80c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 13d8ffe476c73c04aff2e0c5de84558a7d9dbeae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="bind2nd-stlclr"></a>bind2nd (STL/CLR)
Generiert eine `binder2nd` für ein Argument und ein Funktionselement ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Fun,  
    typename Arg>  
    binder2nd<Fun> bind2nd(Fun% functor,  
        Arg right);  
```  
  
## <a name="template-parameters"></a>Vorlagenparameter  
 arg  
 Der Typ des Arguments.  
  
 Fun  
 Der Typ, der das Funktionselement.  
  
## <a name="function-parameters"></a>Funktionsparameter  
 Funktionselement  
 Das Funktionselement umschließen.  
  
 Rechts  
 Das zweite Argument umschließen.  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion gibt [binder2nd (STL/CLR)](../dotnet/binder2nd-stl-clr.md)`<Fun>(functor, right)`. Sie verwenden es als eine einfache Möglichkeit, ein Funktionselement ist zwei Argumente und das zweite Argument in ein Funktionselement ist nur einem Argument zu umschließen, den sie mit dem ersten Argument aufruft.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_bind2nd.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::minus<int> sub_op;   
    cliext::binder2nd<cliext::minus<int> > sub4(sub_op, 4);   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        sub4);   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        bind2nd(sub_op, 4));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
0 -1  
0 -1  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/funktionale >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [binder2nd (STL/CLR)](../dotnet/binder2nd-stl-clr.md)