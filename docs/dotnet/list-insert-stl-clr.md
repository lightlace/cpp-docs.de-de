---
title: "list::insert (STL/CLR)"
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
  - "cliext::list::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert-Member [STL/CLR]"
ms.assetid: 399ed30f-6b76-41a8-b180-6070e3ca1c68
caps.latest.revision: 16
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# list::insert (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fügt Elemente in einer bestimmten Position hinzu.  
  
## Syntax  
  
```  
iterator insert(iterator where, value_type val);  
void insert(iterator where, size_type count, value_type val);  
template<typename InIt>  
    void insert(iterator where, InIt first, InIt last);  
void insert(iterator where,  
    System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### Parameter  
 count  
 Zahl einzufügen Elemente.  
  
 first  
 Anfang Einfügen des Bereichs.  
  
 last  
 Ende Einfügen des Bereichs.  
  
 right  
 Einzufügen Enumeration.  
  
 val  
 Wert des Elements eingefügt.  
  
 deinen  
 Wo von im Container zuvor einfügt.  
  
## Hinweise  
 Jede der Memberfunktionen fügen, vor dem Element ein, das von `where` in der Sequenz gesteuerten, eine Sequenz dargestellt wird, die von der verbleibenden Operanden angegeben wird.  
  
 Die erste Memberfunktion wird ein Element mit dem Wert `val` und gibt ein Iterator zurück, der das Element neu eingefügte festlegt.  Sie verwenden sie, um ein einzelnes Element vor einer Stelle einzufügen, der durch einen Iterator festgelegt wird.  
  
 Die zweite Memberfunktion fügt eine Wiederholung der `count`\-Elemente des Werts `val` ein.  Sie verwenden ihn, dass Nullen oder einzufügen zusammenhängendere Elemente, die alle Kopien des gleichen Wert sind.  
  
 Wenn `InIt` ein ganzzahliger Typ ist, verhält sich die dritte Memberfunktion genau wie `insert(``where``, (size_type)``first``, (value_type)``last``)`.  Andernfalls wird die Sequenz `[``first``,` `last``)`.  Sie verwenden sie, um die mit keinem oder einzufügen zusammenhängenderen kopierte Elemente einer anderen Sequenz.  
  
 Die vierte Memberfunktion wird die Sequenz ein, die durch `right` festgelegt ist.  Sie verwenden sie, um eine Sequenz einzufügen, die Angriffen einen Enumerator beschrieben wird.  
  
 Wenn es ein einzelnes Element einfügt, ist die Anzahl der Elementkopien in der Anzahl von Elementen zwischen der Einfügemarke und dem näheren Ende der Sequenz linear. \(Wenn Sie eine oder mehrere Elemente an jedem Ende der Sequenz einfügen, treten keine Elementkopien.\) Wenn `InIt` ein Eingabeiterator ist, führt die dritte Memberfunktion effektiv eine einzelnen Einfüge\- für jedes Element in der Sequenz aus.  Wenn sie `N`\-Elemente einfügen, ist die Anzahl der in `N`\-Elementkopien sowie die Anzahl der Elemente zwischen der Einfügemarke und dem näheren Ende der Sequenz linear.  
  
## Beispiel  
  
```  
// cliext_list_insert.cpp   
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
  
// insert a single value using iterator   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",   
        *c1.insert(++it, L'x'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a repetition of values   
    cliext::list<wchar_t> c2;   
    c2.insert(c2.begin(), 2, L'y');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    it = c1.end();   
    c2.insert(c2.end(), c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    c2.insert(c2.begin(),   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using index   
    it = c2.begin();   
    ++it, ++it, ++it;   
    c2.insert(it, L'z');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **ein b c**  
**insert\(begin\(\)\+1, L'x\) \= x**  
 **x b c ein**  
 **y y**  
 **y y ein x b**  
 **ein x b c y y ein x b**   
## Anforderungen  
 **Header:** \<cliext\/Liste\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [list](../dotnet/list-stl-clr.md)   
 [list::assign](../dotnet/list-assign-stl-clr.md)