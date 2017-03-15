---
title: "hash_multimap::erase (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multimap::erase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erase-Member [STL/CLR]"
ms.assetid: 663c67f6-8070-47db-abdc-58f7ace69736
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# hash_multimap::erase (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Entfernt Elemente an den angegebenen Positionen.  
  
## Syntax  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
bool erase(key_type key)  
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
 Die erste Memberfunktion gesteuerten entfernt das Element der Sequenz, die von `where` dargestellte und gibt ein Iterator, der das erste Element zurück festgelegt wird, das über dem entfernten Element hinaus bleibt, oder [hash\_multimap::end](../dotnet/hash-multimap-end-stl-clr.md)`()`, wenn kein solches Element vorhanden ist.  Sie verwenden sie, um ein einzelnes Element zu entfernen.  
  
 Die zweite Memberfunktion entfernt die Elemente der gesteuerten Sequenz im Bereich `[``first``,` `last``)` und gibt ein Iterator, der das erste Element festgelegt, das über allen Elementen entfernt hinaus bleibt, oder `end()` zurück, wenn kein solches Element vorhanden ist.  Sie verwenden sie, dass Nullen oder zu entfernen zusammenhängendere Elemente.  
  
 Die dritte Memberfunktion entfernt jedes Element der Sequenz, deren Schlüssel gesteuerten entsprechenden Reihenfolge zu `key`, und gibt die Anzahl die Anzahl der entfernten Elemente zurück.  Sie verwenden sie, um alle Elemente zu entfernen und zu erfassen, die einen angegebenen Schlüssel übereinstimmen.  
  
 Jede Elementlöschung akzeptiert die Uhrzeit, die dem Logarithmus der Anzahl der Elemente in der Sequenz gesteuerten proportional ist.  
  
## Beispiel  
  
```  
// cliext_hash_multimap_erase.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    cliext::hash_multimap<wchar_t, int> c1;   
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'a', 1));   
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'b', 2));   
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (cliext::hash_multimap<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    cliext::hash_multimap<wchar_t, int>::iterator it =   
        c1.erase(c1.begin());   
    System::Console::WriteLine("erase(begin()) = [{0} {1}]",   
        it->first, it->second);   
  
// add elements and display " b c d e"   
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'd', 4));   
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'e', 5));   
    for each (cliext::hash_multimap<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase all but end   
    it = c1.end();   
    it = c1.erase(c1.begin(), --it);   
    System::Console::WriteLine("erase(begin(), end()-1) = [{0} {1}]",   
        it->first, it->second);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// erase end   
    System::Console::WriteLine("erase(L'x') = {0}", c1.erase(L'x'));   
    System::Console::WriteLine("erase(L'e') = {0}", c1.erase(L'e'));   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[bc 3\]**  
**erase\(begin\(\)\) \= \[b 2\]**  
 **\[b c 2\] \[3\] \[d\] \[4e 5\]**  
**erase\(begin\(\), end\(\)\-1\) \= \[e 5\]**  
**size\(\) \= 1**  
**\(Löschen L'x\) \= 0**  
**\(Löschen L'e\) \= 1**   
## Anforderungen  
 **Header:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multimap::clear](../dotnet/hash-multimap-clear-stl-clr.md)