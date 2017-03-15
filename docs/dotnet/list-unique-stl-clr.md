---
title: "list::unique (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::unique"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unique-Member [STL/CLR]"
ms.assetid: c3a29e4e-0ec1-4472-b050-7a9511037132
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# list::unique (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Entfernt benachbarte Elemente, die einen angegebenen Test bestehen.  
  
## Syntax  
  
```  
void unique();  
template<typename Pred2>  
    void unique(Pred2 pred);  
```  
  
#### Parameter  
 pred  
 Vergleich für Elementpaaren.  
  
## Hinweise  
 Die erste Memberfunktion entfernt der gesteuerten Sequenz \(Löschen\) jedes Element, das gleich sein Im vorangehenden Element vergleicht \- wenn Element `X`\-Element `Y` und `X == Y` stehen, entfernt die Memberfunktion `Y`.  Sie verwenden sie, um alle bis auf eine Kopie einer Untersequenz der benachbarten Elemente zu entfernen, die gleich vergleichen.  Beachten Sie, dass, wenn die gesteuerte Sequenz, sortiert wird, wie mit dem [list::sort](../dotnet/list-sort-stl-clr.md)`()`, die Memberfunktion aufruft, nur Elemente mit eindeutigen Werte können. \(Daher der Name\).  
  
 Die zweite Memberfunktion verhält sich genauso wie das erste, allerdings entfernt jedes Element `Y`, das dem `X` ein Element erfolgreich ist, für das `pred``(X, Y)`.  Sie verwenden sie, um alle bis auf eine Kopie einer Untersequenz der benachbarten Elemente zu entfernen, die einer Prädikatfunktion entsprechen oder Delegat, die Sie angeben.  Beachten Sie, dass, wenn die gesteuerte Sequenz, sortiert wird z, indem `sort(``pred``)`, die Memberfunktion aufruft, können nur Elemente, die keine ihnen entsprechenden Reihenfolge mit einer beliebigen anderen Elementen aufweisen.  
  
## Beispiel  
  
```  
// cliext_list_unique.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique   
    cliext::list<wchar_t> c2(c1);   
    c2.unique();   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique(not_equal_to)   
    c2 = c1;   
    c2.unique(cliext::not_equal_to<wchar_t>());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **ein b c**  
 **ein b c**  
 **ein "**   
## Anforderungen  
 **Header:** \<cliext\/Liste\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [list](../dotnet/list-stl-clr.md)   
 [list::remove](../dotnet/list-remove-stl-clr.md)   
 [list::remove\_if](../dotnet/list-remove-if-stl-clr.md)   
 [list::sort](../dotnet/list-sort-stl-clr.md)