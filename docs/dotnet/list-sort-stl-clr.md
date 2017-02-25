---
title: "list::sort (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::sort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sort-Member [STL/CLR]"
ms.assetid: f811d5f4-a19e-4194-8765-1e68097c52f0
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# list::sort (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sortiert die kontrollierte Sequenz.  
  
## Syntax  
  
```  
void sort();  
template<typename Pred2>  
    void sort(Pred2 pred);  
```  
  
#### Parameter  
 pred  
 Vergleich für Elementpaaren.  
  
## Hinweise  
 Die erste Memberfunktion ordnet die Elemente in der Sequenz gesteuerten neu damit sie nach `operator<` sortiert werden \- Elemente verringert wird nicht, während Sie die Reihenfolge hinzuzufügen.  Sie verwenden diese Memberfunktion, um die Sequenz in aufsteigender Reihenfolge zu sortieren.  
  
 Die zweite Memberfunktion verhält sich genauso wie das erste, sofern die Sequenz wird nach `pred` sortiert \- `pred``(X, Y)` ist für jedes Element `X` falsch, `Y`\-Element in der resultierenden Sequenz folgt.  Sie verwenden sie, um die Sequenz in einer Reihenfolge zu sortieren, der Sie durch eine Prädikatfunktion oder \-Delegaten angeben.  
  
 Beide Funktionen führen eine stabile Sortierung aus \- kein Paar von Elementen in der ursprünglichen Sequenz gesteuerten wird in die resultierende gesteuerte Sequenz umgekehrt.  
  
## Beispiel  
  
```  
// cliext_list_sort.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// sort descending and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// sort ascending and redisplay   
    c1.sort();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **ein b c**  
 **c a b**  
 **ein b c**   
## Anforderungen  
 **Header:** \<cliext\/Liste\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [list](../dotnet/list-stl-clr.md)   
 [list::merge](../dotnet/list-merge-stl-clr.md)   
 [list::reverse](../dotnet/list-reverse-stl-clr.md)   
 [list::splice](../dotnet/list-splice-stl-clr.md)   
 [list::unique](../dotnet/list-unique-stl-clr.md)