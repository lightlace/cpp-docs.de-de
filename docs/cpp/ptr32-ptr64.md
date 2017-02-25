---
title: "__ptr32, __ptr64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__ptr32_cpp"
  - "__ptr64_cpp"
  - "__ptr32"
  - "__ptr64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__ptr32-Schlüsselwort [C++]"
  - "__ptr64-Schlüsselwort [C++]"
  - "_ptr32-Schlüsselwort [C++]"
  - "_ptr64-Schlüsselwort [C++]"
  - "ptr32-Schlüsselwort [C++]"
  - "ptr64-Schlüsselwort [C++]"
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# __ptr32, __ptr64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 `__ptr32` stellt einen systemeigenen Zeiger auf einem 32\-Bit\-System dar, während `__ptr64` einen systemeigenen Zeiger auf einem 64\-Bit\-System darstellt.  
  
 Das folgende Beispiel zeigt, wie die einzelnen Zeigertypen deklariert werden:  
  
```  
int * __ptr32 p32;  
int * __ptr64 p64;  
```  
  
 Bei einem 32\-Bit\-System wird ein Zeiger, der mit `__ptr64` deklariert wird, auf einen 32\-Bit\-Zeiger gekürzt.  Bei einem 64\-Bit\-System wird ein Zeiger, der mit `__ptr32` deklariert wird, in einen 64\-Bit\-Zeiger umgewandelt.  
  
> [!NOTE]
>  Sie können weder `__ptr32` noch `__ptr64` beim Kompilieren mit **\/clr:pure** verwenden.  Andernfalls wird `Compiler Error C2472` generiert.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie Zeiger mit den Schlüsselwörtern `__ptr32` und `__ptr64` deklariert und zugewiesen werden.  
  
```  
#include <cstdlib>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    int * __ptr32 p32;  
    int * __ptr64 p64;  
  
    p32 = (int * __ptr32)malloc(4);  
    *p32 = 32;  
    cout << *p32 << endl;  
  
    p64 = (int * __ptr64)malloc(4);  
    *p64 = 64;  
    cout << *p64 << endl;  
}  
```  
  
  **32**  
**64**   
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Grundlegende Typen](../cpp/fundamental-types-cpp.md)