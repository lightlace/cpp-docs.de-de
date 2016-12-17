---
title: "list::merge (STL/CLR)"
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
  - "cliext::list::merge"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "merge-Member [STL/CLR]"
ms.assetid: f8e93cd3-bd08-4086-859b-08a2899cc9a6
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# list::merge (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Führt zwei geordnete kontrollierte Sequenzen zusammen.  
  
## Syntax  
  
```  
void merge(list<Value>% right);  
template<typename Pred2>  
    void merge(list<Value>% right, Pred2 pred);  
```  
  
#### Parameter  
 pred  
 Vergleich für Elementpaaren.  
  
 right  
 Container, z in zusammenzuführen.  
  
## Hinweise  
 Die erste Memberfunktion entfernt alle Elemente der Sequenz, die durch `right` gesteuert wird und fügt diese gesteuerten in der Sequenz.  Beide Sequenzen müssen durch `operator<` zuvor sortiert werden \- Elemente dürfen nicht verringert wird, indem Sie jede Sequenz fortschreiten.  Die resultierende Sequenz wird auch nach `operator<` sortiert.  Sie verwenden diese Memberfunktion, um zwei Sequenzen diese Erhöhung des Werts in eine Sequenz auch zusammenzuführen, die Anwendungsleistung des Werts dieser ist.  
  
 Die zweite Memberfunktion verhält sich genauso wie das erste, sofern die Sequenzen werden nach `pred` sortiert \- `pred``(X, Y)` muss für jedes Element `X` falsch, das Element in der Sequenz `Y` folgt.  Sie verwenden sie, um zwei Sequenzen zusammenzuführen, die von einer Prädikatfunktion oder zu delegieren sortiert werden, die Sie angeben.  
  
 Beide Funktionen führen eine stabile Zusammenführung aus \- kein Elementpaar in keiner der ursprünglichen gesteuerten Sequenzen wird in die resultierende gesteuerte Sequenz umgekehrt.  Wenn ein Paar Elemente `X` und `Y` in der resultierenden Sequenz gesteuerten entsprechende Reihenfolge hat \- `!(X < Y) && !(X < Y)` \- ein Element von der ursprünglichen Sequenz gesteuerten wird vor einem Element der Sequenz, die durch `right` gesteuert wird.  
  
## Beispiel  
  
```  
// cliext_list_merge.cpp   
// compile with: /clr   
#include <cliext/list>   
  
typedef cliext::list<wchar_t> Mylist;   
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'c');   
    c1.push_back(L'e');   
  
// display initial contents " a c e"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    cliext::list<wchar_t> c2;   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
    c2.push_back(L'f');   
  
// display initial contents " b d f"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// merge and display   
    cliext::list<wchar_t> c3(c1);   
    c3.merge(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
  
// sort descending, merge descending, and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.merge(c1, cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
  **a\-c e**  
 **b d f**  
 **a b c d e f**  
**c2.size\(\) \= 0**  
 **EG auf**  
 **F\-Ed c a b**  
 **F\-Ee d c c a b ein**  
**c1.size\(\) \= 0**   
## Anforderungen  
 **Header:** \<cliext\/Liste\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [list](../dotnet/list-stl-clr.md)   
 [list::sort](../dotnet/list-sort-stl-clr.md)   
 [list::splice](../dotnet/list-splice-stl-clr.md)