---
title: "set::operator= (STL/CLR)"
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
  - "cliext::set::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Operator= Member [STL/CLR]"
ms.assetid: 14e16799-d188-4e0d-a0ce-be2c98f93cc8
caps.latest.revision: 8
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# set::operator= (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ersetzt die gesteuerte Sequenz.  
  
## Syntax  
  
```  
set<Key>% operator=(set<Key>% right);  
```  
  
#### Parameter  
 right  
 Container zu kopieren.  
  
## Hinweise  
 Der Member, den Operator `right` zum Objekt kopiert, dann, `*this` zurückgibt.  Sie verwenden sie, um die gesteuerte Sequenz durch eine Kopie der gesteuerten Sequenz in `right` zu ersetzen.  
  
## Beispiel  
  
```  
// cliext_set_operator_as.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (Myset::value_type elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myset c2;   
    c2 = c1;   
// display contents " a b c"   
    for each (Myset::value_type elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **ein b c**  
 **ein b c**   
## Anforderungen  
 **Header:** \<cliext\/Satz\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [set](../dotnet/set-stl-clr.md)