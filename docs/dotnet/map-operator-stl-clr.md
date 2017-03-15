---
title: "map::operator(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::map::operator[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operatormember [] [STL/CLR]"
ms.assetid: 50e494c5-62d4-4469-8da3-7432ee4dff97
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# map::operator(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ordnet eine Schlüssel mit dem zugeordneten zugeordneten Wert zu.  
  
## Syntax  
  
```  
mapped_type operator[](key_type key);  
```  
  
#### Parameter  
 Schlüssel  
 Für zu suchen Schlüsselwert.  
  
## Hinweise  
 Die Memberfunktionen ermittelt, ein Element mit entsprechender Reihenfolge in `key` zu suchen.  Sofern die Methode fündig wird, gibt sie den zugeordneten zugeordneten Wert zurück; Andernfalls wird sie `value_type(``key``, mapped_type())` und gibt das zugeordnete \(Standard\) zugeordneten Wert zurück.  Sie verwenden sie, um einen zugeordneten Wert gesucht werden, dessen zugeordnete Schlüssel, oder sicherzustellen angegeben ist, dass ein Eintrag für die Schlüssel vorhanden ist, wenn kein solcher Block gefunden wird.  
  
## Beispiel  
  
```  
// cliext_map_operator_sub.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("c1[{0}] = {1}",   
        L'A', c1[L'A']);   
    System::Console::WriteLine("c1[{0}] = {1}",   
        L'b', c1[L'b']);   
  
// redisplay altered contents   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// alter mapped values and redisplay   
    c1[L'A'] = 10;   
    c1[L'c'] = 13;   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[bc 3\]**  
**A \[c1\] \= 0**  
**\[c1 b\] \= 2**  
 **A \[0\] \[1\] \[2\] \[bc 3\]**  
 **A \[10\] \[1\] \[2\] \[bc 13\]**   
## Anforderungen  
 **Header:** \<cliext\/Zuordnung\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [map](../dotnet/map-stl-clr.md)   
 [map::find](../dotnet/map-find-stl-clr.md)   
 [map::insert](../dotnet/map-insert-stl-clr.md)