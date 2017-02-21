---
title: "pair::pair (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::pair::pair"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pair-Member [STL/CLR]"
ms.assetid: 188035f3-bd37-4b46-96dd-5ceb9a16df79
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# pair::pair (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein Paarobjekt.  
  
## Syntax  
  
```  
pair();  
pair(pair<Coll>% right);  
pair(pair<Coll>^ right);  
pair(Value1 val1, Value2 val2);  
```  
  
#### Parameter  
 right  
 So speichern von Paaren.  
  
 val1  
 Erster gespeichert Wert.  
  
 val2  
 Zweite speichern Wert.  
  
## Hinweise  
 Der Konstruktor:  
  
 `pair();`  
  
 initialisiert die gespeicherten Paare mit Standard erstellten Werte.  
  
 Der Konstruktor:  
  
 `pair(pair<Value1, Value2>% right);`  
  
 initialisiert die gespeicherten Paare mit `right``.``right``.`[pair::first](../dotnet/pair-first-stl-clr.md) und [pair::second](../dotnet/pair-second-stl-clr.md).  
  
 `pair(pair<Value1, Value2>^ right);`  
  
 initialisiert die gespeicherten Paare mit `right``->``right``>`[pair::first](../dotnet/pair-first-stl-clr.md) und [pair::second](../dotnet/pair-second-stl-clr.md).  
  
 Der Konstruktor:  
  
 `pair(Value1 val1, Value2 val2);`  
  
 initialisiert die gespeicherten Paare mit `val1` und `val2`.  
  
## Beispiel  
  
```  
// cliext_pair_construct.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
// construct an empty container   
    cliext::pair<wchar_t, int> c1;   
    System::Console::WriteLine("[{0}, {1}]",   
        c1.first == L'\0' ? "\\0" : "??", c1.second);   
  
// construct with a pair of values   
    cliext::pair<wchar_t, int> c2(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
// construct by copying another pair   
    cliext::pair<wchar_t, int> c3(c2);   
    System::Console::WriteLine("[{0}, {1}]", c3.first, c3.second);   
  
// construct by copying a pair handle   
    cliext::pair<wchar_t, int> c4(%c3);   
    System::Console::WriteLine("[{0}, {1}]", c4.first, c4.second);   
  
    return (0);   
    }  
  
```  
  
  **\[\\0, 0\]**  
**\[x, 3\]**  
**\[x, 3\]**  
**\[x, 3\]**   
## Anforderungen  
 **Header:** \<cliext\/Hilfsprogramm\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [pair](../dotnet/pair-stl-clr.md)