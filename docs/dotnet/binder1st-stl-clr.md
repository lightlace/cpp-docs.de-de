---
title: "binder1st (STL/CLR)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "cliext::binder1st"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binder1st-Funktion [STL/CLR]"
ms.assetid: a989c9cc-a485-45d9-bd19-519018e6974b
caps.latest.revision: 18
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# binder1st (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein EinArgumentfunktionselement, die, wenn sie aufgerufen wird, dem gespeicherten ZweiArgumentfunktionselement zurückgibt, das mit dem gespeicherten ersten Argument und dem angegebenen zweiten Argument aufgerufen wird.  Sie verwenden sie angeben einem Funktionsobjekt hinsichtlich sein gespeichertes Funktionselement.  
  
## Syntax  
  
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
|binder1st|Erstellt das Funktionselement.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|operator\(\)|Berechnet die gewünschte Funktion.|  
|Operator delegate\_type^\(\)|Wandelt das Funktionselement zu einem Delegaten um.|  
  
## Hinweise  
 Die Vorlagenklasse beschreibt ein EinArgumentfunktionselement, das ein ZweiArgumentfunktionselement und ein erstes Argument speichert.  Sie definiert den Memberoperator, `operator()`, wenn das Objekt als Funktion aufgerufen wird, das Ergebnis des Funktionsaufrufs des gespeicherten Feature\-Elements mit dem gespeicherten ersten Argument und dem angegebenen zweiten Argument zurückgibt.  
  
 Sie können das Objekt auch übergeben, da ein Funktionsargument, dessen Typ `delegate_type^` ist und es entsprechend konvertiert wird.  
  
## Beispiel  
  
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
  
  **4 3**  
 **\-1 0**  
 **\-1 0**   
## Anforderungen  
 **Header:** \<cliext\/funktionsfähig\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [bind1st](../dotnet/bind1st-stl-clr.md)