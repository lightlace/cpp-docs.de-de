---
title: "priority_queue::priority_queue (STL/CLR)"
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
  - "cliext::priority_queue::priority_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "priority_queue-Member [STL/CLR]"
ms.assetid: aab423d7-959e-48fd-9028-e9f45f43cb8a
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# priority_queue::priority_queue (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein Containeradapterobjekt.  
  
## Syntax  
  
```  
priority_queue();  
priority_queue(priority_queue<Value, Container> right);  
priority_queue(priority_queue<Value, Container> right);  
explicit priority_queue(value_compare^ pred);  
priority_queue(value_compare^ pred, container_type% cont);  
template<typename InIt>  
    priority_queue(InIt first, InIt last);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred, container_type% cont);  
```  
  
#### Parameter  
 fort.  
 Container zu kopieren.  
  
 first  
 Anfang Einfügen des Bereichs.  
  
 last  
 Ende Einfügen des Bereichs.  
  
 pred  
 Reihenfolgenprädikat für die gesteuerte Sequenz.  
  
 right  
 Objekt oder Bereich Einfüge\-.  
  
## Hinweise  
 Der Konstruktor:  
  
 `priority_queue();`  
  
 stellt einen leeren umschlossenen Container, mit dem Standardreihenfolgenprädikat erstellt.  Sie verwenden sie, um eine leere gesteuerten ursprünglichen Sequenz, mit dem Standardreihenfolgenprädikat anzugeben.  
  
 Der Konstruktor:  
  
 `priority_queue(priority_queue<Value, Container>% right);`  
  
 stellt einen Container zeichnen, die eine Kopie von `right.get_container()`, mit dem Reihenfolgenprädikat `right.value_comp()`.  Sie verwenden sie, um einer gesteuerten ursprünglichen Sequenz, die eine Kopie der Sequenz, die erfolgen durch das Objekt `right` gesteuert wird, mit dem gleichen Reihenfolgenprädikat anzugeben.  
  
 Der Konstruktor:  
  
 `priority_queue(priority_queue<Value, Container>^ right);`  
  
 stellt einen Container zeichnen, die eine Kopie von `right->get_container()`, mit dem Reihenfolgenprädikat `right->value_comp()`.  Sie verwenden sie, um einer gesteuerten ursprünglichen Sequenz, die eine Kopie der Sequenz, die erfolgen durch das Objekt `*right` gesteuert wird, mit dem gleichen Reihenfolgenprädikat anzugeben.  
  
 Der Konstruktor:  
  
 `explicit priority_queue(value_compare^ pred);`  
  
 stellt einen leeren umschlossenen Container, mit dem Reihenfolgenprädikat `pred`.  Sie verwenden sie, um eine leere gesteuerten ursprünglichen Sequenz, mit dem angegebenen Reihenfolgenprädikat anzugeben.  
  
 Der Konstruktor:  
  
 `priority_queue(value_compare^ pred, container_type cont);`  
  
 stellt einen leeren umschlossenen Container, mit dem Reihenfolgenprädikat `pred` erstellt, dann gibt alle Elemente von `cont`, die Sie es verwenden, um einer gesteuerten ursprünglichen Sequenz aus einem vorhandenen Container anzugeben, mit dem angegebenen Reihenfolgenprädikat.  
  
 Der Konstruktor:  
  
 `template<typename InIt>`  
  
 `priority_queue(InIt first, InIt last);`  
  
 stellt einen leeren umschlossenen Container, mit dem Standardreihenfolgenprädikat erstellt, dann drückt die Sequenz `[``first``,` `last``)`.  Sie verwenden sie, um einer gesteuerten ursprünglichen Sequenz aus einem angegebenen eqeuence, mit dem angegebenen Reihenfolgenprädikat anzugeben.  
  
 Der Konstruktor:  
  
 `template<typename InIt>`  
  
 `priority_queue(InIt first, InIt last,`  
  
 `value_compare^ pred);`  
  
 stellt einen leeren umschlossenen Container, mit dem Reihenfolgenprädikat `pred` erstellt, dann drückt die Sequenz `[``first``,` `last``)`.  Sie verwenden sie, um einer gesteuerten ursprünglichen Sequenz aus einem angegebenen seqeuence, mit dem angegebenen Reihenfolgenprädikat anzugeben.  
  
 Der Konstruktor:  
  
 `template<typename InIt>`  
  
 `priority_queue(InIt first, InIt last,`  
  
 `value_compare^ pred, container_type% cont);`  
  
 stellt einen leeren umschlossenen Container, mit dem Reihenfolgenprädikat `pred` erstellt, dann gibt alle Elemente von `cont` sowie die Sequenz `[``first``,` `last``)`.  Sie verwenden sie, um einer gesteuerten ursprünglichen Sequenz aus einem vorhandenen Container und einem angegebenen seqeuence, mit dem angegebenen Reihenfolgenprädikat anzugeben.  
  
## Beispiel  
  
```  
// cliext_priority_queue_construct.cpp   
// compile with: /clr   
#include <cliext/queue>   
#include <cliext/deque>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
typedef cliext::deque<wchar_t> Mydeque;   
int main()   
    {   
// construct an empty container   
    Mypriority_queue c1;   
    Mypriority_queue::container_type^ wc1 = c1.get_container();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mypriority_queue c2 = cliext::greater<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    for each (wchar_t elem in wc1)   
        c2.push(elem);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule by copying an underlying container   
    Mypriority_queue c2x =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
   for each (wchar_t elem in c2x.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mypriority_queue c3(wc1->begin(), wc1->end());   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mypriority_queue c4(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>());   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range, another container, and an ordering rule   
    Mypriority_queue c5(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c5.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Mypriority_queue c6(c3);   
    for each (wchar_t elem in c6.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mypriority_queue c7(%c3);   
    for each (wchar_t elem in c7.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule, by copying an underlying container   
    Mypriority_queue c8 =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c8.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **c ein b**  
**size\(\) \= 0**  
 **a\-c b**  
 **a\-c b**  
 **c ein b**  
 **a\-c b**  
 **ein b c c b**  
 **c ein b**  
 **c ein b**  
 **a\-c b**   
## Anforderungen  
 **Header:** \<cliext\/Warteschlange\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [priority\_queue::assign](../dotnet/priority-queue-assign-stl-clr.md)   
 [priority\_queue::generic\_container](../dotnet/priority-queue-generic-container-stl-clr.md)   
 [priority\_queue::operator\=](../dotnet/priority-queue-operator-assign-stl-clr.md)