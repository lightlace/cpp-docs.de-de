---
title: "list::splice (STL/CLR)"
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
  - "cliext::list::splice"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "splice-Member [STL/CLR]"
ms.assetid: ebc424b9-8341-4a88-b101-86d56324f5ac
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# list::splice (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Restitch\-Links zwischen Knoten.  
  
## Syntax  
  
```  
void splice(iterator where, list<Value>% right);  
void splice(iterator where, list<Value>% right,  
    iterator first);  
void splice(iterator where, list<Value>% right,  
    iterator first, iterator last);  
```  
  
#### Parameter  
 first  
 Anfang zum Verbinden des Bereichs.  
  
 last  
 Ende zum Verbinden des Bereichs.  
  
 right  
 Ziehen zum Verbinden, Container.  
  
 deinen  
 Wo von im Container zuvor eine Verbindung herstellt.  
  
## Hinweise  
 Die Memberfunktion wird die erste Sequenz ein, die durch `right` vor dem Element in der Sequenz gesteuerten gesteuert wird, die auf den durch `where` gezeigt wird.  Sie entfernt auch alle Elemente von `right`. \(`%``right``this` darf nicht entsprechen.\) Sie verwenden sie, um die ganze Liste in eine andere zu verbinden.  
  
 Die zweite Memberfunktion entfernt das Element, auf den durch in der Sequenz `first` dargestellt wird, die durch `right` gesteuert wird und fügt es vor dem Element in der Sequenz gesteuerten ein, die auf den durch `where` gezeigt wird. \(Wenn `where` `==` `first` `||` `where` `== ++``first`, keine Änderung.\) Sie verwenden ihn, um ein einzelnes Element aus einer Liste in andere zu verbinden.  
  
 Die dritte Memberfunktion fügt den Unterbereich ein, der vom `[``first``,` `last``)` über die Reihenfolge festgelegt wird, die von `right` vor dem Element in der Sequenz gesteuerten gesteuert wird, die auf den durch `where` gezeigt wird.  Sie entfernt auch den ursprünglichen Unterbereich der Sequenz, die durch `right` gesteuert wird. \(Wenn `right` `==` `this`, des `[``first``,` `last``)`\-Element nicht angeben darf, auf den durch `where` gezeigt wird\). Sie verwenden sie, um eine Untersequenz von null oder mehr Elementen aus einer Liste in andere zu verbinden.  
  
## Beispiel  
  
```  
// cliext_list_splice.cpp   
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
  
// splice to a new list   
    cliext::list<wchar_t> c2;   
    c2.splice(c2.begin(), c1);   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// return one element   
    c1.splice(c1.end(), c2, c2.begin());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// return remaining elements   
    c1.splice(c1.begin(), c2, c2.begin(), c2.end());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
    return (0);   
    }  
  
```  
  
  **ein b c**  
**c1.size\(\) \= 0**  
 **ein b c**  
 **a**  
 **b c**  
 **c a b**  
**c2.size\(\) \= 0**   
## Anforderungen  
 **Header:** \<cliext\/Liste\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [list](../dotnet/list-stl-clr.md)   
 [list::assign](../dotnet/list-assign-stl-clr.md)   
 [list::insert](../dotnet/list-insert-stl-clr.md)   
 [list::merge](../dotnet/list-merge-stl-clr.md)