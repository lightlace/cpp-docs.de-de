---
title: Compiler (Stufe 1) C4750 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4750
dev_langs:
- C++
helpviewer_keywords:
- C4750
ms.assetid: b0b2c938-7d2a-4c36-8270-7daee15ffee3
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 84f0628de933344eb23dc6325679abdcd3699c3a
ms.openlocfilehash: 6e22ef89b92a5b584979abbd370f82b482cf74e0
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4750"></a>Compilerwarnung (Stufe 1) C4750
'Bezeichner': Funktion mit „_alloca()“ „inline“ in einer Schleife  
  
 Die "Bezeichner"-Funktion erzwingt eine Inlineerweiterung von der [_alloca](../../c-runtime-library/reference/alloca.md) Funktion innerhalb einer Schleife, die einen Stapelüberlauf verursachen kann, wenn die Schleife ausgeführt wird.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass die Funktion 'Bezeichner' nicht geändert wird, mit der [__forceinline](../../cpp/inline-functions-cpp.md) Bezeichner.  
  
2.  Stellen Sie sicher, dass die "Bezeichner"-Funktion keine enthält ein [_alloca](../../c-runtime-library/reference/alloca.md) -Funktion, die in einer Schleife befindet.  
  
3.  Geben Sie die [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/Ox](../../build/reference/ox-full-optimization.md), oder [/Og](../../build/reference/og-global-optimizations.md) Kompilierung Switch.  
  
4.  Ort der [_alloca](../../c-runtime-library/reference/alloca.md) -Funktion einer [versuchen-except-Anweisung](../../cpp/try-except-statement.md) abgefangen, der einen Stapelüberlauf.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird `MyFunction` in einer Schleife aufgerufen und `MyFunction` ruft die `_alloca` -Funktion auf. Der `__forceinline` -Modifizierer bewirkt die Inlineerweiterung der `_alloca` -Funktion.  
  
```  
// c4750.cpp  
// compile with: /O2 /W1 /c  
#include <intrin.h>  
  
char * volatile newstr;  
  
__forceinline void myFunction(void) // C4750 warning  
{  
// The _alloca function does not require a __try/__except   
// block because the example uses compiler option /c.  
    newstr = (char * volatile) _alloca(1000);  
}  
  
int main(void)  
{  
    for (int i=0; i<50000; i++)  
       myFunction();  
    return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [_alloca](../../c-runtime-library/reference/alloca.md)
