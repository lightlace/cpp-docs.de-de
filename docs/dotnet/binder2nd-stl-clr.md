---
title: "binder2nd (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::binder2nd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binder2nd-Funktion [STL/CLR]"
ms.assetid: f4be8722-1778-4cb9-9ec7-ad1443f6899f
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# binder2nd (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein EinArgumentfunktionselement, die, wenn sie aufgerufen wird, dem gespeicherten ZweiArgumentfunktionselement zurückgibt, das dem angegebenen ersten Argument und den gespeicherten zweiten Argument aufgerufen wird.  Sie verwenden sie angeben einem Funktionsobjekt hinsichtlich sein gespeichertes Funktionselement.  
  
## Syntax  
  
```  
template<typename Fun>  
    ref class binder2nd  
    { // wrap operator()  
public:  
    typedef Fun stored_function_type;  
    typedef typename Fun::first_argument_type first_argument_type;  
    typedef typename Fun::second_argument_type second_argument_type;  
    typedef typename Fun:result_type result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        first_argument_type, result_type>  
        delegate_type;  
  
    binder2nd(Fun% functor, second_argument_type left);  
    binder2nd(binder2nd<Arg>% right);  
  
    result_type operator()(first_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### Parameter  
 Fun  
 Der Typ des gespeicherten Feature\-Elements.  
  
## Memberfunktionen  
  
|Typdefinition|**Beschreibung**|  
|-------------------|----------------------|  
|delegate\_type|Der Typ des generischen Delegaten.|  
|first\_argument\_type|Der Typ des ersten Arguments des Feature\-Elements.|  
|result\_type|Der Typ des Funktionselementergebnisses.|  
|second\_argument\_type|Der Typ des Funktionselementzweiten Argumente.|  
|stored\_function\_type|Der Typ des Feature\-Elements.|  
  
|Member|**Beschreibung**|  
|------------|----------------------|  
|binder2nd|Erstellt das Funktionselement.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|operator\(\)|Berechnet die gewünschte Funktion.|  
|Operator delegate\_type^\(\)|Wandelt das Funktionselement zu einem Delegaten um.|  
  
## Hinweise  
 Die Vorlagenklasse beschreibt ein EinArgumentfunktionselement, das ein ZweiArgumentfunktionselement und ein zweites Argument speichert.  Sie definiert den Memberoperator, `operator()`, wenn das Objekt als Funktion aufgerufen wird, das Ergebnis des Funktionsaufrufs des gespeicherten Feature\-Elements mit dem angegebenen ersten Argument und dem gespeicherten zweiten Argument zurückgibt.  
  
 Sie können das Objekt auch übergeben, da ein Funktionsargument, dessen Typ `delegate_type^` ist und es entsprechend konvertiert wird.  
  
## Beispiel  
  
```  
// cliext_binder2nd.cpp   
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
    cliext::binder2nd<cliext::minus<int> > sub4(sub_op, 4);   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        sub4);   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        bind2nd(sub_op, 4));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 3**  
 **0 \-1**  
 **0 \-1**   
## Anforderungen  
 **Header:** \<cliext\/funktionsfähig\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [bind2nd](../dotnet/bind2nd-stl-clr.md)