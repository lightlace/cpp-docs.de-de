---
title: "vector::vector (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector::vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vector-Melber [STL/CLR]"
ms.assetid: a0b5e807-1ef2-422b-b772-1f96cd62fb51
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# vector::vector (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein container\-Objekt.  
  
## Syntax  
  
```  
vector();  
vector(vector<Value>% right);  
vector(vector<Value>^ right);  
explicit vector(size_type count);  
vector(size_type count, value_type val);  
template<typename InIt>  
    vector(InIt first, InIt last);  
vector(System::Collections::Generic::IEnumerable<Value>^ right);  
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
  
 `vector();`  
  
 initialisiert die gesteuerte Sequenz ohne Elemente.  Sie verwenden sie, um eine leere ursprünglichen gesteuerten Sequenz angeben.  
  
 Der Konstruktor:  
  
 `vector(vector<Value>% right);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``right``.`[vector::begin](../dotnet/vector-begin-stl-clr.md)`(),` `right``.`[vector::end](../dotnet/vector-end-stl-clr.md)`())`.  Sie verwenden sie, um einer gesteuerten ursprünglichen Sequenz angeben, die eine Kopie dieser Folge ist, die vom Vektorobjekt `right` gesteuert wird.  
  
 Der Konstruktor:  
  
 `vector(vector<Value>^ right);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``right``->`[vector::begin](../dotnet/vector-begin-stl-clr.md)`(),` `right``->`[vector::end](../dotnet/vector-end-stl-clr.md)`())`.  Sie verwenden sie, um einer gesteuerten ursprünglichen Sequenz angeben, die eine Kopie dieser Folge ist, die vom Vektorobjekt gesteuert wird, dessen Handle `right` ist.  
  
 Der Konstruktor:  
  
 `explicit vector(size_type count);`  
  
 initialisiert die gesteuerte Sequenz mit `count`\-Elemente jede mit Wert `value_type()`.  Sie verwenden ihn, um den Container mit allen Elementen füllen, der den Standardwert aufweist.  
  
 Der Konstruktor:  
  
 `vector(size_type count, value_type val);`  
  
 initialisiert die gesteuerte Sequenz mit `count`\-Elemente jede mit Wert `val`.  Sie verwenden sie, um den Container mit allen Elementen füllen, der denselben Wert verfügt.  
  
 Der Konstruktor:  
  
 `template<typename InIt>`  
  
 `vector(InIt first, InIt last);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``first``,` `last``)`.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer anderen Sequenz erstellen.  
  
 Der Konstruktor:  
  
 `vector(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 initialisiert die gesteuerte Sequenz mit der Folge, die der Enumerator `right` festgelegt wird.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer anderen Sequenz erstellen, die von ein Enumerator beschrieben wird.  
  
## Beispiel  
  
```  
// cliext_vector_construct.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
// construct an empty container   
    cliext::vector<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::vector<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::vector<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::vector<wchar_t>::iterator it = c3.end();   
    cliext::vector<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::vector<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::vector<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::vector<wchar_t> c8(%c3);   
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
 **Header:** \<cliext\/Vektor\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [Vektor](../dotnet/vector-stl-clr.md)   
 [vector::assign](../dotnet/vector-assign-stl-clr.md)   
 [vector::generic\_container](../dotnet/vector-generic-container-stl-clr.md)   
 [vector::operator\=](../dotnet/vector-operator-assign-stl-clr.md)