---
title: Compilerwarnung (Stufe 4) C4701 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4701
dev_langs:
- C++
helpviewer_keywords:
- C4701
ms.assetid: d7c76c66-1f3f-4d3c-abe4-5d94c84a5a1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c48df2f4ac3d5aad4ae82abf76dab4d96e8af89a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4701"></a>Compilerwarnung (Stufe 4) C4701
möglicherweise nicht initialisierten lokalen Variablen 'Name' verwendet  
  
 Die lokale Variable *Namen* kann verwendet werden können, ohne einen Wert zugewiesen wird. Dies kann zu unvorhersehbaren Ergebnissen führen.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code generiert C4701 und C4703.  
  
```cpp  
#include <malloc.h>  
  
void func(int size)  
{  
    void* p;  
    if (size < 256) {  
        p = malloc(size);  
    }  
  
    if (p != nullptr) // C4701 and C4703  
        free(p);  
}  
  
void main()  
{  
    func(9);  
}  
```  
  
```Output  
c:\src\test.cpp(10) : warning C4701: potentially uninitialized local variable 'p' used  
c:\src\test.cpp(10) : warning C4703: potentially uninitialized local pointer variable 'p' used  
  
```  
  
 Um diese Warnung zu beheben, initialisieren Sie die Variable, wie im folgenden Beispiel gezeigt:  
  
```cpp  
#include <malloc.h>  
  
void func(int size)  
{  
    void* p = nullptr;  
    if (size < 256) {  
        p = malloc(size);  
    }  
  
    if (p != nullptr)  
        free(p);  
}  
  
void main()  
{  
    func(9);  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Compilerwarnung (Stufe 4) C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)   
 [Warnungen, / SDL und Verbessern der Erkennung von nicht initialisierten Variablen](http://blogs.msdn.com/b/sdl/archive/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection.aspx)