---
title: "list::to_array (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::to_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "to_array-Member [STL/CLR]"
ms.assetid: 3ea7b90c-127b-43cd-804b-019b86b77582
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# list::to_array (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Kopiert die gesteuerte Sequenz zu einem neuen Array.  
  
## Syntax  
  
```  
cli::array<Value>^ to_array();  
```  
  
## Hinweise  
 Die Memberfunktion gibt ein Array zurück, das die gesteuerte Sequenz enthält.  Sie verwenden sie, um eine Kopie der gesteuerten Sequenz in der Arrayform zu erhalten.  
  
## Beispiel  
  
```  
// cliext_list_to_array.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.push_back(L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **ein b c d**  
 **ein b c**   
## Anforderungen  
 **Header:** \<cliext\/Liste\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [list](../dotnet/list-stl-clr.md)