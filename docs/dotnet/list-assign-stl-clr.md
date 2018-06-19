---
title: 'List:: Assign (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::assign
dev_langs:
- C++
helpviewer_keywords:
- assign member [STL/CLR]
ms.assetid: c5f2b131-d0e1-4188-9d4b-d617280e4032
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 02b579038d8945423d18d856e0682fe22245c563
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33131477"
---
# <a name="listassign-stlclr"></a>list::assign (STL/CLR)
Ersetzt alle Elemente.  
  
## <a name="syntax"></a>Syntax  
  
```  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parameter  
 count  
 Die Anzahl einzufügender Elemente.  
  
 first  
 Anfang des Bereichs, der eingefügt.  
  
 last  
 Das Ende des Bereichs einfügen.  
  
 Rechts  
 Die Enumeration eingefügt.  
  
 Val  
 Der Wert des einzufügenden Elements.  
  
## <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion ersetzt die kontrollierte Sequenz durch eine Wiederholung von `count` -Elementen des Werts `val`. Sie verwenden sie den Container mit Elementen gefüllt alle mit dem gleichen Wert.  
  
 Wenn `InIt` ein Ganzzahltyp ist, wird die zweite Memberfunktion verhält sich wie `assign((size_type)first, (value_type)last)`. Andernfalls ersetzt die kontrollierte Sequenz durch die Sequenz [`first`, `last`). Sie verwenden es für die gesteuerte Sequenz eine Kopie einer anderen Sequenz.  
  
 Die dritte Memberfunktion ersetzt die kontrollierte Sequenz durch die Sequenz, die vom Enumerator festgelegte `right`. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer Sequenz, die durch einen Enumerator beschrieben.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_list_assign.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::list<wchar_t> c2;   
    c2.assign(6, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an iterator range   
    cliext::list<wchar_t>::iterator it = c1.end();   
    c2.assign(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an enumeration   
    c2.assign(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
x x x x x x  
a b  
a b c  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/List >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::operator= (STL/CLR)](../dotnet/list-operator-assign-stl-clr.md)