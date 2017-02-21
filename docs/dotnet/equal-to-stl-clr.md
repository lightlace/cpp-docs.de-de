---
title: "equal_to (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::equal_to"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "equal_to-Funktion [STL/CLR]"
ms.assetid: 9dd6e27d-e695-470f-b7a7-19a6db970ee5
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# equal_to (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Funktionselement, die, wenn sie aufgerufen werden, Rückgaben ausrichten, wenn das erste Argument gleich das zweite ist.  Sie verwenden sie angeben einem Funktionsobjekt hinsichtlich den Argumenttyp.  
  
## Syntax  
  
```  
template<typename Arg>  
    ref class equal_to  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    equal_to();  
    equal_to(equal_to<Arg>% right);  
  
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
|equal\_to|Erstellt das Funktionselement.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|operator\(\)|Berechnet die gewünschte Funktion.|  
|Operator delegate\_type^\(\)|Wandelt das Funktionselement zu einem Delegaten um.|  
  
## Hinweise  
 Die Vorlagenklasse beschreibt ein ZweiArgumentfunktionselement.  Sie definiert den Memberoperator, `operator()`, wenn das Objekt als Funktion aufgerufen wird, sie true zurückgibt, wenn das erste Argument gleich das zweite ist.  
  
 Sie können das Objekt auch übergeben, da ein Funktionsargument, dessen Typ `delegate_type^` ist und es entsprechend konvertiert wird.  
  
## Beispiel  
  
```  
// cliext_equal_to.cpp   
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
        c2.begin(), c3.begin(), cliext::equal_to<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 3**  
 **4 4**  
 **1 0**   
## Anforderungen  
 **Header:** \<cliext\/funktionsfähig\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [not\_equal\_to](../dotnet/not-equal-to-stl-clr.md)