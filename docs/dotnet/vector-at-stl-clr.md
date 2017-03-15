---
title: "vector::at (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector::at"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "at-Member [STL/CLR]"
ms.assetid: 9af9f829-48b8-4906-ba4a-b43454acb2c7
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# vector::at (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Greift auf ein Element in einer angegebenen Position zu.  
  
## Syntax  
  
```  
reference at(size_type pos);  
```  
  
#### Parameter  
 Position  
 Die Position des Elements, auf das zugegriffen wird.  
  
## Hinweise  
 Die Memberfunktion wird ein Verweis auf das Element der Sequenz in Position gesteuerten `pos` zurück.  Sie verwenden sie, um ein Element zu lesen oder zu schreiben, dessen Position Sie kennen.  
  
## Beispiel  
  
```  
// cliext_vector_at.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using at   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// change an entry and redisplay   
    c1.at(1) = L'x';   
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
 [vector::operator](../dotnet/vector-operator-stl-clr.md)