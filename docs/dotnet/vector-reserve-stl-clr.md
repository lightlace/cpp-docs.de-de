---
title: "vector::reserve (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector::reserve"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reserve-Member [STL/CLR]"
ms.assetid: d1d5ede9-9628-4b55-95ec-f087a57205f2
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# vector::reserve (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt eine minimale Zunahmekapazität für den Container sicher.  
  
## Syntax  
  
```  
void reserve(size_type count);  
```  
  
#### Parameter  
 count  
 Neue Mindestkapazität des Containers.  
  
## Hinweise  
 Die Memberfunktion wird sichergestellt, dass `capacity()` künftig mindestens `count` zurückgibt.  Sie verwenden sie, um sicherzustellen, dass der Container nicht, muss für die Speicher gesteuerte Reihenfolge neu zuzuordnen, bis er sich das an angegebenen Größe entwickelt hat.  
  
## Beispiel  
  
```  
// cliext_vector_reserve.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// increase capacity   
    cliext::vector<wchar_t>::size_type cap = c1.capacity();   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        cap, c1.size() <= cap);   
    c1.reserve(cap + 5);   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        c1.capacity(), cap + 5 <= c1.capacity());   
    return (0);   
    }  
  
```  
  
  **ein b c**  
**capacity\(\) \= 4, darf \= True**  
**capacity\(\) \= 9, darf \= True**   
## **Beschreibung**  
 Beachten Sie, dass die aktuellen Inhalte möglicherweise aus Werten unterscheiden, die hier angezeigt werden, solange aller `ok` Prüfbericht true.  
  
## Anforderungen  
 **Header:** \<cliext\/Vektor\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [Vektor](../dotnet/vector-stl-clr.md)   
 [vector::capacity](../dotnet/vector-capacity-stl-clr.md)   
 [vector::resize](../dotnet/vector-resize-stl-clr.md)