---
title: "hash_multimap::insert (STL/CLR)"
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
  - "cliext::hash_multimap::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert-Member [STL/CLR]"
ms.assetid: 51cd98b0-c959-4a44-b914-582c00681bd7
caps.latest.revision: 15
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multimap::insert (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fügt Elemente hinzu.  
  
## Syntax  
  
```  
iterator insert(value_type val);  
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
  
 Die erste Memberfunktion wird ein Element mit dem Wert `val` und gibt ein Iterator zurück, der das Element neu eingefügte festlegt.  Sie verwenden ihn, um ein einzelnes Element einzufügen.  
  
 Die zweite Memberfunktion wird ein Element mit dem Wert `val`, wobei `where` als Hinweis \(Leistung verbessern\) und gibt ein Iterator ein, der das Element neu eingefügte festlegt.  Sie verwenden sie, um ein einzelnes Element einzufügen, das möglicherweise neben einem Element könnte, das, Sie kennen.  
  
 Die dritte Memberfunktion wird die Sequenz `[``first``,` `last``)`.  Sie verwenden sie, dass Nullen oder mehr Elemente einfügen kopiert aus einer anderen Sequenz.  
  
 Die vierte Memberfunktion wird die Sequenz ein, die durch `right` festgelegt ist.  Sie verwenden sie, um eine Sequenz einzufügen, die Angriffen einen Enumerator beschrieben wird.  
  
 Jede Einfügen wird die Zeit, die z Logarithmus der Anzahl der Elemente in der Sequenz gesteuerten proportional ist.  Einfüge\- kann in der amortisierten konstanten Zeitpunkt auftreten einen Hinweis jedoch zugewiesen, der ein Element neben der Einfügemarke festlegt.  
  
## Beispiel  
  
```  
// cliext_hash_multimap_insert.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
    Myhash_multimap::iterator it =   
        c1.insert(Myhash_multimap::make_value(L'x', 24));   
    System::Console::WriteLine("insert([L'x' 24]) = [{0} {1}]",   
        it->first, it->second);   
  
    it = c1.insert(Myhash_multimap::make_value(L'b', 2));   
    System::Console::WriteLine("insert([L'b' 2]) = [{0} {1}]",   
        it->first, it->second);   
  
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    it = c1.insert(c1.begin(), Myhash_multimap::make_value(L'y', 25));   
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",   
        it->first, it->second);   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Myhash_multimap c2;   
    it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (Myhash_multimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Myhash_multimap c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::   
            IEnumerable<Myhash_multimap::value_type>^)%c1);   
    for each (Myhash_multimap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[bc 3\]**  
**Einfüge\- \(\[L'x 24\) \= \[\]x 24\]**  
**Einfüge\- \(\[L'b 2\) \= \[\]b 2\]**  
 **\[1\] \[2\] \[b b 2\] \[3\] \[cx 24\]**  
**insert\(begin\(\), \[L'y 25\) \= \[\]y 25\]**  
 **\[1\] \[2\] \[b b c 2\] \[3\] \[24\] \[xy 25\]**  
 **\[1\] \[2\] \[b b 2\] \[3\] \[cx 24\]**  
 **\[1\] \[2\] \[b b c 2\] \[3\] \[24\] \[xy 25\]**   
## Anforderungen  
 **Header:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)