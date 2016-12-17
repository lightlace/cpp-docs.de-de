---
title: "logical_and (STL/CLR)"
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
  - "cliext::logical_and"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "logical_and-Funktion [STL/CLR]"
ms.assetid: ae103802-11e0-4060-a4f3-4f6fdc209e7c
caps.latest.revision: 18
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# logical_and (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Funktionselement, die, wenn sie aufgerufen werden, wird nur das erste Argument und der zweite Test als true ausrichten.  Sie verwenden sie angeben einem Funktionsobjekt hinsichtlich den Argumenttyp.  
  
## Syntax  
  
```  
template<typename Arg>  
    ref class logical_and  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    logical_and();  
    logical_and(logical_and<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### Parameter  
 Arg  
 Der Typ der Argumente.  
  
## Memberfunktionen  
  
|Typdefinition|**Beschreibung**|  
|-------------------|----------------------|  
|delegate\_type|Der Typ des generischen Delegaten.|  
|first\_argument\_type|Der Typ des ersten Arguments des Feature\-Elements.|  
|result\_type|Der Typ des Funktionselementergebnisses.|  
|second\_argument\_type|Der Typ des Funktionselementzweiten Argumente.|  
  
|Member|**Beschreibung**|  
|------------|----------------------|  
|logical\_and|Erstellt das Funktionselement.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|operator\(\)|Berechnet die gewünschte Funktion.|  
|Operator delegate\_type^|Wandelt das Funktionselement zu einem Delegaten um.|  
  
## Hinweise  
 Die Vorlagenklasse beschreibt ein ZweiArgumentfunktionselement.  Sie definiert den Memberoperator, `operator()`, wenn das Objekt als Funktion aufgerufen wird sie nur true, wenn das erste Argument und der zweite Test als true zurückgibt.  
  
 Sie können das Objekt auch übergeben, da ein Funktionsargument, dessen Typ `delegate_type^` ist und es entsprechend konvertiert wird.  
  
## Beispiel  
  
```  
// cliext_logical_and.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(2);   
    c1.push_back(0);   
    Myvector c2;   
    c2.push_back(3);   
    c2.push_back(0);   
    Myvector c3(2, 0);   
  
// display initial contents " 1 0" and " 1 0"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::logical_and<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **2 0**  
 **3 0**  
 **1 0**   
## Anforderungen  
 **Header:** \<cliext\/funktionsfähig\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [logical\_or](../dotnet/logical-or-stl-clr.md)