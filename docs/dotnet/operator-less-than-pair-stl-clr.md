---
title: "operator&lt; (pair) (STL/CLR)"
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
  - "cliext::pair::operator<"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator<-Member [STL/CLR]"
ms.assetid: e7061b29-1289-4ea9-ae69-feea8abbfb25
caps.latest.revision: 8
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# operator&lt; (pair) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Paarkleiner\-als\-vergleich.  
  
## Syntax  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator<(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### Parameter  
 left  
 Linkspaare zu vergleichen.  
  
 right  
 Rechte Paare zu vergleichen.  
  
## Hinweise  
 Die Operatorfunktion gibt `left``.first <` `right``.first || !(``right``.first <` `left``.first &&` `left``.second <` `right``.second` zurück.  Sie verwenden sie, um zu testen, ob `left` bestellte vor `right` hat, wenn die zwei Paare verglichenes Element durch Element sind.  
  
## Beispiel  
  
```  
// cliext_pair_operator_lt.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] < [x 3] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[x 3] < [x 4] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
  **\[x, 3\]**  
**\[x, 4\]**  
**x \[3\] \< \[x 3\] ist falsch**  
**x \[3\] \< \[x 4\] gilt**   
## Anforderungen  
 **Header:** \<cliext\/Hilfsprogramm\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [pair](../dotnet/pair-stl-clr.md)   
 [operator\=\= \(pair\)](../dotnet/operator-equality-pair-stl-clr.md)   
 [operator\!\= \(pair\)](../dotnet/operator-inequality-pair-stl-clr.md)   
 [operator\>\= \(pair\)](../dotnet/operator-greater-or-equal-pair-stl-clr.md)   
 [operator\> \(pair\)](../dotnet/operator-greater-than-pair-stl-clr.md)   
 [operator\<\= \(pair\)](../dotnet/operator-less-or-equal-pair-stl-clr.md)