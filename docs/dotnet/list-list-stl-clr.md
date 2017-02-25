---
title: "list::list (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::list"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Listenmember [STL/CLR]"
ms.assetid: 51b58f63-c65a-4d54-b746-0c10635b123b
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# list::list (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein container\-Objekt.  
  
## Syntax  
  
```  
list();  
list(list<Value>% right);  
list(list<Value>^ right);  
explicit list(size_type count);  
list(size_type count, value_type val);  
template<typename InIt>  
    list(InIt first, InIt last);  
list(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### Parameter  
 count  
 Zahl einzufügen Elemente.  
  
 first  
 Anfang Einfügen des Bereichs.  
  
 last  
 Ende Einfügen des Bereichs.  
  
 right  
 Objekt oder Bereich Einfüge\-.  
  
 val  
 Wert des Elements eingefügt.  
  
## Hinweise  
 Der Konstruktor:  
  
 `list();`  
  
 initialisiert die gesteuerte Sequenz ohne Elemente.  Sie verwenden sie, um eine leere ursprünglichen gesteuerten Sequenz angeben.  
  
 Der Konstruktor:  
  
 `list(list<Value>% right);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``right``.`[list::begin](../dotnet/list-begin-stl-clr.md)`(),` `right``.`[list::end](../dotnet/list-end-stl-clr.md)`())`.  Sie verwenden sie, um einer gesteuerten ursprünglichen Sequenz angeben, die eine Kopie dieser Folge ist das Listenobjekt, die durch `right` gesteuert wird.  
  
 Der Konstruktor:  
  
 `list(list<Value>^ right);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``right``->`[list::begin](../dotnet/list-begin-stl-clr.md)`(),` `right``->`[list::end](../dotnet/list-end-stl-clr.md)`())`.  Sie verwenden sie, um einer gesteuerten ursprünglichen Sequenz angeben, die eine Kopie dieser Folge ist, die das Listenobjekt gesteuert wird, dessen Handle `right` ist.  
  
 Der Konstruktor:  
  
 `explicit list(size_type count);`  
  
 initialisiert die gesteuerte Sequenz mit `count`\-Elemente jede mit Wert `value_type()`.  Sie verwenden ihn, um den Container mit allen Elementen füllen, der den Standardwert aufweist.  
  
 Der Konstruktor:  
  
 `list(size_type count, value_type val);`  
  
 initialisiert die gesteuerte Sequenz mit `count`\-Elemente jede mit Wert `val`.  Sie verwenden sie, um den Container mit allen Elementen füllen, der denselben Wert verfügt.  
  
 Der Konstruktor:  
  
 `template<typename InIt>`  
  
 `list(InIt first, InIt last);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``first``,` `last``)`.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer anderen Sequenz erstellen.  
  
 Der Konstruktor:  
  
 `list(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 initialisiert die gesteuerte Sequenz mit der Folge, die der Enumerator `right` festgelegt wird.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer anderen Sequenz erstellen, die von ein Enumerator beschrieben wird.  
  
## Beispiel  
  
```  
// cliext_list_construct.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
// construct an empty container   
    cliext::list<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::list<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::list<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::list<wchar_t>::iterator it = c3.end();   
    cliext::list<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::list<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::list<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::list<wchar_t> c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **0 0 0**  
 **x x x x x x**  
 **x x x x x**  
 **x x x x x x**  
 **x x x x x x**  
 **x x x x x x**   
## Anforderungen  
 **Header:** \<cliext\/Liste\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [list](../dotnet/list-stl-clr.md)   
 [list::assign](../dotnet/list-assign-stl-clr.md)   
 [list::generic\_container](../dotnet/list-generic-container-stl-clr.md)   
 [list::operator\=](../dotnet/list-operator-assign-stl-clr.md)