---
title: dividiert (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::divides
dev_langs:
- C++
helpviewer_keywords:
- divides function [STL/CLR]
ms.assetid: 4c36026a-02ba-475d-af68-854599647f4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 84e95ef9138540ad716655f159392768ac115fb9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111522"
---
# <a name="divides-stlclr"></a>divides (STL/CLR)
Die Vorlagenklasse beschreibt ein Funktionselement ist, dass beim Aufrufen, gibt die ersten Arguments dividiert durch den zweiten. Sie verwenden ein Funktionsobjekt im Hinblick auf seine Argumenttyp angeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Arg>  
    ref class divides  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef Arg result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    divides();  
    divides(divides<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>Parameter  
 arg  
 Der Typ der Argumente und der Rückgabewert.  
  
## <a name="member-functions"></a>Memberfunktionen  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|delegate_type|Der Typ des generischen Delegaten.|  
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|  
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|  
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|  
  
|Member|Beschreibung|  
|------------|-----------------|  
|divides|Erstellt das Funktionselement.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|Operator()|Berechnet die gewünschte Funktion.|  
|Operator delegate_type^()|Wandelt das Funktionselement an einen Delegaten an.|  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenklasse beschreibt ein Funktionselement ist zwei Argumenten. Die Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, wird der ersten Arguments dividiert durch den zweiten zurückgegeben.  
  
 Sie können auch das Objekt übergeben, als ein Funktionsargument, dessen Typ ist `delegate_type^` und werden entsprechend konvertiert werden.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_divides.cpp   
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
    Myvector c2;   
    c2.push_back(2);   
    c2.push_back(1);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 2 1"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::divides<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
2 1  
2 3  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/funktionale >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Modulo (STL/CLR)](../dotnet/modulus-stl-clr.md)   
 [multiplies (STL/CLR)](../dotnet/multiplies-stl-clr.md)