---
title: "negate (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::negate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "negate-Funktion [STL/CLR]"
ms.assetid: 58e4c339-0dee-4db8-b2cc-de8920977039
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# negate (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Funktionselement, die, wenn sie aufgerufen wird, das negierten Argument zurückgibt.  Sie verwenden sie angeben einem Funktionsobjekt hinsichtlich den Argumenttyp.  
  
## Syntax  
  
```  
template<typename Arg>  
    ref class negate  
    { // wrap operator()  
public:  
    typedef Arg argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        argument_type, result_type>  
        delegate_type;  
  
    negate();  
    negate(negate<Arg>% right);  
  
    result_type operator()(argument_type left);  
    operator delegate_type^();  
    };  
```  
  
#### Parameter  
 Arg  
 Der Typ der Argumente.  
  
## Memberfunktionen  
  
|Typdefinition|**Beschreibung**|  
|-------------------|----------------------|  
|argument\_type|Der Typ des Funktionselementarguments.|  
|delegate\_type|Der Typ des generischen Delegaten.|  
|result\_type|Der Typ des Funktionselementergebnisses.|  
  
|Member|**Beschreibung**|  
|------------|----------------------|  
|negate|Erstellt das Funktionselement.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|operator\(\)|Berechnet die gewünschte Funktion.|  
|Operator delegate\_type^|Wandelt das Funktionselement zu einem Delegaten um.|  
  
## Hinweise  
 Die Vorlagenklasse beschreibt ein EinArgumentfunktionselement.  Sie definiert den Memberoperator, `operator()`, wenn das Objekt als Funktion aufgerufen wird, den sie negierten Argument zurückgibt.  
  
 Sie können das Objekt auch übergeben, da ein Funktionsargument, dessen Typ `delegate_type^` ist und es entsprechend konvertiert wird.  
  
## Beispiel  
  
```  
// cliext_negate.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(-3);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 -3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c3.begin(), cliext::negate<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 \-3**  
 **\-4 3**   
## Anforderungen  
 **Header:** \<cliext\/funktionsfähig\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [logical\_not](../dotnet/logical-not-stl-clr.md)