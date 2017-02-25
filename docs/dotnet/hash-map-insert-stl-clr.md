---
title: "hash_map::insert (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_map::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert-Member [STL/CLR]"
ms.assetid: 52926ec7-ad4e-4791-a043-46136ee40a69
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# hash_map::insert (STL/CLR)
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
// cliext_hash_map_insert.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
typedef Myhash_map::pair_iter_bool Pairib;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
    Pairib pair1 =   
        c1.insert(Myhash_map::make_value(L'x', 24));   
    System::Console::WriteLine("insert([L'x' 24]) = [{0} {1}] {2}",   
        pair1.first->first, pair1.first->second, pair1.second);   
  
    pair1 = c1.insert(Myhash_map::make_value(L'b', 2));   
    System::Console::WriteLine("insert([L'b' 2]) = [{0} {1}] {2}",   
        pair1.first->first, pair1.first->second, pair1.second);   
  
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    Myhash_map::iterator it =   
        c1.insert(c1.begin(), Myhash_map::make_value(L'y', 25));   
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",   
        it->first, it->second);   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Myhash_map c2;   
    it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (Myhash_map::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Myhash_map c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::   
            IEnumerable<Myhash_map::value_type>^)%c1);   
    for each (Myhash_map::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[bc 3\]**  
**Einfüge\- \(\[L'x 24\]\) \= \[\] True x 24**  
**Einfüge\- \(\[L'b 2\]\) \= \[b 2\] False**  
 **\[1\] \[b 2\] \[3\] \[cx 24\]**  
**insert\(begin\(\), \[L'y 25\) \= \[\]y 25\]**  
 **\[1\] \[2\] \[b c x 3\] \[24\] \[y 25\]**  
 **\[1\] \[b 2\] \[3\] \[cx 24\]**  
 **\[1\] \[2\] \[b c x 3\] \[24\] \[y 25\]**   
## Anforderungen  
 **Header:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_map](../dotnet/hash-map-stl-clr.md)