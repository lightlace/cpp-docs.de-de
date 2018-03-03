---
title: Not_Equal_To (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::not_equal_to
dev_langs:
- C++
helpviewer_keywords:
- not_equal_to function [STL/CLR]
ms.assetid: 1b66e0ca-eace-4672-8da9-ed16f8608bca
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ae79c521f7edcc055ec6eee5907a6102ebf26134
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="notequalto-stlclr"></a>not_equal_to (STL/CLR)
Die Vorlagenklasse beschreibt ein Funktionselement ist, dass beim Aufrufen, gibt true zurück, nur, wenn das erste Argument nicht gleich dem zweiten ist. Sie verwenden ein Funktionsobjekt im Hinblick auf seine Argumenttyp angeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Arg>  
    ref class not_equal_to  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    not_equal_to();  
    not_equal_to(not_equal_to<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>Parameter  
 arg  
 Der Typ der Argumente.  
  
## <a name="member-functions"></a>Memberfunktionen  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|delegate_type|Der Typ des generischen Delegaten.|  
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|  
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|  
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|  
  
|Member|Beschreibung|  
|------------|-----------------|  
|not_equal_to|Erstellt das Funktionselement.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|Operator()|Berechnet die gewünschte Funktion.|  
|Operator Delegate_type ^|Wandelt das Funktionselement an einen Delegaten an.|  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenklasse beschreibt ein Funktionselement ist zwei Argumenten. Die Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, wird "true" nur, wenn das erste Argument nicht gleich dem zweiten ist.  
  
 Sie können auch das Objekt übergeben, als ein Funktionsargument, dessen Typ ist `delegate_type^` und werden entsprechend konvertiert werden.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_not_equal_to.cpp   
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
    c2.push_back(4);   
    c2.push_back(4);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 4 4"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::not_equal_to<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
4 4  
0 1  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/funktionale >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [equal_to (STL/CLR)](../dotnet/equal-to-stl-clr.md)