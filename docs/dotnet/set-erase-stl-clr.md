---
title: "set::erase (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set::erase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erase-Member [STL/CLR]"
ms.assetid: 0596514b-d4cd-4d2d-8223-3bee6980261c
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# set::erase (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Entfernt Elemente an den angegebenen Positionen.  
  
## Syntax  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
size_type erase(key_type key)  
```  
  
#### Parameter  
 first  
 Anfang zu löschen des Bereichs.  
  
 Schlüssel  
 So löschen Schlüsselwert.  
  
 last  
 Ende zu löschen des Bereichs.  
  
 deinen  
 So löschen Element.  
  
## Hinweise  
 Die erste Memberfunktion gesteuerten entfernt das Element der Sequenz, die von `where` dargestellte und gibt ein Iterator, der das erste Element zurück festgelegt wird, das über dem entfernten Element hinaus bleibt, oder [set::end](../dotnet/set-end-stl-clr.md)`()`, wenn kein solches Element vorhanden ist.  Sie verwenden sie, um ein einzelnes Element zu entfernen.  
  
 Die zweite Memberfunktion entfernt die Elemente der gesteuerten Sequenz im Bereich `[``first``,` `last``)` und gibt ein Iterator, der das erste Element festgelegt, das über allen Elementen entfernt hinaus bleibt, oder `end()` zurück, wenn kein solches Element vorhanden ist.  Sie verwenden sie, dass Nullen oder zu entfernen zusammenhängendere Elemente.  
  
 Die dritte Memberfunktion entfernt jedes Element der Sequenz, deren Schlüssel gesteuerten entsprechenden Reihenfolge zu `key`, und gibt die Anzahl die Anzahl der entfernten Elemente zurück.  Sie verwenden sie, um alle Elemente zu entfernen und zu erfassen, die einen angegebenen Schlüssel übereinstimmen.  
  
 Jede Elementlöschung akzeptiert die Uhrzeit, die dem Logarithmus der Anzahl der Elemente in der Sequenz gesteuerten proportional ist.  
  
## Beispiel  
  
```  
// cliext_set_erase.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.insert(L'd');   
    c1.insert(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    Myset::iterator it = c1.end();   
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
 **Header:** \<cliext\/Satz\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [set](../dotnet/set-stl-clr.md)   
 [set::clear](../dotnet/set-clear-stl-clr.md)