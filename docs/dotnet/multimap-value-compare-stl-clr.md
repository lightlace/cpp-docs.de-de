---
title: "multimap::value_compare (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::value_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_compare-Member [STL/CLR]"
ms.assetid: a066968b-df6e-40a7-83fd-b8520b07a1e0
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# multimap::value_compare (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Reihenfolgendelegat für zwei Elementwerte.  
  
## Syntax  
  
```  
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>  
    value_compare;  
```  
  
## Hinweise  
 Der Typ ist ein Synonym für den Delegaten, der die Reihenfolge ihrer Wertargumente bestimmt.  
  
## Beispiel  
  
```  
// cliext_multimap_value_compare.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    Mymultimap::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",   
        kcomp(Mymultimap::make_value(L'a', 1),   
            Mymultimap::make_value(L'a', 1)));   
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",   
        kcomp(Mymultimap::make_value(L'a', 1),   
            Mymultimap::make_value(L'b', 2)));   
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",   
        kcomp(Mymultimap::make_value(L'b', 2),   
            Mymultimap::make_value(L'a', 1)));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **Vergleichen \(\[L'a, 1\], \[L'a, 1\] \= False\)**  
**Vergleichen \(\[L'a, 1\], \[L'b, 2\]\) \= True**  
**Vergleichen \(\[L'b, 2\], \[L'a, 1\] \= False\)**   
## Anforderungen  
 **Header:** \<cliext\/Zuordnung\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::key\_compare](../dotnet/multimap-key-compare-stl-clr.md)   
 [multimap::value\_comp](../dotnet/multimap-value-comp-stl-clr.md)   
 [multimap::value\_type](../dotnet/multimap-value-type-stl-clr.md)