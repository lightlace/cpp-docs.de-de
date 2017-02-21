---
title: "__func__ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__func__"
  - "__func___cpp"
dev_langs: 
  - "C++"
ms.assetid: a5299b8d-f0ee-4af2-91dd-8fb165e68798
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# __func__
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\(C\+\+11\)** Der vordefinierte Bezeichner "\_\_func\_\_" ist implizit als Zeichenfolge definiert, die den unqualifizierten und nicht erweiterten Namen der einschließenden Funktion enthält.  \_\_func\_\_  wird vom C\+\+\-Standard vorgegeben und ist keine Microsoft\-Erweiterung.  
  
## Syntax  
  
```vb  
__func__  
```  
  
## Rückgabewert  
 Gibt ein Null\-terminiertes Konstantenzeichenarray mit Zeichen zurück, das den Funktionsnamen enthält.  
  
## Beispiel  
  
```  
  
#include <string>  
#include <iostream>  
  
namespace Test  
{  
    struct Foo  
    {  
        static void DoSomething(int i, std::string s)  
        {  
           std::cout << __func__ << std::endl; // Output: DoSomething  
        }  
    };  
}  
int main()  
{  
    Test::Foo::DoSomething(42, "Hello");  
  
    return 0;  
}  
  
```  
  
## Anforderungen  
 C\+\+11