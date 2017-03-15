---
title: "vector::operator= (STL/CLR)"
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
  - "cliext::vector::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Operator= Member [STL/CLR]"
ms.assetid: c2de9d74-9de7-4560-866f-3d55952e9bd7
caps.latest.revision: 16
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# vector::operator= (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ersetzt die gesteuerte Sequenz.  
  
## Syntax  
  
```  
vector<Value>% operator=(vector<Value>% right);  
```  
  
#### Parameter  
 right  
 Container zu kopieren.  
  
## Hinweise  
 Der Member, den Operator `right` zum Objekt kopiert, dann, `*this` zurückgibt.  Sie verwenden sie, um die gesteuerte Sequenz durch eine Kopie der gesteuerten Sequenz in `right` zu ersetzen.  
  
## Beispiel  
  
```  
// cliext_vector_operator_as.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
    c2 = c1;   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **ein b c**  
 **ein b c**   
## Anforderungen  
 **Header:** \<cliext\/Vektor\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [Vektor](../dotnet/vector-stl-clr.md)   
 [vector::assign](../dotnet/vector-assign-stl-clr.md)