---
title: "vector::erase (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector::erase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erase-Member [STL/CLR]"
ms.assetid: 624905eb-83c0-499b-a07a-c10aebd7acc3
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# vector::erase (STL/CLR)
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
  
 Beide Memberfunktionen geben ein Iterator, der das erste Element festgelegt, das über allen Elementen entfernt hinaus bleibt, oder [vector::end](../dotnet/vector-end-stl-clr.md)`()` zurück, wenn kein solches Element vorhanden ist.  
  
 Wenn diese Elemente gelöscht, ist die Anzahl der Elementkopien in der Anzahl von Elementen zwischen dem Ende Lösch\- und dem näheren Ende der Sequenz linear. \(Wenn Sie eine oder mehrere Elemente an jedem Ende der Sequenz löschen, treten keine Elementkopien.\)  
  
## Beispiel  
  
```  
// cliext_vector_erase.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
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
    cliext::vector<wchar_t>::iterator it = c1.end();   
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
 **Header:** \<cliext\/Vektor\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [Vektor](../dotnet/vector-stl-clr.md)   
 [vector::clear](../dotnet/vector-clear-stl-clr.md)