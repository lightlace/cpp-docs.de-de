---
title: "vector::operator(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector::operator[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operatormember [] [STL/CLR]"
ms.assetid: 379a7029-460d-4de8-918b-c79e3e13b9d4
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# vector::operator(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Greift auf ein Element in einer angegebenen Position zu.  
  
## Syntax  
  
```  
reference operator[](size_type pos);  
```  
  
#### Parameter  
 Position  
 Die Position des Elements, auf das zugegriffen wird.  
  
## Hinweise  
 Der Memberoperator gibt ein referene dem Element in Position `pos` zurück.  Sie verwenden sie, um auf ein Element zugreifen, dessen Position Sie kennen.  
  
## Beispiel  
  
```  
// cliext_vector_operator_sub.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using subscripting   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
  
// change an entry and redisplay   
    c1[1] = L'x';   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **ein b c**  
 **x c ein**   
## Anforderungen  
 **Header:** \<cliext\/Vektor\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [Vektor](../dotnet/vector-stl-clr.md)   
 [vector::at](../dotnet/vector-at-stl-clr.md)