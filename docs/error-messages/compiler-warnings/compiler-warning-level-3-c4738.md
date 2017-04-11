---
title: Compilerfehler Warnung (Stufe 3) C4738 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4738
dev_langs:
- C++
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
caps.latest.revision: 9
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: ce2db890b7b90eedf5b4456e875a06f8f92b0289
ms.lasthandoff: 04/04/2017

---
# <a name="compiler-warning-level-3-c4738"></a>Compilerwarnung (Stufe 3) C4738
Das 32-Bit-Gleitkommaergebnis wird im Speicher gespeichert. Möglicherweise kommt es zu einem Leistungsverlust  
  
 C4738 warnt davor, dass das Ergebnis einer Zuweisung, umgewandelt, Argument übergebene oder anderen Vorgang möglicherweise gerundet werden soll oder dass der Vorgang nicht genügend Register war und zum Verwenden von Speicher (Überlaufs) erforderlich sind. Dies kann zu Leistungseinbußen führen.  
  
 Um diese Warnung beheben, und vermeiden Sie Rundung, kompilieren Sie mit [/fp: fast](../../build/reference/fp-specify-floating-point-behavior.md) oder `double` anstelle von `float`.  
  
 Um diese Warnung beheben, und vermeiden Sie die Ausführung nicht genügend Register, die Reihenfolge der Berechnungen ändern, und ändern Sie die Verwendung von Inlinefunktionen  
  
 Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Compiler deaktivierte Compilerwarnungen standardmäßig](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4738 generiert:  
  
```  
// C4738.cpp  
// compile with: /c /fp:precise /O2 /W3  
// processor: x86  
#include <stdio.h>  
  
#pragma warning(default : 4738)  
  
float func(float f)  
{  
    return f;  
}  
  
int main()  
{  
    extern float f, f1, f2;  
    double d = 0.0;  
  
    f1 = func(d);  
    f2 = (float) d;  
    f = f1 + f2;   // C4738  
    printf_s("%f\n", f);  
}  
```
