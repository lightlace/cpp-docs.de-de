---
title: Vector::Operator(STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::operator[]
dev_langs: C++
helpviewer_keywords: operatormember [] [STL/CLR]
ms.assetid: 379a7029-460d-4de8-918b-c79e3e13b9d4
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 73d58a8e1c4a677a248c0a4af90199fd50b36d56
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="vectoroperatorstlclr"></a>vector::operator(STL/CLR)
Greift auf ein Element an einer angegebenen Position zu.  
  
## <a name="syntax"></a>Syntax  
  
```  
reference operator[](size_type pos);  
```  
  
#### <a name="parameters"></a>Parameter  
 pos  
 Position des Elements, auf das zugegriffen wird  
  
## <a name="remarks"></a>Hinweise  
 Der Memberoperator gibt eine Referene zurück, auf das Element an der Position `pos`. Sie verwenden es, auf ein Element zuzugreifen, deren Position Sie kennen.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_vector_operator_sub.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using subscripting   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
  
// change an entry and redisplay   
    c1[1] = L'x';   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a x c  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Vektor >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Vektor (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector::at (STL/CLR)](../dotnet/vector-at-stl-clr.md)