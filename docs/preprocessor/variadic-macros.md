---
title: "Variadic-Makros | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "variadic-Makros [C++]"
  - "__VA_ARGS__ variadic-Makrospezifizierer"
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Variadic-Makros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Variadic\-Makros sind funktionsähnliche Makros, die eine variable Anzahl von Argumenten enthalten.  
  
## Hinweise  
 Um variadic\-Makros zu verwenden, können die Auslassungszeichen als endgültiges formales Argument in einer Makrodefinition angegeben werden, und mit dem Ersetzungsbezeichner `__VA_ARGS__` können Sie in der Definition die zusätzlichen Argumente einfügen. `__VA_ARGS__` wird von allen Argumenten, die mit den Auslassungszeichen übereinstimmen, einschließlich Kommas zwischen ihnen, ersetzt.  
  
 Der C\-Standard gibt an, dass mindestens ein Argument an die Auslassungszeichen übergeben werden muss, um sicherzustellen, dass das Makro sich nicht in einen Ausdruck mit einem nachfolgenden Komma auflöst.  Die Implementierung von Visual C\+\+ unterdrückt ein nachfolgendes Komma, wenn keine Argumente an die Auslassungszeichen übergeben werden.  
  
## Beispiel  
  
```cpp  
// variadic_macros.cpp  
#include <stdio.h>  
#define EMPTY  
  
#define CHECK1(x, ...) if (!(x)) { printf(__VA_ARGS__); }  
#define CHECK2(x, ...) if ((x)) { printf(__VA_ARGS__); }  
#define CHECK3(...) { printf(__VA_ARGS__); }  
#define MACRO(s, ...) printf(s, __VA_ARGS__)  
  
int main() {  
    CHECK1(0, "here %s %s %s", "are", "some", "varargs1(1)\n");  
    CHECK1(1, "here %s %s %s", "are", "some", "varargs1(2)\n");   // won't print  
  
    CHECK2(0, "here %s %s %s", "are", "some", "varargs2(3)\n");   // won't print  
    CHECK2(1, "here %s %s %s", "are", "some", "varargs2(4)\n");  
  
    // always invokes printf in the macro  
    CHECK3("here %s %s %s", "are", "some", "varargs3(5)\n");  
  
    MACRO("hello, world\n");  
  
    MACRO("error\n", EMPTY); // would cause error C2059, except VC++   
                             // suppresses the trailing comma  
}  
```  
  
## Output  
  
```  
here are some varargs1(1)  
here are some varargs2(4)  
here are some varargs3(5)  
hello, world  
error  
  
```  
  
## Siehe auch  
 [Makros](../preprocessor/macros-c-cpp.md)