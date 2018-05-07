---
title: binder1st (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::binder1st
dev_langs:
- C++
helpviewer_keywords:
- binder1st function [STL/CLR]
ms.assetid: a989c9cc-a485-45d9-bd19-519018e6974b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8ab2d0a0d5127dae39008fdce177d23f1a6f7074
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="binder1st-stlclr"></a>binder1st (STL/CLR)
Die Vorlagenklasse beschreibt ein Funktionselement ist nur einem Argument, die beim Aufruf gibt die gespeicherte zwei Argumenten Funktionselement mit gespeicherten erstes Argument und das zweite angegebene Argument aufgerufen. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf seine gespeicherte Funktionselement.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Fun>  
    ref class binder1st  
    { // wrap operator()  
public:  
    typedef Fun stored_function_type;  
    typedef typename Fun::first_argument_type first_argument_type;  
    typedef typename Fun::second_argument_type second_argument_type;  
    typedef typename Fun:result_type result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        second_argument_type, result_type>  
        delegate_type;  
  
    binder1st(Fun% functor, first_argument_type left);  
    binder1st(binder1st<Arg>% right);  
  
    result_type operator()(second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>Parameter  
 Fun  
 Der Typ des gespeicherten Funktionselement.  
  
## <a name="member-functions"></a>Memberfunktionen  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|delegate_type|Der Typ des generischen Delegaten.|  
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|  
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|  
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|  
|stored_function_type|Der Typ, der das Funktionselement.|  
  
|Member|Beschreibung|  
|------------|-----------------|  
|binder1st|Erstellt das Funktionselement.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|Operator()|Berechnet die gewünschte Funktion.|  
|Operator delegate_type^()|Wandelt das Funktionselement an einen Delegaten an.|  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenklasse beschreibt ein Funktionselement ist nur einem Argument, das ein Funktionselement ist zwei Argumente und ein erstes Argument gespeichert. Die Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, gibt das Ergebnis des Aufrufs der gespeicherten Funktionselement mit dem gespeicherten ersten Argument und das zweite angegebene Argument zurück.  
  
 Sie können auch das Objekt übergeben, als ein Funktionsargument, dessen Typ ist `delegate_type^` und werden entsprechend konvertiert werden.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_binder1st.cpp   
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
    cliext::binder1st<cliext::minus<int> > subfrom3(sub_op, 3);   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        subfrom3);   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        bind1st(sub_op, 3));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
-1 0  
-1 0  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/funktionale >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [bind1st (STL/CLR)](../dotnet/bind1st-stl-clr.md)