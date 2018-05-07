---
title: 'Vector:: Assign (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::assign
dev_langs:
- C++
helpviewer_keywords:
- assign member [STL/CLR]
ms.assetid: 945e2048-6c61-4701-b13c-8241cbee3fa1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a16e9262ad69f6f4fe2e11030b5880485139823a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="vectorassign-stlclr"></a>vector::assign (STL/CLR)
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
// cliext_vector_assign.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::vector<wchar_t> c2;   
    c2.assign(6, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an iterator range   
    c2.assign(c1.begin(), c1.end() - 1);   
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
 **Header:** \<Cliext/Vektor >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Vektor (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector::operator= (STL/CLR)](../dotnet/vector-operator-assign-stl-clr.md)