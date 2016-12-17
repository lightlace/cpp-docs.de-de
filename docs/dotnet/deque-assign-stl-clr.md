---
title: "deque::assign (STL/CLR)"
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
  - "cliext::deque::assign"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "assign-Member [STL/CLR]"
ms.assetid: 03fafdbb-6b10-4464-b3dc-0cc5cb8ac980
caps.latest.revision: 14
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# deque::assign (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ersetzt alle Elemente.  
  
## Syntax  
  
```  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
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
  
## Hinweise  
 Die Memberfunktion die erste ersetzt gesteuerte Sequenz von einer Wiederholung von `count`\-Elemente des Werts `val`.  Sie verwenden sie, um den Container mit allen Elementen füllen, der denselben Wert verfügt.  
  
 Wenn `InIt` ein ganzzahliger Typ ist, verhält sich die zweite Memberfunktion genau wie `assign((size_type)``first``, (value_type)``last``)`.  Andernfalls ersetzt sie die gesteuerte Sequenz nach die Sequenz `[``first``,` `last``)`.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie erstellen einer anderen Sequenz.  
  
 Die dritte Memberfunktion ersetzt die gesteuerte Sequenz nach der Reihenfolge, die der Enumerator `right` festgelegt wird.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer Sequenz erstellen, die von ein Enumerator beschrieben wird.  
  
## Beispiel  
  
```  
// cliext_deque_assign.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::deque<wchar_t> c2;   
    c2.assign(6, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an iterator range   
    c2.assign(c1.begin(), c1.end() - 1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an enumeration   
    c2.assign(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **x x x x x x**  
 **ein b**  
 **ein b c**   
## Anforderungen  
 **Header:** \<cliext\/Doppelschlange\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [deque](../dotnet/deque-stl-clr.md)   
 [operator\= \(deque\)](../dotnet/operator-assign-deque-stl-clr.md)