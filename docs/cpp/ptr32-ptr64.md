---
title: __ptr32, __ptr64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
- __ptr32
- __ptr64
dev_langs:
- C++
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: d722f8403efbe1172fefbe8a792c95d4063e893f
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="ptr32-ptr64"></a>__ptr32, __ptr64
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 `__ptr32` stellt einen systemeigenen Zeiger auf einem 32-Bit-System dar, während `__ptr64` einen systemeigenen Zeiger auf einem 64-Bit-System darstellt.  
  
 Das folgende Beispiel zeigt, wie die einzelnen Zeigertypen deklariert werden:  
  
```  
int * __ptr32 p32;  
int * __ptr64 p64;  
```  
  
 Bei einem 32-Bit-System wird ein Zeiger, der mit `__ptr64` deklariert wird, auf einen 32-Bit-Zeiger gekürzt. Bei einem 64-Bit-System wird ein Zeiger, der mit `__ptr32` deklariert wird, in einen 64-Bit-Zeiger umgewandelt.  
  
> [!NOTE]
>  Sie können keine `__ptr32` oder `__ptr64` beim Kompilieren mit **/CLR: pure**. Andernfalls wird `Compiler Error C2472` generiert. Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
## <a name="example"></a>Beispiel  
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
  
```Output  
32  
64  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlegende Typen](../cpp/fundamental-types-cpp.md)
