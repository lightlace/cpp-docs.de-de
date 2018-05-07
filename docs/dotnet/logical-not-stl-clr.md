---
title: Logical_not (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::logical_not
dev_langs:
- C++
helpviewer_keywords:
- logical_not function [STL/CLR]
ms.assetid: 32a2c6e2-1c58-41ac-8827-f3ee5adfe81d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d4048c642a1c562237bccba8fa3e5fd5429bba4e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="logicalnot-stlclr"></a>logical_not (STL/CLR)
Die Vorlagenklasse beschreibt ein Funktionselement ist, dass beim Aufrufen, gibt nur dann, wenn entweder "true" sein Argument als "false" überprüft. Sie verwenden ein Funktionsobjekt im Hinblick auf seine Argumenttyp angeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Arg>  
    ref class logical_not  
    { // wrap operator()  
public:  
    typedef Arg argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        argument_type, result_type>  
        delegate_type;  
  
    logical_not();  
    logical_not(logical_not<Arg> %right);  
  
    result_type operator()(argument_type left);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>Parameter  
 arg  
 Der Typ der Argumente.  
  
## <a name="member-functions"></a>Memberfunktionen  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|argument_type|Der Typ des Arguments Funktionselement.|  
|delegate_type|Der Typ des generischen Delegaten.|  
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|  
  
|Member|Beschreibung|  
|------------|-----------------|  
|logical_not|Erstellt das Funktionselement.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|Operator()|Berechnet die gewünschte Funktion.|  
|Operator Delegate_type ^|Wandelt das Funktionselement an einen Delegaten an.|  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenklasse beschreibt ein Funktionselement ist nur einem Argument. Die Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, wird "true" nur, wenn das Argument als "false" überprüft.  
  
 Sie können auch das Objekt übergeben, als ein Funktionsargument, dessen Typ ist `delegate_type^` und werden entsprechend konvertiert werden.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_logical_not.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(0);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 0"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c3.begin(), cliext::logical_not<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 0  
0 1  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/funktionale >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [negate (STL/CLR)](../dotnet/negate-stl-clr.md)