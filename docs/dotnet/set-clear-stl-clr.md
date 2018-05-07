---
title: 'Set:: Clear (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::set::clear
dev_langs:
- C++
helpviewer_keywords:
- clear member [STL/CLR]
ms.assetid: 52b39d7d-d479-45ff-a652-61cd26eb0c9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f29053d277630520cc4c93cba340181639fe0e6b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="setclear-stlclr"></a>set::clear (STL/CLR)
Entfernt alle Elemente.  
  
## <a name="syntax"></a>Syntax  
  
```  
void clear();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion ruft tatsächlich [Set:: Erase (STL/CLR)](../dotnet/set-erase-stl-clr.md) `(` [Set:: begin (STL/CLR)](../dotnet/set-begin-stl-clr.md) `(),` [Set:: End (STL/CLR)](../dotnet/set-end-stl-clr.md) `())`. Sie verwenden es, um sicherzustellen, dass die kontrollierte Sequenz leer ist.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_set_clear.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// add elements and clear again   
    c1.insert(L'a');   
    c1.insert(L'b');   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 0  
 a b  
size() = 0  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Set >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Legen Sie (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set::erase (STL/CLR)](../dotnet/set-erase-stl-clr.md)