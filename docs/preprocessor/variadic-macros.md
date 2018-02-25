---
title: Variadic-Makros | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- variadic macros [C++]
- __VA_ARGS__ variadic macro specifier
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a0e3832ab334d31b50edbe0cc1fd5dccbffb61bf
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="variadic-macros"></a>Variadic-Makros
Variadic-Makros sind funktionsähnliche Makros, die eine variable Anzahl von Argumenten enthalten.  
  
## <a name="remarks"></a>Hinweise  
 Um Variadic-Makros verwenden, kann mit der Auslassungspunkten als das letzte formale Argument in einer Makrodefinition stehen, und die Austausch-ID angegeben werden `__VA_ARGS__` dürfen in der Definition verwendet werden, um die zusätzlichen Argumente einzufügen.  `__VA_ARGS__` wird von allen Argumenten ersetzt, die mit den Auslassungspunkten, einschließlich der Trennzeichen dazwischen entsprechen.  
  
 Der C-Standard gibt an, dass mindestens ein Argument an die Auslassungszeichen übergeben werden muss, um sicherzustellen, dass das Makro sich nicht in einen Ausdruck mit einem nachfolgenden Komma auflöst.  Die Implementierung von Visual C++ unterdrückt ein nachfolgendes Komma, wenn keine Argumente an die Auslassungszeichen übergeben werden.  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="output"></a>Ausgabe  
  
```  
here are some varargs1(1)  
here are some varargs2(4)  
here are some varargs3(5)  
hello, world  
error  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Makros (C/C++)](../preprocessor/macros-c-cpp.md)