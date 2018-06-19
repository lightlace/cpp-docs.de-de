---
title: 'Vector:: AT (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::at
dev_langs:
- C++
helpviewer_keywords:
- at member [STL/CLR]
ms.assetid: 9af9f829-48b8-4906-ba4a-b43454acb2c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 426dfae309defdef026078325ca06d72ccc4e1b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33166886"
---
# <a name="vectorat-stlclr"></a>vector::at (STL/CLR)
Greift auf ein Element an einer angegebenen Position zu.  
  
## <a name="syntax"></a>Syntax  
  
```  
reference at(size_type pos);  
```  
  
#### <a name="parameters"></a>Parameter  
 pos  
 Position des Elements, auf das zugegriffen wird  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einen Verweis auf das Element der kontrollierten Sequenz an der Position `pos`. Verwenden sie zum Lesen oder schreiben ein Element, dessen Position Sie kennen.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_vector_at.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using at   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// change an entry and redisplay   
    c1.at(1) = L'x';   
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
 [vector::operator(STL/CLR)](../dotnet/vector-operator-stl-clr.md)