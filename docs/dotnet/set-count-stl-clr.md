---
title: "set::count (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set::Count"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "count-Member [STL/CLR]"
ms.assetid: 78855f8c-3de5-4d3e-800b-0bbea5e829dd
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# set::count (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sucht die Anzahl von Elementen, die einen angegebenen Schlüssel übereinstimmen.  
  
## Syntax  
  
```  
size_type count(key_type key);  
```  
  
#### Parameter  
 Schlüssel  
 Für zu suchen Schlüsselwert.  
  
## Hinweise  
 Die Memberfunktion wird die Anzahl der Elemente in der Sequenz zurück gesteuerten, die entsprechende Reihenfolge mit `key` haben.  Damit können Sie die Anzahl der Elemente in der kontrollierten Sequenz ermitteln, die derzeit einem angegebenen Schlüssel entsprechen.  
  
## Beispiel  
  
```  
// cliext_set_count.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));   
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));   
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));   
    return (0);   
    }  
  
```  
  
  **ein b c**  
**Anzahl \(L'A\) \= 0**  
**Anzahl \(L'b\) \= 1**  
**Anzahl \(L'C\) \= 0**   
## Anforderungen  
 **Header:** \<cliext\/Satz\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [set](../dotnet/set-stl-clr.md)   
 [set::equal\_range](../dotnet/set-equal-range-stl-clr.md)