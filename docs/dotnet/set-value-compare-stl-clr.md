---
title: "set::value_compare (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set::value_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_compare-Member [STL/CLR]"
ms.assetid: cf45d7ae-5cd1-4633-9fe6-f0b97730465c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# set::value_compare (STL/CLR)
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
// cliext_set_value_compare.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    Myset::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **Vergleichen \(L'a, L'a\) \= False**  
**Vergleichen \(L'a, L'b\) \= True**  
**Vergleichen \(L'b, L'a\) \= False**   
## Anforderungen  
 **Header:** \<cliext\/Satz\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [set](../dotnet/set-stl-clr.md)   
 [set::key\_compare](../dotnet/set-key-compare-stl-clr.md)   
 [set::value\_comp](../dotnet/set-value-comp-stl-clr.md)   
 [set::value\_type](../dotnet/set-value-type-stl-clr.md)