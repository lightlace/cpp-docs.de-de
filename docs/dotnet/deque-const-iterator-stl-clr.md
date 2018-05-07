---
title: 'deque:: const_iterator (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::const_iterator
dev_langs:
- C++
helpviewer_keywords:
- const_iterator member [STL/CLR]
ms.assetid: 51579985-4664-4aaa-bad3-02f52f9050ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a1f0ad9cbb51b3aa9cb1e8a85a813e20adc567e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dequeconstiterator-stlclr"></a>deque::const_iterator (STL/CLR)
Der Typ eines konstanten Iterators für die gesteuerte Sequenz.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef T2 const_iterator;  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein Objekt vom angegebenen Typ `T2` , die als Konstante random-Access-Iterator für die gesteuerte Sequenz dienen kann.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_deque_const_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::deque<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" {0}", *cit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/doppelschlange >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::iterator (STL/CLR)](../dotnet/deque-iterator-stl-clr.md)