---
title: "hash_set::upper_bound (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::upper_bound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "upper_bound-Member [STL/CLR]"
ms.assetid: dc8815f1-8b45-4f3d-a51f-54050d434d8f
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# hash_set::upper_bound (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Suchenende des Bereichs, der einen angegebenen Schlüssel entspricht.  
  
## Syntax  
  
```  
iterator upper_bound(key_type key);  
```  
  
#### Parameter  
 Schlüssel  
 Für zu suchen Schlüsselwert.  
  
## Hinweise  
 Die Memberfunktion bestimmt das letzte Element in der Sequenz `X` gesteuerten, die denselben Bucket wie `key` wendet und entsprechenden Reihenfolge zu `key`.  Wenn kein solches Element vorhanden ist oder wenn `X` das letzte Element der gesteuerten Sequenz ist, gibt sie `()` zurück; [hash\_set::end](../dotnet/hash-set-end-stl-clr.md) Andernfalls gibt sie ein Iterator zurück, der das erste Element darüber hinaus `X` festlegt.  Sie verwenden sie, um das Ende einer Sequenz der Elemente in der Sequenz gesteuerten einfach zu finden, das einen angegebenen Schlüssel übereinstimmen.  
  
## Beispiel  
  
```  
// cliext_hash_set_upper_bound.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",   
        c1.upper_bound(L'x') == c1.end());   
  
    System::Console::WriteLine("*upper_bound(L'a') = {0}",   
        *c1.upper_bound(L'a'));   
    System::Console::WriteLine("*upper_bound(L'b') = {0}",   
        *c1.upper_bound(L'b'));   
    return (0);   
    }  
  
```  
  
  **ein b c**  
**upper\_bound\(L'x'\)\=\=end\(\) \= True**  
**\*upper\_bound \(L'a b\) \=**  
**\*upper\_bound \(L'b\) \= c**   
## Anforderungen  
 **Header:** \<cliext\/hash\_set\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::count](../dotnet/hash-set-count-stl-clr.md)   
 [hash\_set::equal\_range](../dotnet/hash-set-equal-range-stl-clr.md)   
 [hash\_set::find](../dotnet/hash-set-find-stl-clr.md)   
 [hash\_set::lower\_bound](../dotnet/hash-set-lower-bound-stl-clr.md)