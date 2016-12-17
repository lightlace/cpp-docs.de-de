---
title: "list::erase (STL/CLR)"
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
  - "cliext::list::erase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erase-Member [STL/CLR]"
ms.assetid: 78705058-1e83-441d-b267-d4fb56451c0b
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# list::erase (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Entfernt Elemente an den angegebenen Positionen.  
  
## Syntax  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### Parameter  
 first  
 Anfang zu löschen des Bereichs.  
  
 last  
 Ende zu löschen des Bereichs.  
  
 deinen  
 So löschen Element.  
  
## Hinweise  
 Die erste Memberfunktion gesteuerten entfernt das Element der Sequenz, die von `where` angezeigt wird.  Sie verwenden sie, um ein einzelnes Element zu entfernen.  
  
 Die zweite Memberfunktion entfernt die Elemente der gesteuerten Sequenz im Bereich `[``first``,` `last``)`.  Sie verwenden sie, dass Nullen oder zu entfernen zusammenhängendere Elemente.  
  
 Beide Memberfunktionen geben ein Iterator, der das erste Element festgelegt, das über allen Elementen entfernt hinaus bleibt, oder [list::end](../dotnet/list-end-stl-clr.md)`()` zurück, wenn kein solches Element vorhanden ist.  
  
 Wenn diese Elemente gelöscht, ist die Anzahl der Elementkopien in der Anzahl von Elementen zwischen dem Ende Lösch\- und dem näheren Ende der Sequenz linear. \(Wenn Sie eine oder mehrere Elemente an jedem Ende der Sequenz löschen, treten keine Elementkopien.\)  
  
## Beispiel  
  
```  
// cliext_list_erase.cpp   
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
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.push_back(L'd');   
    c1.push_back(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    cliext::list<wchar_t>::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
  **ein b c**  
**erase\(begin\(\)\) \= b**  
 **c b d e**  
**erase\(begin\(\), end\(\)\-1\) \= e**  
**size\(\) \= 1**   
## Anforderungen  
 **Header:** \<cliext\/Liste\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [list](../dotnet/list-stl-clr.md)   
 [list::clear](../dotnet/list-clear-stl-clr.md)