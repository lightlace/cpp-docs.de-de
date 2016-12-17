---
title: "set::insert (STL/CLR)"
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
  - "cliext::set::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert-Member [STL/CLR]"
ms.assetid: 40472869-5c28-4658-b1d3-3ede4d8b8921
caps.latest.revision: 16
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# set::insert (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fügt Elemente hinzu.  
  
## Syntax  
  
```  
cliext::pair<iterator, bool> insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### Parameter  
 first  
 Anfang Einfügen des Bereichs.  
  
 last  
 Ende Einfügen des Bereichs.  
  
 right  
 Einzufügen Enumeration.  
  
 val  
 Einzufügen Schlüsselwert.  
  
 deinen  
 Wo von im Container \(Mallory nur Hinweis\).  
  
## Hinweise  
 Jede der Memberfunktionen fügen eine Sequenz ein, die für die übrigen Operanden angegeben wird.  
  
 Die erste Memberfunktion ermittelt, ein Element mit dem Wert `val` einzufügen und gibt ein Paar Werten `X` zurück.  Wenn `X.second` true ist, legt das `X.first` neu eingefügte Element fest; Andernfalls legt `X.first` ein Element mit entsprechender Reihenfolge fest, die bereits vorhanden ist und kein neues Element wird eingefügt.  Sie verwenden ihn, um ein einzelnes Element einzufügen.  
  
 Die zweite Memberfunktion wird ein Element mit dem Wert `val`, wobei `where` als Hinweis \(Leistung verbessern\) und gibt ein Iterator ein, der das Element neu eingefügte festlegt.  Sie verwenden sie, um ein einzelnes Element einzufügen, das möglicherweise neben einem Element könnte, das, Sie kennen.  
  
 Die dritte Memberfunktion wird die Sequenz `[``first``,` `last``)`.  Sie verwenden sie, dass Nullen oder mehr Elemente einfügen kopiert aus einer anderen Sequenz.  
  
 Die vierte Memberfunktion wird die Sequenz ein, die durch `right` festgelegt ist.  Sie verwenden sie, um eine Sequenz einzufügen, die Angriffen einen Enumerator beschrieben wird.  
  
 Jede Einfügen wird die Zeit, die z Logarithmus der Anzahl der Elemente in der Sequenz gesteuerten proportional ist.  Einfüge\- kann in der amortisierten konstanten Zeitpunkt auftreten einen Hinweis jedoch zugewiesen, der ein Element neben der Einfügemarke festlegt.  
  
## Beispiel  
  
```  
// cliext_set_insert.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
typedef Myset::pair_iter_bool Pairib;   
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
  
// insert a single value, unique and duplicate   
    Pairib pair1 = c1.insert(L'x');   
    System::Console::WriteLine("insert(L'x') = [{0} {1}]",   
        *pair1.first, pair1.second);   
  
    pair1 = c1.insert(L'b');   
    System::Console::WriteLine("insert(L'b') = [{0} {1}]",   
        *pair1.first, pair1.second);   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    System::Console::WriteLine("insert(begin(), L'y') = {0}",   
        *c1.insert(c1.begin(), L'y'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Myset c2;   
    Myset::iterator it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Myset c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **ein b c**  
**Einfüge\- \(L'x\) \= \[x True\]**  
**Einfüge\- \(L'b\) \= \[b False\]**  
 **ein b c x**  
**insert\(begin\(\), L'y\) \= y**  
 **ein x\-y b c**  
 **ein b c x**  
 **ein x\-y b c**   
## Anforderungen  
 **Header:** \<cliext\/Satz\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [set](../dotnet/set-stl-clr.md)