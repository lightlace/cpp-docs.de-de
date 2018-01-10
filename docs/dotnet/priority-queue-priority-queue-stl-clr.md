---
title: 'priority_queue:: priority_queue (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::priority_queue::priority_queue
dev_langs: C++
helpviewer_keywords: priority_queue member [STL/CLR]
ms.assetid: aab423d7-959e-48fd-9028-e9f45f43cb8a
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 03d0054f3c755c3dd6e4bd653c972a0f7aa6735d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="priorityqueuepriorityqueue-stlclr"></a>priority_queue::priority_queue (STL/CLR)
Erstellt ein Container-Adapter-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 Fortsetzung  
 Der zu kopierende Container.  
  
 first  
 Anfang des Bereichs, der eingefügt.  
  
 last  
 Das Ende des Bereichs einfügen.  
  
 pred  
 Sortierung Prädikat für die gesteuerte Sequenz.  
  
 Rechts  
 Einzufügendes Objekt bzw. einzufügender Bereich.  
  
## <a name="remarks"></a>Hinweise  
 Der Konstruktor:  
  
 `priority_queue();`  
  
 erstellt einen leeren umschlossenen Container mit der standardmäßigen Reihenfolge Prädikat. Sie können damit eine leere gesteuerte Sequenz, mit der standardmäßigen Reihenfolge Prädikat angeben.  
  
 Der Konstruktor:  
  
 `priority_queue(priority_queue<Value, Container>% right);`  
  
 erstellt einen umschlossenen Container, der eine Kopie des `right.get_container()`, mit dem Prädikat Reihenfolge `right.value_comp()`. Verwenden sie eine gesteuerte Sequenz an, die eine Kopie der Sequenz, die durch das Warteschlangenobjekt gesteuert wird `right`, mit der gleichen Reihenfolge Prädikat.  
  
 Der Konstruktor:  
  
 `priority_queue(priority_queue<Value, Container>^ right);`  
  
 erstellt einen umschlossenen Container, der eine Kopie des `right->get_container()`, mit dem Prädikat Reihenfolge `right->value_comp()`. Verwenden sie eine gesteuerte Sequenz an, die eine Kopie der Sequenz, die durch das Warteschlangenobjekt gesteuert wird `*right`, mit der gleichen Reihenfolge Prädikat.  
  
 Der Konstruktor:  
  
 `explicit priority_queue(value_compare^ pred);`  
  
 erstellt einen leeren umschlossenen Container mit dem Prädikat Reihenfolge `pred`. Sie können damit eine leere gesteuerte Sequenz, mit der angegebenen Reihenfolge Prädikat angeben.  
  
 Der Konstruktor:  
  
 `priority_queue(value_compare^ pred, container_type cont);`  
  
 erstellt einen leeren umschlossenen Container mit dem Prädikat Reihenfolge `pred`, stellt dann alle Elemente der `cont` können sie eine gesteuerte Sequenz aus einem vorhandenen Container mit der angegebenen Reihenfolge Prädikat angeben.  
  
 Der Konstruktor:  
  
 `template<typename InIt> priority_queue(InIt first, InIt last);`  
  
 erstellt einen leeren umschlossenen Container mit der Sortierung standardprädikat, dann wird die Sequenz [`first`, `last`). Sie können damit eine gesteuerte Sequenz aus einem angegebenen Eqeuence mit der angegebenen Reihenfolge Prädikat angeben.  
  
 Der Konstruktor:  
  
 `template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred);`  
  
 erstellt einen leeren umschlossenen Container mit dem Prädikat Reihenfolge `pred`, dann wird die Sequenz [`first`, `last`). Sie können damit eine gesteuerte Sequenz aus einem angegebenen Seqeuence mit der angegebenen Reihenfolge Prädikat angeben.  
  
 Der Konstruktor:  
  
 `template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred, container_type% cont);`  
  
 erstellt einen leeren umschlossenen Container mit dem Prädikat Reihenfolge `pred`, stellt dann alle Elemente der `cont` sowie die Sequenz [`first`, `last`). Sie können damit eine gesteuerte Sequenz aus einem vorhandenen Container und eine angegebene Seqeuence mit der angegebenen Reihenfolge Prädikat angeben.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
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
  
```Output  
size() = 0  
 c a b  
size() = 0  
 a c b  
 a c b  
 c a b  
 a c b  
 a a b c c b  
 c a b  
 c a b  
 a c b  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext bzw. einer neuen Warteschlange >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue:: Assign (STL/CLR)](../dotnet/priority-queue-assign-stl-clr.md)   
 [priority_queue::generic_container (STL/CLR)](../dotnet/priority-queue-generic-container-stl-clr.md)   
 [priority_queue::operator= (STL/CLR)](../dotnet/priority-queue-operator-assign-stl-clr.md)