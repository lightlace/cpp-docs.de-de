---
title: "make_pair (STL/CLR)"
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
  - "cliext::make_pair"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_pair-Funktion [STL/CLR]"
ms.assetid: 74733f2c-97b0-4d69-b431-5ab8f0de9e3e
caps.latest.revision: 8
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# make_pair (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Führen Sie `pair` von einem Paar Werten.  
  
## Syntax  
  
```  
template<typename Value1,  
    typename Value2>  
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);  
```  
  
#### Parameter  
 Value1  
 Der Typ des zuerst umschlossenen Werts.  
  
 Value2  
 Der Typ des zweiten umschlossenen Werts.  
  
 first  
 Erster Wert einzubindende.  
  
 second  
 Zweite Wert einzubindende.  
  
## Hinweise  
 Die Vorlagenfunktion gibt `pair<``Value1``,` `Value2``>(``first``,` `second``)` zurück.  Sie verwenden sie, um ein Objekt `pair``<``Value1``,` `Value2``>` von einem Paar Werten zu erstellen.  
  
## Beispiel  
  
```  
// cliext_make_pair.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    c1 = cliext::make_pair(L'y', 4);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    return (0);   
    }  
  
```  
  
  **\[x, 3\]**  
**\[y, 4\]**   
## Anforderungen  
 **Header:** \<cliext\/Hilfsprogramm\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [range\_adapter](../dotnet/range-adapter-stl-clr.md)