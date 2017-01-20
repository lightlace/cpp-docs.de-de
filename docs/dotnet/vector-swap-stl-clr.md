---
title: "vector::swap (STL/CLR)"
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
  - "cliext::vector::swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "swap-Member [STL/CLR]"
ms.assetid: 9ad083fe-f79b-4b97-8013-581fd00c059a
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# vector::swap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vertauscht den Inhalt von zwei Containern.  
  
## Syntax  
  
```  
void swap(vector<Value>% right);  
```  
  
#### Parameter  
 right  
 Container, mit denen Inhalt getauscht werden soll.  
  
## Hinweise  
 Die Memberfunktion tauscht die gesteuerten Sequenzen zwischen `*this` und `right` aus.  Sie geschieht bei der konstanten Zeit und es löst keine Ausnahmen aus.  Sie verwenden sie als schnelle Möglichkeit, der Inhalt zweier Containern auszutauschen.  
  
## Beispiel  
  
```  
// cliext_vector_swap.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::vector<wchar_t> c2(5, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **ein b c**  
 **x x x x x**  
 **x x x x x**  
 **ein b c**   
## Anforderungen  
 **Header:** \<cliext\/Vektor\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [Vektor](../dotnet/vector-stl-clr.md)   
 [vector::assign](../dotnet/vector-assign-stl-clr.md)   
 [vector::operator\=](../dotnet/vector-operator-assign-stl-clr.md)