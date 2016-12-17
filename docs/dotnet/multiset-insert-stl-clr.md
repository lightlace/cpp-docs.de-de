---
title: "multiset::insert (STL/CLR)"
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
  - "cliext::multiset::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert-Member [STL/CLR]"
ms.assetid: 7a3b1cc8-ec60-4ed0-ace5-46cb5872e6e7
caps.latest.revision: 13
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# multiset::insert (STL/CLR)
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
// cliext_multiset_insert.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
    System::Console::WriteLine("insert(L'x') = {0}",   
        *c1.insert(L'x'));   
  
    System::Console::WriteLine("insert(L'b') = {0}",   
        *c1.insert(L'b'));   
  
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
    Mymultiset c2;   
    Mymultiset::iterator it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Mymultiset c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **ein b c**  
**Einfüge\- \(L'x\) \= x**  
**Einfüge\- \(L'b b\) \=**  
 **ein b b c x**  
**insert\(begin\(\), L'y\) \= y**  
 **ein b b c x\-y**  
 **ein b b c x**  
 **ein b b c x\-y**   
## Anforderungen  
 **Header:** \<cliext\/Satz\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [multiset](../dotnet/multiset-stl-clr.md)